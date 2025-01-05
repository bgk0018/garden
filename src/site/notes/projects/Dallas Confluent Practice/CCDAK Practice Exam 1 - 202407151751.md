---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/ccdak-practice-exam-1-202407151751/","tags":["⏱️","♣️/kafka"],"created":"2024-08-29T16:38:00.826-05:00","updated":"2025-01-02T22:22:20.000-06:00"}
---


# CCDAK Practice Exam 1

https://learning.datacouch.io/course/ccdak-practice-tests?previouspage=home#/course/3280285000000183032/attend/section/3280285000000183078/lesson/3280285000000183108

## References

## Flashcards

Which of the following is the correct command for creating a topic foo with 3 partitions and with a replication factor of 3?

- bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 3 --topic foo
- bin/kafka-topics-create.sh --zookeeper localhost:9092 --replication-factor 3 --partitions 3 --topic foo
- bin/kafka-topics.sh --create --broker localhost:9092 --replication-factor 3 --partitions 3 --topic foo
- bin/kafka-topics-create.sh --zookeeper localhost:2181 --num-replicas 3 --partitions 3 --topic foo  
?  
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 3 --topic foo

Which class is used to create a Producer in kafka:

- Producer Class
- KafkaProducer Class
- Kafka Class
- ConfluentProducer Class
- Confluent Class  
?  
KafkaProducer Class
<!--SR:!2024-07-19,4,270-->

What happens when a broker is brought down for an upgrade and the topic has no replication enabled i.e. 1 copy only.

- Kafka will automatically copy the topic partition on non replicated topic to some other machine
- Topic partition resident to that broker will be unavailable
- Kafka will not let you bring down a broker where a topic partition is hosted with no additional replication
- Upgrade can only be possible when whole Kafka cluster is brought down.  
?  
Topic partition resident to that broker will be unavailable
<!--SR:!2024-07-19,4,270-->

Does KSQL support indexing?:: No

Which property is used to specify brokers for the initial connection in kafka:

- brokers.list
- bootstrap.brokers
- bootstrap.servers
- servers.list
- broker.servers  
?  
bootstrap.servers
<!--SR:!2024-07-19,4,270-->

On our development cluster we have set auto.create.topics.enable to true. We have just created a new topic called “platinumcustomers”. What will be replication factor for this topic

- The replication factor will be 1
- The replication will be configured according to the defaults in server.properties file of the brokers
- The replication factor will be 3
- You cannot create a topic without specifying replication factor  
?  
The replication will be configured according to the defaults in server.properties file of the brokers
<!--SR:!2024-07-19,4,270-->

Kafka platform is not well suited for

- Simplifying data pipelines
- Data visualization and reporting
- Handling streaming data
- Support real time analytics  
?  
Data visualization and reporting
<!--SR:!2024-08-20,14,290-->

Which property is used to specify compression type:

- compression.codec
- compression.type
- compression.format
- compression.technology
- compression.strategy  
?  
compression.type
<!--SR:!2024-07-19,4,270-->

On our development cluster we have set auto.create.topics.enable to true. We have just created a new topic called “goldcustomers”.How many partitions will the topic have

- The number of partitions will be 1
- The number of partitions will be configured according to the defaults in server.properties file of the brokers
- The number of partitions will be 3
- You cannot create a topic without specifying number of partitions.  
?  
The number of partitions will be configured according to the defaults in server.properties file of the brokers
<!--SR:!2024-07-19,4,270-->

Which of the following are not part of the Kafka Ecosystem? Choose Two

- KSQL
- Schema Registry
- Oozie
- Sqoop
- Rest Proxy  
?
- Oozie
- Sqoop
<!--SR:!2024-07-19,4,270-->

Which of the following are invalid compression types to be specified in Kafka, Choose Two:

- snappy
- gzip
- Avro
- lz4
- ORC  
?
- Avro
- ORC
<!--SR:!2024-07-19,4,270-->

Which setting in the Kafka Cluster Configuration decides if automatic creation of topic is allowed or not allowed

- default.replication.factor
- auto.create.topics.enable
- topic.creation.automatic
- bootstrap.servers  
?  
auto.create.topics.enable
<!--SR:!2024-07-19,4,270-->

The non-Java clients are based on the following library which provides consistent APIs & semantics, high performance & high quality clients in various programming languages

- Kafka-console-consumer
- Kafka-console-producer
- Zookeeper
- librdkafka  
?  
librdkafka
<!--SR:!2024-07-19,4,270-->

