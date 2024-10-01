---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-streams-for-data-processing-202406021531/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:38:55.072-05:00","updated":"2024-06-13T17:49:53.000-05:00"}
---

# Kafka Streams for Data Processing

What is Kafka Streams?

- Easy data processing and transformation library within Kafka
- Ships with Kafka Library
- No separate cluster needed for Kafka Streams as opposed to Flink
- Has exactly once capabilities
- On record at a time processing (no batching)
- Works for any application size

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240331111226293.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240331111226293.webp)

Kafka Stream vs Spark Streaming, NiFi, Flink?
- Data streaming over micro batch
- Cluster required for other options besides Kafka Stream
- Scales easily by just adding java processes
- Exactly once semantics
- All code-based

# References


# Flashcards