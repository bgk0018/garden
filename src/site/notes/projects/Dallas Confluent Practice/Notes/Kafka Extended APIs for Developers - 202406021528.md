---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-extended-ap-is-for-developers-202406021528/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:38:54.899-05:00","updated":"2024-11-08T09:43:56.812-06:00"}
---

# Kafka Extended APIs for Developers

[[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] and [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] are considered low level, and since their introduction other higher level APIs have been created, specifically:
- [[projects/Dallas Confluent Practice/Notes/Kafka Connect - 202403301639\|Kafka Connect]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Streams - 202403301640\|Kafka Streams]]
- [[projects/Dallas Confluent Practice/Notes/Schema Registry - 202403301641\|Schema Registry]]

- Kafka Brokers do NOT verify the messages they receive
- Kafka takes bytes as input with out loading them into memory (zero copy)
- Schema Registry then is a separate component
	- Producers and Consumers need to be able to talk to it
	- The Schema Registry must be able to reject bad data before sent to Kafka
	- Supports Avro, Protobuf and JSON

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170029132.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170029132.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170119062.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170119062.webp)

Gotchas:
- Needs to be highly available
- Schema formats have a learning curve (Avro, etc.)

You can also evolve schemas over time. The same problems you experience in changing any contract apply. Additions are backwards compatible, modifications or deletions are not.

Schema changes are versioned (v1, v2, etc.)

You can also assign default values for new properties as the schemas evolve.


![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170923135.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170923135.webp)

- Known data source use kafka connect source or sink depending on data flow
- Use Producer to collect directly from the source
- Consumer for producing ephemeral messages
- Kafka Streams for ETL back into Kafka
- KSQL for queries on Kafka data

# References


# Flashcards