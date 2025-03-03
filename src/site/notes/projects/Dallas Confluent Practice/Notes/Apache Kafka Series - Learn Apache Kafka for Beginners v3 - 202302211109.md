---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/apache-kafka-series-learn-apache-kafka-for-beginners-v3-202302211109/","title":"Apache Kafka Series - Learn Apache Kafka for Beginners v3","tags":["🎓","⏱️"],"created":"2025-02-24T16:13:22.359-06:00","updated":"2024-11-10T16:22:19.000-06:00"}
---


# 202302211109 - Apache Kafka Series - Learn Apache Kafka for Beginners V3

## Introduction

Used to decouple direct integrations between many different systems, lowering the total complexity of a system. [[projects/Dallas Confluent Practice/Notes/Apache Kafka - 202302211117\|Apache Kafka]]. This allows more effective scaling.

A distributed, resilient, and fault tolerant streaming platform. Has good [[projects/Dallas Confluent Practice/Notes/Horizontal Scaling - 202302211120\|Horizontal Scaling]] and high performance.

- Used as a messaging system
- Activity Tracker
- Aggregate metrics
- Application logs
- Stream processing
- Decoupling system dependencies
- Big data
- Microservices pub/sub

Kafka is only used as a transportation mechanism


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Introduction to Apache Kafka

- [[projects/Dallas Confluent Practice/Notes/Real World Insights and Case Studies - 202406021533\|Real World Insights and Case Studies]]  
- [[projects/Dallas Confluent Practice/Notes/Kafka in the Enterprise for Admins - 202406021529\|Kafka in the Enterprise for Admins]]  


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Kafka Architecture

- [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]]
- [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]]
- [[projects/Dallas Confluent Practice/Notes/Offset - 202405282304\|Offset]]
- [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Brokers]]
	- [[projects/Dallas Confluent Practice/Notes/Broker Discovery - 202405302218\|Broker Discovery]]
- [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]]
- [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]]
- [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replica]]
- [[projects/Dallas Confluent Practice/Notes/Topic Durability - 202406011116\|Topic Durability]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Producers

- [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]]
- [[projects/Dallas Confluent Practice/Notes/Message Key - 202303012028\|Message Key]]
- [[projects/Dallas Confluent Practice/Notes/Message Anatomy - 202405302129\|Message Anatomy]]
- [[projects/Dallas Confluent Practice/Notes/Message Serializer - 202405302131\|Message Serializer]]
- [[projects/Dallas Confluent Practice/Notes/Producer Acknowledgement - 202405302231\|Producer Acknowledgement]]
- [[projects/Dallas Confluent Practice/Notes/Java Producer Client - 202406021637\|Java Producer Client]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Consumers

- [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]]
- [[projects/Dallas Confluent Practice/Notes/Consumer Deserializer - 202405302142\|Consumer Deserializer]]
- [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Group]]
- [[projects/Dallas Confluent Practice/Notes/Consumer Offsets - 202405302152\|Consumer Offset]]
- [[projects/Dallas Confluent Practice/Notes/Delivery Semantics - 202405302156\|Delivery Semantics]]
	- [[projects/Dallas Confluent Practice/Notes/At Least Once Delivery - 202303012107\|At Least Once Delivery]]
	- [[projects/Dallas Confluent Practice/Notes/At Most Once Delivery - 202303012109\|At Most Once Delivery]]
	- [[projects/Dallas Confluent Practice/Notes/Exactly Once Delivery - 202303012110\|Exactly Once Delivery]]
- [[projects/Dallas Confluent Practice/Notes/Resetting Consumer Group Offsets - 202406011212\|Resetting Consumer Group Offsets]]
- [[projects/Dallas Confluent Practice/Notes/Java Consumer Client - 202406021638\|Java Consumer Client - 202406021638]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Kafka CLI Tools

- [[projects/Dallas Confluent Practice/Notes/Kafka Topics CLI - 202406011123\|Kafka Topics CLI]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Producer CLI - 202406011140\|Kafka Producer CLI]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Consumer CLI - 202406011144\|Kafka Consumer CLI]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Consumer Groups CLI - 202406011147\|Kafka Consumer Groups CLI]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Kafka Configuration and Setup