Which property is used to specify the datatype i.e. Class used to serialize the key for the key in a kafka message:

- key.type
- key.serializer
- datatype.key
- datatype.key.serializer
- data.key.type  
?  
key.serializer
<!--SR:!2024-07-19,4,270-->

While running the following two commands the second command does not go through and throws an error. What could be the root cause of the error:  
`$> kafka-topics --zookeeper zk:port --create --topic sometopic --partitions 6 --replication-factor 3`  
`$> kafka-topics --zookeeper zk:port --alter --topic sometopic --partitions 2`

- Error arrives because in second command we are not mentioning replication factor
- Error arrives because you can increase the number of partitions but cannot reduce it
- There is no error
- Error arrives because you cannot change no. of partitions once decided during creation.  
?  
Error arrives because you can increase the number of partitions but cannot reduce it
<!--SR:!2024-08-21,15,290-->

Are worker processes of Kafka Connect managed by Kafka?:: False

Which property is used to specify the datatype i.e. Class used to serialize the value for the value in a kafka message:

- value.type
- value.serializer
- datatype.value
- datatype.value.serializer
- data.value.type  
?  
value.serializer

While running the following two commands on our development Kafka Cluster with all default settings we see an extremely strange behavior:  
`$> kafka-topics --zookeeper zk:port --delete --topic sometopic`  
`$> kafka-topics --zookeeper zk:port --list`  
After running second command we still see that sometopic is existing and hasn’t been deleted. What could be the potential reason

- Topics cannot be deleted in Kafka
- To delete a topic all the brokers must be brought down
- To delete a topic we should stop all producers and consumers, after running the first command may be a running producer is again trying to access the topic
- After deleting a topic a zookeeper restart is needed only then a topic gets deleted  
?  
To delete a topic we should stop all producers and consumers, after running the first command may be a running producer is again trying to access the topic

Following are the main storage and messaging components of the Kafka cluster

- Brokers
- Producers
- Consumers
- Topics  
?  
Brokers

When writing a Kafka Producer the `compression.type` is set to snappy. What does this imply:

- Data is compressed on the producer, is decompressed as soon as it is written to Kafka
- Data is compressed on the producer, is stored as compressed on kafka and also stays compressed on the consumer. The message can only be decompressed after it is written to some file system like local, HDFS, or Amazon S3
- Data is compressed on the producer, is stored as compressed on kafka broker, decompressed on the Consumer  
?  
Data is compressed on the producer, is stored as compressed on kafka broker, decompressed on the Consumer
<!--SR:!2024-07-19,4,270-->

What is the default size of a log segment i.e. `log.segment.bytes`

- 4 GB
- 10 GB
- 24 GB
- 1 GB  
?  
1 GB
<!--SR:!2024-07-19,4,270-->

True or False: Broker, Producer, and Consumer software works the same on physical machines, VMs, Docker containers i.e. the broker, producer and consumer are agnostic to running on physical machines, VMs and Dockers.:: True

<!--SR:!2024-07-19,4,270-->

True or False: Key serializer must be used even if you do not intend to use keys:: True

<!--SR:!2024-07-19,4,270-->

What is the default period of time for log segment files to be rolled i.e. `log.roll.hours`

- 1 day
- 3 days
- 7 days
- 1 month  
?  
7 days
<!--SR:!2024-07-19,4,270-->

True or False: Keys and Values in a kafka message have to be of the same type:: False

<!--SR:!2024-07-19,4,270-->

True or False: Compression in Kafka is enabled on per topic basis:: False

Client Authentication can be done using which two protocols

- TLS
- SASL
- UDP
- TCP
- HTTP  
?  
TLS  
SASL
<!--SR:!2024-07-19,4,270-->

__________________ is a concept that allows breaking up data, so that there is no need for Consumers to parse the data that they do not want or need to see.

- Producers
- Topics
- Zookeeper
- Kafka Cluster  
?  
Topics
<!--SR:!2024-07-19,4,270-->

True or False: We can have one producer compressing the messages and another one not compressing messages both writing to the same topic:: True

<!--SR:!2024-07-19,4,270-->

Which of the following best describes Kafka Connect?

