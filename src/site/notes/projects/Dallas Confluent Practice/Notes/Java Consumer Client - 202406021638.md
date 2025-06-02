---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/java-consumer-client-202406021638/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:19.270-06:00","updated":"2025-01-26T11:45:31.583-06:00"}
---


# Java Consumer Client

Multiple topics can be passed as a list or regex pattern.

## References

## Flashcards

A consumer wants to read messages from a specific partition of a topic. How can this be achieved?::: Call `assign()` passing a Collection of `TopicPartitions` as the argument
<!--SR:!2025-01-27,2,220!2025-01-27,3,260-->

<!--SR:!2024-07-19,22,250!2024-08-06,40,290-->

Select all the way for one consumer to subscribe simultaneously to the following topics - topic.history, topic.sports, topic.politics? (select two)
- `consumer.subscribePrefix("topic.");`
- `consumer.subscribe(Pattern.compile("topic\..*"));`
- `consumer.subscribe("topic.history"); consumer.subscribe("topic.sports"); consumer.subscribe("topic.politics");`
- `consumer.subscribe(Arrays.asList("topic.history", "topic.sports", "topic.politics"));`
?
- `consumer.subscribe(Pattern.compile("topic\..*"));`
- `consumer.subscribe(Arrays.asList("topic.history", "topic.sports", "topic.politics"));`
<!--SR:!2025-02-18,29,290-->

A consumer wants to read messages from partitions 0 and 1 of a topic topic1. Code snippet is shown below.
```java
consumer.subscribe(Arrays.asList("topic1"));
List<TopicPartition> pc = new ArrayList<>();
pc.add(new PartitionTopic("topic1", 0));
pc.add(new PartitionTopic("topic1", 1));
consumer.assign(pc);
```
?  
Throws IllegalStateException subscribe() and assign() cannot be called by the same consumer, subscribe() is used to leverage the consumer group mechanism, while assign() is used to manually control partition assignment and reads assignment

<!--SR:!2024-08-11,33,268-->

How can you gracefully make a Kafka consumer to stop immediately polling data from Kafka and gracefully shut down a consumer application?:: Call consumer.wakeUp() and catch a WakeUpException
<!--SR:!2025-01-29,5,231-->

<!--SR:!2024-08-13,47,308-->

When shutting down your consumer and calling `consumer.wakeUp()` you should also call close so that:: The consumer who is shutting down will commit any remaining offsets and send the group coordinator broker a message that the consumer is leaving the group for a more efficient consumer group rebalance
<!--SR:!2025-01-25,2,247-->

<!--SR:!2024-07-19,4,284-->

If you want to start reading all messages from the beginning of the partition:: `seekToBeginning(Collection<TopicPartition> tp)`
<!--SR:!2025-01-29,5,234-->

<!--SR:!2024-08-08,2,264-->

If you want to start reading all messages from the end of the partition and only consume new messages:: `seekToBeginning(Collection<TopicPartition> tp)`
<!--SR:!2025-01-25,2,216-->

<!--SR:!2024-07-19,4,284-->

You can run custom code when partitions are added or removed from a consumer by:: passing a `ConsumerRebalanceListener` when calling the `subscribe()` method
<!--SR:!2025-01-26,2,216-->

A `ConsumerRebalanceListener` interface has what methods
?
- `onPartitionsAssigned(Collection<TopicPartition> partitions)`
- `onPartitionsRevoked(Collection<TopicPartition> partitions)`
- `onPartitionsLost(Collection<TopicPartition> partitions)`
<!--SR:!2025-01-26,1,204-->

What are the qualities of `onPartitionsAssigned(Collection<TopicPartition> partitions)` being invoked?:: Will be invoked on every rebalance as a way of notifying the consumer that a rebalance happened. If no new partitions were assigned, the collection will be empty
<!--SR:!2025-01-28,2,219-->

<!--SR:!2024-07-19,4,284-->

What are the qualities of `onPartitionsRevoked(Collection<TopicPartition> partitions)` being invoked?:: Will be invoked in normal rebalance conditions when the consumer has given up partition ownership. The collection will never be empty when invoked
<!--SR:!2025-01-26,2,239-->

<!--SR:!2024-07-19,4,284-->

What are the qualities of `onPartitionsLost(Collection<TopicPartition> partitions)` being invoked?:: Will be invoked during an exceptional rebalance, the partitions passed in the collection will already have new owners before this is invoked
<!--SR:!2025-01-27,3,259-->

<!--SR:!2024-07-19,4,284-->

Before a Consumer Rebalance, it's a good idea to use the `ConsumerRebalanceListener` to:: Commit your current offset
<!--SR:!2025-02-08,14,292-->

<!--SR:!2024-07-19,4,284-->

If you want to control when you commit during a large batch, you can use:: `consumer.commitAsync(currentOffsets, null)` and `consumer.commitSync()` with a modulus to segment the batch periodically
<!--SR:!2025-01-25,1,174-->

<!--SR:!2024-07-19,4,284-->

Why might we want to use both `consumer.commitAsync` and `consumer.commitSync`?:: Since async doesn't wait and releases the current thread, it will be more performant, however when we go to shutdown a consumer, it makes sense to block on the current thread and wait until commitSync has completed before exiting
<!--SR:!2025-01-25,1,220-->

<!--SR:!2024-07-19,4,284-->

Whenever you call `poll()`, and `enable.auto.commit=true`, when will the consumer commit?:: The next time `poll()` is called and the `auto.commit.interval.ms` period has elapsed it will commit the last offset of the previous `poll()` whether it was actually completed or not
<!--SR:!2025-01-26,2,227-->

<!--SR:!2024-07-19,4,284-->