- [[projects/Dallas Confluent Practice/Notes/Advertised Listeners - 202406021523\|Advertised Listeners]]  
- [[projects/Dallas Confluent Practice/Notes/Advanced Topics Configuration - 202406021522\|Advanced Topics Configuration]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Data Processing with Kafka Streams

- [[projects/Dallas Confluent Practice/Notes/Kafka Streams for Data Processing - 202406021531\|Kafka Streams for Data Processing]]  
	- [[projects/Dallas Confluent Practice/Notes/KStreams and KTables Simple Operations Stateless - 202406021532\|KStreams and KTables Simple Operations Stateless]]  
	- [[projects/Dallas Confluent Practice/Notes/KStreams and KTables Advanced Operations - 202406021531\|KStreams and KTables Advanced Operations]]  
- [[projects/Dallas Confluent Practice/Notes/Exactly Once Semantics Theory - 202406021527\|Exactly Once Semantics Theory]]  
- [[projects/Dallas Confluent Practice/Notes/KSQL - 202406022143\|KSQL - 202406022143]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Schema Management

- [[projects/Dallas Confluent Practice/Notes/Schema Registry - 202403301641\|Schema Registry]]  
	- [[projects/Dallas Confluent Practice/Notes/Avro Schemas - 202406021524\|Avro Schemas]]  
	- [[projects/Dallas Confluent Practice/Notes/Avro in Java - 202406021524\|Avro in Java]]  
- [[projects/Dallas Confluent Practice/Notes/Confluent Schema Registry and Kafka REST Proxy - 202406021526\|Confluent Schema Registry and Kafka REST Proxy]]  


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Kafka Connect

- [[projects/Dallas Confluent Practice/Notes/Apache Connect Hands-on - 202406021528\|Apache Connect Hands-on]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Connect Source - 202406022136\|Kafka Connect Source - 202406022136]]
- [[Kafka Connect Sink\|Kafka Connect Sink]]

## Flashcards

To import data from external databases, I should use::: Kafka Connect Source. Kafka Connect Sink is used to export data from Kafka to external databases and Kafka Connect Source is used to import from external databases into Kafka. 
You want to sink data from a Kafka topic to S3 using Kafka Connect. There are 10 brokers in the cluster, the topic has 2 partitions with replication factor of 3. How many tasks will you configure for the S3 connector?:: 2 You cannot have more sink tasks (= consumers) than the number of partitions, so 2. 
You are using JDBC source connector to copy data from 3 tables to three Kafka topics. There is one connector created with max.tasks equal to 2 deployed on a cluster of 3 workers. How many tasks are launched?:: 2 here, we have three tables, but the max.tasks is 2, so that's the maximum number of tasks that will be created 
You are using JDBC source connector to copy data from a table to Kafka topic. There is one connector created with max.tasks equal to 2 deployed on a cluster of 3 workers. How many tasks are launched?:: 1 JDBC connector allows one task per table 

</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Cluster Management

- [[projects/Dallas Confluent Practice/Notes/Zookeeper - 202406011120\|Zookeeper]]
	- [[projects/Dallas Confluent Practice/Notes/Zookeeper Setup - 202406021533\|Zookeeper Setup]]  
- [[projects/Dallas Confluent Practice/Notes/Kafka KRaft - 202406011123\|Kafka KRaft]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Cluster - 202406021527\|Kafka Cluster]]


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Additional Tools and Integrations

- [[projects/Dallas Confluent Practice/Notes/Confluent REST Proxy - 202406021526\|Confluent REST Proxy]]  


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Security

- [[Authentication\|Authentication]]
- [[Authorization\|Authorization]]
- [[Encryption\|Encryption]] (SSL/SASL)
- [[Kafka ACLs - 202406021631 \|Kafka ACLs]] (Access Control Lists)


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Monitoring and Metrics

- Kafka Monitoring Tools
- [[projects/Dallas Confluent Practice/Notes/Metrics Collection - 202406062123\|Metrics Collection]]
- Logging
- Kafka JMX (Java Management Extensions)


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Performance Tuning and Optimization

- Producer Performance Tuning
- Consumer Performance Tuning
- Broker Performance Tuning
- Resource Allocation
- Load Balancing


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Fault Tolerance and High Availability

- Failover Mechanisms
- Data Replication Strategies
- Handling Node Failures


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Data Management and Retention

- Data Retention Policies
- Log Compaction
- Topic Cleanup Policies


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Integrations and Ecosystem

- Kafka Connectors
- Integration with Big Data Tools (Hadoop, Spark, etc.)
- Integration with Cloud Services (AWS MSK, Azure Event Hubs for Kafka, Google Cloud Pub/Sub)


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Use Cases and Patterns

- Common Use Cases (Event Sourcing, Messaging, Log Aggregation, Stream Processing)
- Design Patterns for Kafka


</div></div>
  

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Kafka Internals

- Kafka Log Structure
- Internal Data Structures
- Kafka Controller


</div></div>


# Related