- Kafka Connect is a framework for streaming data between Apache Kafka and other data systems
- Kafka Connect provides a serving layer for your metadata. It provides a RESTful interface for storing and retrieving Avro schemas. It stores a versioned history of all schemas, provides multiple compatibility settings and allows evolution of schemas
- Kafka Connect is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services.
- Kafka Connect provides a RESTful interface to a Kafka cluster, making it easy to produce and consume messages, view the state of the cluster, and perform administrative actions without using the native Kafka protocol or clients  
?  
Kafka Connect is a framework for streaming data between Apache Kafka and other data systems
<!--SR:!2024-07-19,4,270-->

Following partitioner is used when there is no key specified.

- Hashpartitioner
- Round Robin Partitioner
- Rangepartitioner
- Valuepartitioner  
?  
Round Robin Partitioner
<!--SR:!2024-07-19,4,270-->

In a Kafka Produce program how do you ensure Producer will not wait for any acknowledgement from the server:

- Set acks=0
- Set acks=false
- Set acks=all
- Set acks=1
- Set acks=true  
?  
Set acks=0
<!--SR:!2024-08-20,14,290-->

Which of the following is not a characteristic or benefit of Kafka Connect?

- Off-the-shelf, tested Connectors for common data sources are available
- Features fault tolerance and automatic load balancing when running in distributed mode
- Just write Plain Old Java code for Kafka Connect
- Pluggable/Extensible by developers  
?  
Just write Plain Old Java code for Kafka Connect
<!--SR:!2024-07-19,4,270-->

Following partitioner is the default partitioner when the key is specified.

- Hashpartitioner
- Round Robin Partitioner
- Rangepartitioner
- Valuepartitioner  
?  
Hashpartitioner

In a Kafka Produce program how do you ensure Producer will wait until the leader has written the record to its local log:

- Set acks=0
- Set acks=false
- Set acks=all
- Set acks=1
- Set acks=true  
?  
Set acks=1
<!--SR:!2024-07-19,4,270-->

Which component of Kafka Connect would be considered capable of reading data from external data stores such as databases

- Kafka Connector Sources
- Kafka Connector Sinks
- Kafka Topic
- Kafka Connector Cluster
- Zookeeper  
?  
Kafka Connector Sources
<!--SR:!2024-07-19,4,270-->

True or False: Hashpartitioner will place all messages with the same value on a single partition.:: False

In a Kafka Produce program how do you ensure Producer will wait until all in-sync replicas have acknowledged receipt of the record:

- Set acks=0
- Set acks=false
- Set acks=all
- Set acks=1
- Set acks=true  
?  
Set acks=all
<!--SR:!2024-07-19,4,270-->

Which component of Kafka Connect would be considered capable of pulling data from a Kafka topic and write it to an external application such as HDFS

- Kafka Connector Sources
- Kafka Connector Sinks
- Kafka Topic
- Kafka Connector Cluster
- Zookeeper  
?  
Kafka Connector Sinks

REST server allows users to send Producer and Consumer requests to the cluster using which protocol

- UDP
- HTTP
- TCP
- FTP  
?  
HTTP
<!--SR:!2024-07-19,4,270-->

What is the best practice to handle transient failures if acks is a value other than 0:

- Set retries to non-zero value
- Set retries to zero
- Don’t set retries value  
?  
Set retries to non-zero value
<!--SR:!2024-07-19,4,270-->

Which component related to Kafka Connect is a repository for Connectors, Transformations and convertors for Kafka Connect

- Kafka Connector Sources
- Confluent Hub
- Kafka Topic
- Kafka Connector Cluster
- Zookeeper  
?  
Confluent Hub

The following is intended to allow customers to add Kafka to their IoT architecture to enable stream processing?

- UDP
- MQTT
- TCP
- FTP  
?  
MQTT

What is the difference between KafkaProducer class and ProducerRecord class?

- They both are the same, ProducerRecord is old class and KafkaProducer is the new one
- They both are the same, ProducerRecord is the new class and KafkaProducer is the old one
- KafkaProducer is the class that handles Producer and ProducerRecord is the class that handles messages. KafkaProducer’s send method takes object of ProducerRecord as an input
- KafkaProducer is the class that handles messages and ProducerRecord is the class that handles Producer. ProducerRecord’s send method takes object of KafkaProducers class as an input  
?  
KafkaProducer is the class that handles Producer and ProducerRecord is the class that handles messages. KafkaProducer’s send method takes object of ProducerRecord as an input
<!--SR:!2024-07-19,4,270-->

Where does Kafka Connect run

