---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-topics-cli-202406011123/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:24.532+01:00","updated":"2024-06-27T23:01:08.008+01:00"}
---

# Kafka Topics CLI

Kafka Topics CLI, i.e., kafka-topics is used to create, delete, describe, or change a topic in Kafka. 

## References

[Conduktor](https://www.conduktor.io/kafka/kafka-topics-cli-tutorial/)  
[Confluent](https://docs.confluent.io/kafka/operations-tools/kafka-tools.html#kafka-topics-sh)
## Flashcards

From the CLI, create people topic with 3 paritions and replication factor of 1:: `kafka-topics --bootstrap-server localhost:9092 --create --topic people --replication-factor 1 --partitions 3`
<!--SR:!2024-07-01,20,270-->

From the CLI, list topics:: `kafka-topics --bootstrap-server localhost:9092 --list`
<!--SR:!2024-06-17,13,270-->

From the CLI, describe people topic:: `kafka-topic --bootstrap-server localhost:9092 --describe --topic people`
<!--SR:!2024-06-22,17,290-->

From the CLI, create a topic people.promotions with configuration compact clean up policy partition count of 1, replication factor of 1, configuration retention of 6 minutes:: `kafka-topics --bootstrap-server localhost:9092 --create --topic people.promotions --partitions 1 --replication-factor 1 --config retention.ms=360000 --config cleanup.policy=compact`
<!--SR:!2024-07-06,9,210-->

How will you find out all the partitions where one or more of the replicas for the partition are not in-sync with the leader?:: `kafka-topics.sh --zookeeper localhost:2181 --describe --under-replicated-partitions`
<!--SR:!2024-06-14,1,130-->

How will you find out all the unavailable partitions?:: `kafka-topics.sh --zookeeper localhost:2181 --describe --unavailable-partitions` Please note that as of Kafka 2.2, the --zookeeper option is deprecated and you can now use: `kafka-topics.sh --bootstrap-server localhost:9092 --describe --unavailable-partitions`
<!--SR:!2024-06-28,1,130-->



How do you create a topic named test with 3 partitions and 3 replicas using the Kafka CLI?:: `bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 3 --topic test`
<!--SR:!2024-06-15,3,265-->

