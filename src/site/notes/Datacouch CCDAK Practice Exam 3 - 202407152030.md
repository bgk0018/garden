---
{"dg-publish":true,"permalink":"/datacouch-ccdak-practice-exam-3-202407152030/","tags":["📖","♣️/kafka"],"created":"2024-07-14T12:08:16.070-05:00","updated":"2024-07-15T22:44:36.053-05:00"}
---

# Datacouch CCDAK Practice Exam 3

True or False: When consuming messages from Avro based topic, there are special methods needed to communicate with Schema Registry as KafkaAvroSerializer and KafkaAvroDeserializer do not have functionality to do so:: False
<!--SR:!2024-07-19,4,270-->


Which of the following defines flatMapValues operation correctly from a Streaming Application perspective?
-  Creates a new KStream by transforming the value of each element in the current stream into zero or more different elements in the new stream
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Creates a new KStream by transforming the value of each element in the current stream into zero or more different elements in the new stream
<!--SR:!2024-07-19,4,270-->


Which of the following is the correct command for creating a producer to the topic confluent ?
-  kafka-topics --producer --zookeeper localhost:2181 --partitions 2 --topic confluent
-  kafka-console-producer --zookeeper localhost:9092 --topic confluent
-  kafka-console-producer --broker-list localhost:9092 --topic confluent
?
kafka-console-producer --broker-list localhost:9092 --topic confluent
<!--SR:!2024-07-19,4,270-->


True or False: Message Schema is stored in Schema Registry and the schema registry is a lookup that is used by the consumer for each and every message.:: False


Which of the following defines reduce operation correctly from a Streaming Application perspective?
-  Combines values of the stream using a supplied Reducer into a new, everupdating KTable
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Combines values of the stream using a supplied Reducer into a new, ever updating KTable
<!--SR:!2024-07-19,4,270-->


Which of the following is the correct command for creating a consumer to the topic confluent?
-  kafka-topics --consumer --zookeeper localhost:2181 --partitions 2 --topic confluent
-  kafka-console-consumer --zookeeper localhost:9092 --topic confluent
-  kafka-console-consumer --bootstrap-server localhost:9092 --topic confluent  
?  
kafka-console-consumer --bootstrap-server localhost:9092 --topic confluent


