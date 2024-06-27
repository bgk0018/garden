---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/consumer-offsets-202405302152/","tags":["📖","♣️/kafka"],"created":"2024-03-19T18:32:56.876+00:00","updated":"2024-06-12T03:16:20.000+01:00"}
---

# Consumer Offsets


[[projects/Dallas Confluent Practice/Notes/Apache Kafka - 202302211117\|Apache Kafka]] stores the offsets at which a [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Group]] has been reading.

The offsets committed are in a Kafka [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topic]] named `__consumer_offsets`

When a [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]] in a [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Group]] has processed data received, it should be periodically committing the offsets.

The Kafka [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] will write to `consumer_offsets`, not the [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Group]] itself).

If a [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]] fails, it will be able to read back from where it left off thanks to the committed Consumer Offset.

## References


## Flashcards

[[projects/Dallas Confluent Practice/Notes/Consumer Offsets - 202405302152\|Consumer Offsets]] are stored::: `__consumer-offsets`
<!--SR:!2024-06-15,11,270!2024-07-03,22,270-->
True/False, [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] are responsible for committing their [[projects/Dallas Confluent Practice/Notes/Consumer Offsets - 202405302152\|Consumer Offsets]] to the `__consumer_offsets` topic:: false, the [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] will write to `__consumer_offsets`
<!--SR:!2024-06-16,11,270-->
