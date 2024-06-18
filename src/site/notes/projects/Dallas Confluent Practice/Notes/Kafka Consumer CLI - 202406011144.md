---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-consumer-cli-202406011144/","tags":["📖","♣️/kafka"],"created":"2024-03-31T02:14:47.800-05:00","updated":"2024-06-13T13:44:07.762-05:00"}
---

# Kafka Consumer CLI

The Kafka console consumer CLI, kafka-console-consumer is used to read data from Kafka and output it to standard output.

## References

- [Conduktor](https://www.conduktor.io/kafka/kafka-consumer-cli-tutorial/)
- [Confluent](https://docs.confluent.io/kafka/operations-tools/kafka-tools.html#kafka-console-consumer-sh)
- 
## Flashcards

From the CLI, consume all people messages from the beginning:: `kafka-console-consumer --bootstrap-server localhost:9092 --topic people --from-beginning`
<!--SR:!2024-06-16,12,270-->

From the CLI, consume all pet messages and print the key of messages from the beginning:: `kafka-console-consumer --bootstrap-server localhost:9092 --topic pets --from-beginning --property print.key=true`
<!--SR:!2024-07-05,24,270-->

From the CLI, specify an explicit consumer group id while consuming from pets topic and print each messages offset from the beginning::: `kafka-console-consumer --bootstrap-server localhost:9092 --topic pets --from-beginning --group adam-pet-consumer --property print.offset=true`
<!--SR:!2024-07-04,21,250!2024-06-22,17,290-->

From the CLI, specify an explicit consumer group id adam-people-consumer for people topic and print message timestamp from the beginning:::`kafka-console-consumer --bootstrap-server localhost:9092 --topic people --from-beginning --group adam-people-consumer --property print.timestamp=true`
<!--SR:!2024-06-15,11,270!2024-06-20,15,290-->

The kafka-console-consumer CLI, when used with the default options uses a ==random== group id
<!--SR:!2024-06-26,15,296-->

Which Kafka CLI should you use to consume from a topic?:: kafka-console-consumer
<!--SR:!2024-06-25,14,296-->