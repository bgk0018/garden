---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/message-serializer-202405302131/","tags":["📖","♣️/kafka"],"created":"2024-03-19T18:32:56.696+00:00","updated":"2024-06-12T03:07:17.000+01:00"}
---

# Message Serializer

Transforms objects/data into bytes  
They are used on the value and the key of the [[projects/Dallas Confluent Practice/Notes/Message Anatomy - 202405302129\|Message Anatomy]]

Common Serializers include
- JSON
- Int, Float
- Avro
- Protobuf

## References


## Flashcards

Used to transform objects/data into bytes to be sent to a [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]]::: Message Serializer
<!--SR:!2024-06-21,16,290!2024-06-16,12,270-->
Message serialization is used on what parts of the message:: The value and the key of the message
<!--SR:!2024-07-04,23,270-->
Common Apache Kafka Serializers::: JSON, Int, Float, Avro, Protobuf
<!--SR:!2024-06-19,14,290!2024-06-21,16,290-->