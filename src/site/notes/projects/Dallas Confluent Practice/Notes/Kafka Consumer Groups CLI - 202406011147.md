---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-consumer-groups-cli-202406011147/","tags":["📖","♣️/kafka"],"created":"2024-03-31T02:14:47.821-05:00","updated":"2024-06-11T21:25:02.000-05:00"}
---

# Kafka Consumer Groups CLI

The Kafka Consumer Groups CLI kafka-consumer-groups is used to manage consumer groups in Kafka.

## References

- [Conduktor](https://www.conduktor.io/kafka/kafka-consumer-group-management-cli-tutorial/)
- [Confluent](https://docs.confluent.io/kafka/operations-tools/kafka-tools.html#kafka-consumer-groups-sh)
## Flashcards

From the CLI, look at where each consumer group is at for each topic partition::: `kafka-consumer-groups --bootstrap-server localhost:9092 --describe --all-groups`
<!--SR:!2024-06-14,3,210!2024-06-14,10,270-->
From the CLI, look at where a consumer group adam-people-consumer is at for each topic partition::: `kafka-consumer-groups --bootstrap-server localhost:9092 --describe --group adam-people-consumer`
<!--SR:!2024-06-17,12,270!2024-06-14,10,270-->
From the CLI, dry run reset the adam-pet-consumer group to the earliest position of the topic people:: `kafka-consumer-groups --bootstrap-server localhost:9092 --group adam-pet-consumer --reset-offsets --to-earliest --topic people --dry-run`
<!--SR:!2024-06-18,7,230-->
From the CLI, execute a reset for the adam-pet-consumer group to the beginning of the topic people::: `kafka-consumer-groups --bootstrap-server localhost:9092 --group adam-pet-consumer --reset-offsets --to-earliest --topic people --execute`
<!--SR:!2024-06-24,13,230!2024-06-18,13,290-->
From the CLI, reset adam-people-consumer group people topic partition 0 to an offset of 1:: `kafka-consumer-groups --bootstrap-server localhost:9092 --group adam-people-consumer --reset-offsets --to-offset 1 --topic people:0 --execute`
<!--SR:!2024-06-18,7,230-->