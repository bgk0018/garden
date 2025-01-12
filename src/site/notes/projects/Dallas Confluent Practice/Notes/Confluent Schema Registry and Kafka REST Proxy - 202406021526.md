---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/confluent-schema-registry-and-kafka-rest-proxy-202406021526/","tags":["♣️/kafka","📖"],"created":"2024-06-01T21:21:37.763-05:00","updated":"2024-11-10T13:34:18.000-06:00"}
---


# Confluent Schema Registry and Kafka REST Proxy

## Confluent Schema Registry

- Store and retrieve schemas for Producers/Consumers
- Enforce compatibility on topics
- Decrease payload size

Schema REST Operations:

- Add
- Retrieve
- Update
- Delete

## Kafka Avro Console Producer and Consumer

```bash
kafka-avro-console-producer
```

```bash
kafka-avro-console-consumer
```

You can use these and a schema registry reference to leverage the schema registry for sending data to kafka

## Reminder Schema Evolution

Write with Old Schema (v1) --> Read with New Schema (v2) is Backwards compatible

- Less common as all readers need to be updated before producer can change to v2  
Write with New Schema (v2) --> Read with Old Schema (v1) is Forwards compatible
- More common as producer can update immediately and consumers can update over time

## Kafka Schema Registry Deep Dive

- Schema registry allows us to offload a lot of the size of the serialization and payload by pushing the schema out to the registry and then only holding reference to a byte that contains the version of the schema and the schema id as well as the actual content of the message
- You will want high durability and availability for your schema registry so consider creating a high availability cluster for the schema registry as well

# References

# Flashcards
