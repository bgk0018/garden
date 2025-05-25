---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-producer-cli-202406011140/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:34.006-05:00","updated":"2025-01-24T21:32:16.868-06:00"}
---


# Kafka Producer CLI

The Kafka console producer CLI, kafka-console-producer is used to read data from standard input and publish it to Kafka.

## References

- [Conduktor](https://www.conduktor.io/kafka/kafka-producer-cli-tutorial/)
- [Confluent](https://docs.confluent.io/kafka/operations-tools/kafka-tools.html#kafka-console-producer-sh)

## Flashcards

From the CLI, publish data to the people topic::`kafka-console-producer --bootstrap-server localhost:9092 --topic people` and `{"name":"Stewie", "show": "Family Guy"}`
<!--SR:!2025-01-25,4,270-->

<!--SR:!2024-08-17,39,290-->

From the CLI, publish some pets with an explicit parsed key separated by a pipe character:: `kafka-console-producer --bootstrap-server localhost:9092 --topic pets --property "parse.key=true" --property "key.separator=|"`
<!--SR:!2025-01-27,3,212-->

<!--SR:!2024-08-01,23,190-->
