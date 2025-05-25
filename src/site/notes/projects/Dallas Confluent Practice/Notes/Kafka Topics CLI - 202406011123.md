---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-topics-cli-202406011123/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:30.628-05:00","updated":"2025-02-04T13:57:23.000-06:00"}
---


# Kafka Topics CLI

Kafka Topics CLI, i.e., kafka-topics is used to create, delete, describe, or change a topic in Kafka. 

## References

[Conduktor](https://www.conduktor.io/kafka/kafka-topics-cli-tutorial/)  
[Confluent](https://docs.confluent.io/kafka/operations-tools/kafka-tools.html#kafka-topics-sh)

## Flashcards

From the CLI, create people topic with 3 paritions and replication factor of 1:: `kafka-topics --bootstrap-server localhost:9092 --create --topic people --replication-factor 1 --partitions 3`
<!--SR:!2025-02-05,11,270-->

<!--SR:!2024-09-26,79,290-->

From the CLI, list topics:: `kafka-topics --bootstrap-server localhost:9092 --list`
<!--SR:!2025-01-25,1,226-->

<!--SR:!2024-07-18,3,230-->

From the CLI, describe people topic:: `kafka-topic --bootstrap-server localhost:9092 --describe --topic people`
<!--SR:!2025-01-27,3,264-->

<!--SR:!2024-09-17,70,310-->

From the CLI, create a topic people.promotions with configuration compact clean up policy partition count of 1, replication factor of 1, configuration retention of 6 minutes:: `kafka-topics --bootstrap-server localhost:9092 --create --topic people.promotions --partitions 1 --replication-factor 1 --config retention.ms=360000 --config cleanup.policy=compact`
<!--SR:!2025-01-26,2,210-->

<!--SR:!2024-08-06,28,230-->

How will you find out all the partitions where one or more of the replicas for the partition are not in-sync with the leader?:: `kafka-topics.sh --zookeeper localhost:2181 --describe --under-replicated-partitions`
<!--SR:!2025-01-25,1,226-->

<!--SR:!2024-07-16,1,130-->

How will you find out all the unavailable partitions?:: `kafka-topics.sh --zookeeper localhost:2181 --describe --unavailable-partitions` Please note that as of Kafka 2.2, the --zookeeper option is deprecated and you can now use: `kafka-topics.sh --bootstrap-server localhost:9092 --describe --unavailable-partitions`
<!--SR:!2025-01-25,2,210-->

<!--SR:!2024-07-19,4,170-->

How do you create a topic named test with 3 partitions and 3 replicas using the Kafka CLI?:: `bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 3 --topic test`
<!--SR:!2025-01-27,3,266-->

<!--SR:!2024-07-22,13,285-->