- Kafka Brokers
- Own dedicated cluster
- Kafka Producers
- Kafka Consumers
- Zookeeper  
?  
Own dedicated cluster

True or False: Retention policies for messages can be configured on a topic level:: True

<!--SR:!2024-08-22,16,290-->

What should be the configurations looking like for High Throughput for batching:

- large batch.size and large linger.ms
- large batch.size and small linger.ms
- small batch.size and large linger.ms
- small batch.size and small linger.ms  
?  
large batch.size and large linger.ms
<!--SR:!2024-07-19,4,270-->

What does Offset mean or correspond to for the Kafka Connector Source for a file input?

- timestamp
- Position in the file
- Sequence id
- File name  
?  
Position in the file
<!--SR:!2024-07-19,4,270-->

Consumer Offset are stored in

- \_\_consumer_offsets topic
- Zookeeper
- /tmp directory on brokers
- consumers  
?  
\_\_consumer_offsets topic

What should be the configurations looking like for Low Latency for batching:

- large batch.size and large linger.ms
- large batch.size and small linger.ms
- small batch.size and large linger.ms
- small batch.size and small linger.ms  
?  
small batch.size and small linger.ms
<!--SR:!2024-07-19,4,270-->

Which of the below components of Kafka support Exactly Once Semantic? (More than one option is correct)

- Schema Registry
- Kafka SQL
- Auto Databalancer
- Kafka Streams  
?  
Kafka SQL  
Kafka Streams
<!--SR:!2024-07-19,4,270-->

How do we configure rack awareness in Kafka?

- Set rack.awareness to true
- Set broker.rack to rack id
- Set broker.rack to true
- Set rack.available to true  
?  
Set broker.rack to rack id
<!--SR:!2024-07-19,4,270-->

How many modes exist in Kafka Connect? (Choose 2)

- Distributed Mode
- Psuedo Mode
- Local Mode
- Standalone Mode  
?  
Distributed Mode  
Standalone Mode

How does Replicator solve the problem of infinite replication loop?

- It uses a message body to record origin cluster
- It uses another topic to keep track of the origin cluster
- It uses a partition to store origin cluster
- It uses message header to record origin cluster  
?  
It uses another topic to keep track of the origin cluster
<!--SR:!2024-07-19,4,270-->

How can we ensure that the load balancer of Rest proxy binds a User’s session to a specific instance?

- Use 1 Rest proxy at a time
- Use Sticky Load balancer
- Use F5 Load Balancer
- None of the above  
?  
Use Sticky Load balancer
<!--SR:!2024-07-19,4,270-->

Which is considered as the best format to work with Kafka?

- CSV
- Avro
- Parquet
- JSON  
?  
Avro
<!--SR:!2024-08-22,16,290-->

Which factors are considered while deciding the task.max for Kafka connector? (Choose any three)

- Number of Topics
- Number of Partitions
- Desired Throughput/Throughput per task
- Machine * No of cores per machine  
?
- Number of Partitions
- Desired Throughput/Throughput per task
- Machine * No of cores per machine
<!--SR:!2024-07-19,4,270-->

What is the default size of a message in Kafka?

- 100 KB
- I0 KB
- 1 MB
- 10 MB  
?  
1 MB

Which of the below options are recommended for Zookeeper?

- Allocate dedicated high core machines for processing data
- Allocate memory-intensive machines for caching data
- Run more than 9 Zookeepers
- Dedicate a separate SATA or SSD for its transaction logs  
?  
Dedicate a separate SATA or SSD for its transaction logs

How many max partitions are recommended in a broker?

- 500
- 1000
- 2000
- 4000  
?  
4000
<!--SR:!2024-07-19,4,270-->

How much JVM memory is sufficient for Broker JVM in a typical deployment?

- 1 GB
- 4 GB
- 20 GB
- 100 GB  
?  
4 GB
<!--SR:!2024-08-19,13,290-->

Which filesystem is recommended for deploying Kafka clusters?

- XFS
- NTFS
- FAT32
- EXT3  
?  
XFS
<!--SR:!2024-07-19,4,270-->

Which component is responsible for checking the liveness of Consumers?

- Group Leader
- Consumer Group
- Group Coordinator
- Zookeeper  
?  
Group Coordinator
<!--SR:!2024-07-19,4,270-->

Where does Kafka store Consumer offsets?

- Zookeeper
- Controller
- User Topic
- System Topic  
?  
System Topic
