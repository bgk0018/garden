---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/resetting-consumer-group-offsets-202406011212/","tags":["♣️/kafka","📖"],"created":"2024-03-30T16:28:34.618-05:00","updated":"2024-11-10T13:47:18.000-06:00"}
---


# Resetting Consumer Group Offsets

This process allows consumers to reprocess messages, skip past certain messages, or start processing from a different point in the topic.

1. **Reprocessing Data**: If there's a need to reprocess old data, such as after fixing a bug in the consumer logic.
2. **Skipping Faulty Data**: If certain messages caused errors and you need to skip them.
3. **Starting Fresh**: If the consumer group is repurposed to handle a new set of messages.
4. **Recovery from Issues**: After recovering from an outage or data corruption.

## Kafka Consumer Group Command

- The [[projects/Dallas Confluent Practice/Notes/Kafka Consumer Groups CLI - 202406011147\|Kafka Consumer Groups CLI]] can be used to reset offsets.
- Common usage: `kafka-consumer-groups.sh --bootstrap-server <broker> --group <group_id> --topic <topic> --reset-offsets --to-earliest`
  
- Options include:
    - `--to-earliest`: Reset offsets to the earliest available messages.
    - `--to-latest`: Reset offsets to the latest messages.
    - `--to-datetime <timestamp>`: Reset offsets to the messages at or after the specified timestamp.
    - `--by-offset <num>`: Reset offsets by a specific offset number.
    - `--shift-by <num>`: Shift current offsets forward or backward by a specified number.
    - `--to-current`: Reset to the current offset (useful for testing).
    - `--dry-run`: Simulate the reset without actually changing the offsets.

## AdminClient API

The AdminClient API allows you to manage and alter consumer group offsets programmatically. This is a more flexible and powerful way to reset offsets, especially for applications that need to automate this process.

```java
import org.apache.kafka.clients.admin.AdminClient;
import org.apache.kafka.clients.admin.AdminClientConfig;
import org.apache.kafka.clients.admin.OffsetSpec;
import org.apache.kafka.clients.admin.OffsetAndMetadata;
import org.apache.kafka.clients.admin.ListOffsetsResult;
import org.apache.kafka.clients.admin.AlterConsumerGroupOffsetsResult;
import org.apache.kafka.common.TopicPartition;

import java.util.Collections;
import java.util.Map;
import java.util.Properties;

public class OffsetResetExample {
    public static void main(String[] args) throws Exception {
        Properties props = new Properties();
        props.put(AdminClientConfig.BOOTSTRAP_SERVERS_CONFIG, "localhost:9092");
        try (AdminClient adminClient = AdminClient.create(props)) {
            String consumerGroupId = "my-group";
            TopicPartition topicPartition = new TopicPartition("my-topic", 0);

            // Example: Reset to earliest
            ListOffsetsResult listOffsetsResult = adminClient.listOffsets(
                Collections.singletonMap(topicPartition, OffsetSpec.earliest()));
            long earliestOffset = listOffsetsResult.partitionResult(topicPartition).get().offset();

            // Create the offset map to update
            Map<TopicPartition, OffsetAndMetadata> offsetsToReset = Collections.singletonMap(
                topicPartition, new OffsetAndMetadata(earliestOffset));

            // Reset offsets
            AlterConsumerGroupOffsetsResult resetOffsetsResult =
                adminClient.alterConsumerGroupOffsets(consumerGroupId, offsetsToReset);
            resetOffsetsResult.all().get ();
            System.out.println("Offsets reset successfully.");
        }
    }
}

```

## References

- [ChatGPT](https://chatgpt.com/share/dc579317-8edc-422d-90fe-ee93e0cd1744)

## Flashcards

Using the Kafka Consumer Group CLI Command, how would you reset the consumer group offsets to the earliest?:: `kafka-consumer-groups.sh --bootstrap-server <broker> --group <group_id> --topic <topic> --reset-offsets --to-earliest --execute`

<!--SR:!2024-09-19,66,270-->

Using AdminClient API, how would you reset the consumer group offsets to the earliest?:: `adminClient.alterConsumerGroupOffsets(consumerGroupId, offsetsToReset);`

<!--SR:!2024-07-16,1,130-->
