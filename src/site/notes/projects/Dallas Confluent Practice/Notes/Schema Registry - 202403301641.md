---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/schema-registry-202403301641/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:32.712-05:00","updated":"2025-01-26T11:44:00.641-06:00"}
---


# Schema Registry

Helps with schema problems in [[maps/Apache Kafka\|Apache Kafka]]

First local cache is checked for the message schema. In case of cache miss, schema is pulled from the schema registry. An exception will be thrown in the Schema Registry does not have the schema (which should never happen if you set it up properly)

- Kafka takes bytes as an input and publishes them
- There is no data verification in Kafka
- Changes to data shape causes consumers to break
- We need data to be self describable
- Evolve data without breaking downstream consumers
- Schema registry helps manage changes to schemas and provides a way to validate data

## Why Not Kafka Broker as Schema Registry?

- Kafka doesn't parse or even read your data (no CPU Usage)
- Kafka would lose zero copy (copy directly to disk)
- Kafka distributes bytes, would require deserialization
- Would lose performance overall

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240406180923577.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240406180923577.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330164342140.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330164342140.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330165312505.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330165312505.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330165732173.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330165732173.webp)

# References

# Flashcards

What isn't a feature of the Confluent schema registry?
- Store avro data
- Enforce compatibility rules
- Store schemas
?
Store avro data
<!--SR:!2025-01-26,2,241-->

A consumer application is using KafkaAvroDeserializer to deserialize Avro messages. What happens if message schema is not present in AvroDeserializer local cache?:: Fetches schema from Schema Registry
<!--SR:!2025-01-28,4,278-->

<!--SR:!2024-06-06,4,270-->

Using the Confluent Schema Registry, where are Avro schema stored?:: In the `_schemas` topic
<!--SR:!2025-02-10,15,298-->

<!--SR:!2024-07-18,21,250-->

What client protocol is supported for the schema registry? (select two)
- SASL
- Websocket
- HTTP
- HTTPS
- JDBC
?
- HTTP
- HTTPS
<!--SR:!2025-02-24,35,290-->

I am producing Avro data on my Kafka cluster that is integrated with the Confluent Schema Registry. After a schema change that is incompatible, I know my data will be rejected. Which component will reject the data?:: The Confluent Schema Registry is your safeguard against incompatible schema changes and will be the component that ensures no breaking schema evolution will be possible. Kafka Brokers do not look at your payload and your payload schema, and therefore will not reject data
<!--SR:!2025-02-06,12,279-->

<!--SR:!2024-08-11,45,290-->

When using the Confluent Kafka Distribution, where does the schema registry reside?:: As a separate JVM component. Schema registry is a separate application that provides RESTful interface for storing and retrieving Avro schemas.
<!--SR:!2025-01-28,4,278-->

<!--SR:!2024-08-27,49,294-->

In Avro, removing a field that does not have a default is a ==breaking== schema evolution
<!--SR:!2025-02-01,8,258-->

<!--SR:!2024-08-24,58,314-->

In Java, Avro SpecificRecords classes are:: automatically generated from an Avro Schema + a Maven / Gradle Plugin. SpecificRecord is created from generated record classes
<!--SR:!2025-01-27,3,258-->

<!--SR:!2024-07-17,20,274-->

In Avro, removing or adding a field that has a default is a ==full== schema evolution
<!--SR:!2025-01-25,1,221-->

<!--SR:!2024-09-29,76,319-->

Which of the following is not an Avro primitive type?
- string
- date
- long
- int
- null
?
date
<!--SR:!2025-01-30,10,279-->

In Avro, adding an element to an enum without a default is a ==breaking== schema evolution
<!--SR:!2025-01-25,4,279-->

<!--SR:!2024-09-19,68,319-->