Which of the following snippet will achieve the goal of subscribing iphone, ipad and ipod topics simultaneously?
-  Simultaneous subscription is not a possibility in Kafka
-  consumer.subscribePattern(“topic.i*”)
-  consumer.subscribe(Arrays.asList(“topic.iphone”, “topic.ipad”, "topic.ipod"));
-  consumer.subscribe(Arrays.asList(“topic.iphone”);
-  consumer.subscribe(Arrays.asList(“topic.ipad”);
-  consumer.subscribe(Arrays.asList(“topic.ipod”);
?
consumer.subscribe(Arrays.asList(“topic.iphone”, “topic.ipad”, "topic.ipod"));
<!--SR:!2024-07-19,4,270-->


Which method is used to just write streams to a topic in a Kafka Streams Application:
-  to()
-  through()
-  produce()
-  consume()
-  subscribe()  
?  
to()


If a user creates a topic confluent with a replication factor of 4, what does that imply.
-  Each partition will live on 4 different brokers
-  Each partition will live on 2 different brokers
-  4 replicas of the same data will live on 1 broker
-  Each partition will live on 8 different brokers  
?  
Each partition will live on 4 different brokers


A consumer starts and has auto.offset.reset=latest, and the topic partition currently has data for offsets going from 550 to 800. The consumer group has committed the offset 600 for the topic before. Where will the consumer read from?
-  Exception is thrown
-  550
-  800
-  600
?
600
<!--SR:!2024-07-19,4,270-->


Which class is instantiated to start processing a stream in the Kafka Streams Application:
-  Producer Class
-  KafkaStreams Class
-  Kafka Class
-  ConfluentProducer Class
-  Confluent Class
?
KafkaStreams Class
<!--SR:!2024-07-19,4,270-->


True or False: Consumer Offset is stored in Zookeeper:: False
<!--SR:!2024-07-19,4,270-->


Schema Registry supports which of the following client protocol?
-  UDP
-  HTTP
-  TCP
-  FTP
?
HTTP
<!--SR:!2024-07-19,4,270-->


Which method is used to start the streaming data in a Kafka Streams Application:
-  start()
-  stream()
-  begin()
-  consume
-  subscribe
?
start()
<!--SR:!2024-07-16,1,230-->


A topic receives new airline bookings on a travel site. Four applications want to process all the new bookings independently - accounts team, booking team, email team, and recommendations team. The topic has 6 partitions, what would be the ideal way to structure it?
-  Create four consumer groups for four applications with 6 consumers in each
-  Create 24 consumers in the same group with 6 consumers for each application
-  Create four consumers with each consumer consuming entire data
?
Create four consumer groups for four applications with 6 consumers in each
<!--SR:!2024-07-19,4,270-->


When writing a KafkaProducer, which of the following property is mandatory?
-  key
-  groupid
-  value
-  Zookeeper-server
-  bootstrap.servers  
?  
bootstrap.servers


What is the default value for processing.guarantee in Kafka Streams:
-  at_least_once
-  exactly_once
-  only_once
-  More_than_once
-  exactly_thrice  
?  
at_least_once


True or False: ACLs is stored in Zookeeper:: True
<!--SR:!2024-07-19,4,270-->


Which field in Avro schema denotes the package name which you will import in your code
-  doc
-  name
-  type
-  fields
-  namespace
?
namespace
<!--SR:!2024-07-19,4,270-->


For Production workloads which is a preferred way to run KSQL:
-  Headless
-  Interactive
?
Headless
<!--SR:!2024-07-19,4,270-->


True or False: In spite of just starting a single consumer Kafka still creates a consumer group with a random Id:: True


Which setting specifies the minimum number of replicas that should be in-sync for a certain partition to be available for new writes
-  acks
-  replication
-  min.insync.replicas
-  bootstrap.serves
?
min.insync.replicas
<!--SR:!2024-07-19,4,270-->


Which of the following defines TUMBLING operation correctly from a KSQL perspective?
-  fixed-sized, non-overlapping windows based on the record's timestamps
-  Fixed-sized, (possibly) overlapping windows based on the record’s timestamps
-  Sessions with a period of activity and gaps in between
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
fixed-sized, non-overlapping windows based on the record's timestamps
<!--SR:!2024-07-19,4,270-->


With 3 zookeeper servers, how many failures can a zookeeper ensemble withstand
-  Seven
-  One
-  Three
-  Zero
?
Zero
<!--SR:!2024-07-19,4,270-->


What is the return type of the object when producer.send() is called?
-  ANY
-  UNIT
-  Object of class Future\<RecordMetadata\>
-  Object of class Future\<ResponseCode\>
-  Exception
?
Object of class Future\<RecordMetadata\>
<!--SR:!2024-07-19,4,270-->


Which of the following defines HOPPING operation correctly from a KSQL perspective?
-  Fixed-sized, non-overlapping windows based on the record's timestamps
-  Fixed-sized, (possibly) overlapping windows based on the record’s timestamps
-  Sessions with a period of activity and gaps in between
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Fixed-sized, (possibly) overlapping windows based on the record’s timestamps
<!--SR:!2024-07-19,4,270-->


With 5 zookeeper servers, how many failures can a zookeeper ensemble withstand
-  Seven
-  One
-  Three
-  Two
?
 Two
<!--SR:!2024-07-19,4,270-->

True or False: Schema Registry runs as a separate JVM process:: True
<!--SR:!2024-07-19,4,270-->


True or False: KSQL is ANSI SQL compliant?:: False
<!--SR:!2024-07-19,4,270-->


An application was sending messages to a topic partition with a replication factor of 3 by connecting to the broker that had partition leader. If the broker in action i.e. one which is hosting the leader goes down, what happens?
-  Kafka will gracefully elect a new leader and producer starts publishing to the new leader topic.
-  The producer starts throwing errors and exits
-  The kafka cluster goes down
?
Kafka will gracefully elect a new leader and producer starts publishing to the new leader topic.
<!--SR:!2024-07-19,4,270-->


Removing a field that does not have a default value in an Avro schema is which of the following schema evolution
-  Backward
-  Forward
-  Full
-  None
-  Its an error scenario  
?  
Backward


You want to sink data from a Kafka topic to Google Cloud Storage bucket using Kafka Connect. There are 40 brokers in the cluster, the topic has 10 partitions with replication factor of 3. How many tasks should we ideally configure for Google Cloud storage bucket?
-  20
-  40
-  10
-  2  
?  
10


What would be the implications of increasing the number of partitions for a topic
-  New messages may head to different partitions
-  It is not possible to change the number of partitions once topic is created
-  New partitions will be idle till you restart producer
-  New partitions get more data  
?  
New messages may head to different partitions


Which data format isn't natively available with the Confluent REST Proxy?
-  protobuf
-  json
-  binary
-  avro
-  None of above
?
None of above
<!--SR:!2024-07-19,4,270-->


Which of the following defines `config.storage.topic` correctly from Kafka Connect perspective?
-  topic where connector and task configuration data are stored
-  topic where connector and task configuration offsets are stored
-  topic where connector and task configuration status updates are stored.
-  topic where ACLs are stored
?
topic where connector and task configuration data are stored
<!--SR:!2024-07-19,4,270-->


Which of the following command line interface CLI is used to consume from a particular topic?
-  kafka-console-consumer
-  kafka-consumer-groups
-  Kafka-console  
?  
kafka-console-consumer


With all the default Kafka settings a Producer tries to send a message with a payload of 4 MB. What will be the outcome?
-  MessageSizeTooLarge exception is thrown
-  4 MB message is broken into 4 messages of 1 MB each
-  In spite of being large message gets transported
-  Kafka cluster crashes
?
MessageSizeTooLarge exception is thrown
<!--SR:!2024-07-19,4,270-->


Which of the following defines `offset.storage.topic` correctly from Kafka Connect perspective?
-  topic where connector and task configuration data are stored
-  topic where connector and task configuration offsets are stored
-  topic where connector and task configuration status updates are stored
-  Topic where ACLs are stored
?
topic where connector and task configuration offsets are stored
<!--SR:!2024-07-19,4,270-->


Which of the following command line interface CLI is used to produce to a particular topic?
-  kafka-console-producer
-  kafka-producer
-  Kafka-console
?
kafka-console-producer
<!--SR:!2024-07-19,4,270-->


True or False: To send binary data through REST Proxy, the Producer needs to encode the binary data to base 64:: True
<!--SR:!2024-07-19,4,270-->


Which of the following defines status.storage.topic correctly from Kafka Connect perspective?
-  topic where connector and task configuration data are stored
-  topic where connector and task configuration offsets are stored
-  topic where connector and task configuration status updates are stored
-  Topic where ACLs are stored  
?  
topic where connector and task configuration status updates are stored


The purpose of broker-list in the kafka-console-producer command is?
-  To create initial connection with the cluster
-  To write to only the nodes that are mentioned in the broker-list
-  Broker-list is actually not needed when producing messages to kafka
-  To black list the broker-list nodes and write to other nodes  
?  
To create initial connection with the cluster


True or False: In a Avro schema, adding an option to enum is a full schema evolution:: False
<!--SR:!2024-07-19,4,270-->


Which of the following are internal Kafka-Connect topics? Choose Two
-  connect-jars
-  connect-offsets
-  connect-status
-  connect-schema
?
-  connect-offsets
-  connect-status
<!--SR:!2024-07-19,4,270-->


The rationale behind having a replication factor of 3 for partitions in general is:
-  To be able to bring one node down for maintenance and still have failover
-  Three is an odd number and is used for election when reading the data for its correctness i.e. a kafka message is correct only if two replicas confirm
-  Three is just random, people in the real world prefer replication factor of 2
?
To be able to bring one node down for maintenance and still have failover
<!--SR:!2024-07-19,4,270-->


True or False: The only way to producer messages are flushed to the brokers is based on batching configuration parameters and there is no manual way to flush the messages to the broker:: False
<!--SR:!2024-07-16,1,230-->


What is the difference between KStream and KTable
-  They are similar and used interchangeably
-  KStreams treats records as a record stream and treats new records as something that will be added if keys are same, KTable treats records as changelog system and treats new records with same keys as updates
-  KStreams treats records as changelog system and treats new records with same keys as updates, KTable treats records as a record stream and treats new records as something that will be added if keys are same
-  KTable is a newer API and the older one is KStream
?
KStreams treats records as a record stream and treats new records as something that will be added if keys are same, KTable treats records as changelog system and treats new records with same keys as updates
<!--SR:!2024-07-19,4,270-->


True or False: Each broker in the kafka cluster has a unique broker id:: True
<!--SR:!2024-07-19,4,270-->


The default value of tasks.max in kafka connect is:
-  1
-  3
-  10
-  5
?
1
<!--SR:!2024-07-19,4,270-->


--from-beginning option gets the data from:
-  Since the beginning that Kafka topic was created
-  From beginning but only data that is within retention period
-  Since the beginning of the day
-  Since the beginning of the month
-  Since the beginning of the year
?
From beginning but only data that is within retention period
<!--SR:!2024-07-19,4,270-->


Which method is invoked when message send is acknowledged :
-  onCompletion(RecordMetadata metadata, java.lang.Exception exception)
-  onSuccess(RecordMetadata metadata, java.lang.Exception exception)
-  onCompletion(Metadata metadata, java.lang.Exception exception)
-  onSuccess(Metadata metadata, java.lang.Exception exception)
?
onCompletion(RecordMetadata metadata, java.lang.Exception exception)
<!--SR:!2024-07-19,4,270-->


What does RecordMetadata contain? (more than one option can be correct):
-  Offset
-  Partition
-  Topic
-  None of the above
?
-  Offset
-  Partition
-  Topic
<!--SR:!2024-07-19,4,270-->


Which are correct signatures of send method(more than one option can be correct):
-  producer.send(record)
-  producer.send(record, callback)
-  producer.send(record, exception)
-  producer.send(record, callback, exception)
?
-  producer.send(record)
-  producer.send(record, callback)
<!--SR:!2024-07-19,4,270-->


Consumer sends Heartbeat to :
-  Group Leader
-  Zookeeper
-  All Brokers
-  Group Coordinator  
?  
Group Coordinator


Long GC Pauses on Broker side can lead to :
-  Broker can be considered dead by Zookeeper
-  Broker can be considered dead by all Producers/Clients
-  Broker can be considered down by Group Leader
-  None of the above
?
Broker can be considered dead by Zookeeper
<!--SR:!2024-07-19,4,270-->


In order to achieve Zero data loss in Kafka, what should be taken care :
-  Commit offsets in onPartitionsChanged method in ConsumerRebalanceListener
-  Commit offsets in onPartitionsRemoved method in ConsumerRebalanceListener
-  Commit offsets in onPartitionsRevoked method in ConsumerRebalanceListener
-  None of the above options
?
Commit offsets in onPartitionsRevoked method in ConsumerRebalanceListener
<!--SR:!2024-07-19,4,270-->


What is the main advantage of storing offsets outside Kafka in a transactional store :
-  For Scaling Kafka
-  For Achieving Fault Tolerance
-  For Achieving Exactly Once Semantic
-  None of the above
?
None of the above
<!--SR:!2024-07-19,4,270-->


Where does Schema Registry stores its schemas?
-  Zookeeper
-  \_\_registry topic
-  \_\_schemas topic
-  \_\_consumer_offsets topic
?
\_\_schemas topic
<!--SR:!2024-07-19,4,270-->


True/False: Rocks DB is used in Kafka Streams in Stateful Streaming Applications.:: True
<!--SR:!2024-07-19,4,270-->


Where does KSQL store its data?
-  On KSQL Cluster
-  On Hadoop Cluster
-  On Local FileSystem
-  On Kafka Cluster  
?  
On Kafka Cluster


Which component is responsible for checking liveness of consumer?
-  Group Leader
-  Consumer Group
-  Group Coordinator
-  Zookeeper
?
Group Coordinator
<!--SR:!2024-07-19,4,270-->


Which of the below components of Kafka doesn’t require cluster installation?
-  Kafka Core
-  Kafka SQL
-  Kafka Connect
-  Kafka Streams  
?  
Kafka Streams


What is the difference between GroupByKey and GroupBy API in KStreams Library? (More than one option is correct)
-  GroupBy causes always repartition
-  GroupByKey causes always repartition
-  GroupBy may cause repartition
-  GroupByKey may cause repartition
?
- GroupBy causes always repartition
-  GroupByKey may cause repartition
<!--SR:!2024-07-19,4,270-->


What is the problem with Stretched Cluster?
-  High Latency
-  Low Throughput
-  Additional Hardware
-  None of the above
?
High Latency
<!--SR:!2024-07-19,4,270-->


What is the default Quota given to each client?
-  100 MB/sec
-  1 GB/sec
-  100 GB/sec
-  Infinite  
?  
Infinite


Which of the below metrics indicates Consumer lag?
-  Records-lag-min
-  Records-lag-max
-  Consumer-lag-min
-  Consumer-lag-max
?
Records-lag-max
<!--SR:!2024-07-19,4,270-->


What is the relationship between topic, partition and segment?
-  One topic can have multiple partitions and single segments.
-  One topic can have only one partition and one segment.
-  One topic can have multiple partitions and multiple segments.
-  One topic can have only one partition and multiple segments.
?
One topic can have multiple partitions and multiple segments.
<!--SR:!2024-07-19,4,270-->


Which statement is/are true?
-  Kafkacat is a command-line utility.
-  Kafkacat is supported by a confluent platform.
-  Kafkacat is an alternative to kafka-console-producer and kafka-console-consumer.
-  Kafkacat is an API framework.
?
Kafkacat is a command-line utility.
<!--SR:!2024-07-19,4,270-->


Kafka is designed to process the messages in real-time, however we can also achieve batch processing in Kafka by tuning in a few parameters. Also there are better performances for batching in , what could be the best reason for the same?
-  Fast processing of ProducerRequest
-  Reduced RPCs
-  Increased RPCs
-  Compression of messages
?
Reduced RPCs
<!--SR:!2024-07-19,4,270-->


When does a message is marked as committed by the leader?
-  when all the replicas are updated upto high water mark.
-  when the leader and at least one follower is/are updated upto high water mark.
-  when only the leader is updated upto high water mark.
-  when all the followers are updated upto high water mark.
?
when all the replicas are updated upto high water mark.
<!--SR:!2024-07-19,4,270-->


What does delivery.timeout.ms define in Kafka?
-  Timeout after which producer would retry.
-  Maximum time client will wait for the response.
-  Maximum time to wait for success or failure after send request.
-  Amount of time to wait before attempting retry.
?
Maximum time to wait for success or failure after send request.
<!--SR:!2024-07-19,4,270-->


The snapshot files are used while using ____________.
-  All type of Producer
-  Transactional Producer
-  Idempotent Producer
-  None of the above
?
Idempotent Producer
<!--SR:!2024-07-19,4,270-->

## References


## Flashcards