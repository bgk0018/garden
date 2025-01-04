---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/confluent-fundamentals-accreditation/","title":"Confluent Fundamentals Accreditation","tags":["⏱️","🎓"],"created":"2024-06-04T21:14:58.249-05:00","updated":"2024-11-10T16:21:00.000-06:00"}
---


# Confluent Fundamentals Accreditation

Kafka uses a (blank) model for consumers.

- Push
- Publish
- **Subscribe**
- Enrollment

Load balancing of Kafka Clients across multiple brokers is accomplished using

- **Partitions**
- Replicas
- Offsets
- Connectors

When writing a message with no key to a Kafka topic and using the default partitioner, all messages will be written

- To the same partition of the topic
- To the same segment file of the topic
- **In a round robin method across all partition of the topic**
- Messages without keys are not allowed in Kafka

Kafka is well suited for (blank) types of operations

- Batch
- Real Time
- Streaming
- **All of the above**

Which of the following are benefits of event stream processing over batch processing? (Pick two)

- **Compute results with low latency in near real-time**
- Execute periodic (daily, weekly, monthly) jobs
- Perform flexible search and ad-hoc queries
- **Compute efficiently over large, continuous, unbounded data sets**

Which of the following technologies can be used to perform event stream processing? (Pick two)

- Confluent Schema Registry
- **Apache Kafka Streams**
- **Confluent KSQL**
- Confluent Replicator

Which of the following use cases would benefit most from continuous event stream processing? (Pick three)

- **Fraud Detection**
- **Context-aware product recommendations for e-commerce**
- End of the day financial settlement processing
- **Log monitoring/application fault detection**

What is the default maximum message size a Kafka broker can receive? (Pick one)

- **1,048,588 bytes**
- 100 bytes
- 10,000 bytes
- 254,200 bytes

Which events will initiate the consumer rebalancing? (Pick three)

- **Consumers joins the consumer group**
- A new producer starts writing messages to the topic in question
- **A consumer leaves the group**
- A new broker is added to the cluster
- **Partitions are added to the topic**

Which actions are undertaken by the controller in case it detects the failure of a broker (which was leader for some partitions)? (Pick three)

- Controller waits for a new leader to be nominated by ZooKeeper
- **Controller selects a new leader and updates the ISR list**
- **Controller persists the new leader and ISR list to ZooKeeper**
- **Controller sends the new leader and ISR list changes to all brokers**

What is the relationship between topics and partitions: (Pick one)

- A topic always has one partition
- **A topic may have more than one partition**
- A partition always has one topic
- A partition may have more than one topic
- There is no relationship between topics and partitions

Kafka message Offset numbers: (Pick one)

- Are unique within a topic
- Are reused after messages are deleted
- **Are unique within a partition**
- Can be non sequential in the log with multiple producers
- Are transparent to brokers

Messages produced to a Kafka cluster are stored in the form of: (Pick one)

- JSON data
- Plain text
- **Bytes**
- Sequence Files

Which of the following are true of the Confluent Schema Registry? (Pick three)

- **It provides a serving layer for your metadata and a RESTful interface for storing and retrieving Avro, Protobuf, or JSON Schema**
- **It provides serializers that plug into Apache Kafka clients, which handle schema storage and retrieval of Kafka messages sent in Avro format.**
- Increases the size of messages by adding the schema in the message.
- **It reduces the overhead with kafka messages by separating the schema and storing and ID.**

Which of the following might be essential sources of events in Kafka?

- IoT devices
- Banking Transactions
- Web Logs
- Database updates
- **All of the above**

Brokers make up a Kafka cluster. Brokers are networked together and act as a single cluster and could run in which of the following? (Select three)

- **VM**
- **Containers**
- **Physical Machines**
- Network File System

Your consumer application could be doing many things. Select any two from below that is typical of consumer applications. (Select two)

- **Creating Reports**
- **Updating Dashboards**
- Publishing data to the brokers
- Batching data to send to Kafka

Kafka uses Apache Zookeeper to manage consensus. Zookeeper acts as a distributed consensus manager. Zookeeper stores information about :

- ACLs
- Failure detection and recovery
- Cluster Management
- Controllers
- **All of the above**

The fundamental data structure that kafka uses to store its messages is called a Log. Which of the following are characteristics of a log. (Select three)

- **Can have multiple consumers reading from the log**
- **Logs are immutable**
- **Multiple producers can write to the logs**
- Only one consumer at a time can read from the log

Logs store data. Each event record is written at a particular offset in the log. The default retention period for data in the logs is (blank).

- **One week**
- One month
- One day
- None of the above

Which of the following are true of timestamps in Kafka messages. (select two)

- Timestamps are optional in the message
- **Every message has a timestamp**
- **If you don’t have a time stamp, one will be provided for you--you will get message creation time**
- You must always use the current time in the message

When you produce data to a Kafka cluster, your data will be sent to the

- Controller
- Zookeeper
- **Broker that is the Leader of the Partition**
- Followers in the cluster

What are the levels of data, or message, durability provided by Kafka? (Pick one)

- [[projects/Dallas Confluent Practice/Notes/At Least Once Delivery - 202303012107\|At least once delivery]] guarantees
- Exactly once delivery guarantees
- At most once delivery guarantees
- **All of the above**
