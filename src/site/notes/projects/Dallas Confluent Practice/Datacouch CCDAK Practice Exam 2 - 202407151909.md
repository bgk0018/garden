---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/datacouch-ccdak-practice-exam-2-202407151909/","tags":["📖","♣️/kafka"],"created":"2024-07-14T11:23:09.820-05:00","updated":"2024-11-10T12:31:52.000-06:00"}
---

# Datacouch CCDAK Practice Exam 2


What does Offset mean or correspond to for the Kafka Connector Source for a database input Choose Two
-  Timestamp
-  Position in the file
-  Sequence id
-  File name
-  Broker Id  
?  
Sequence id


Topic configurations and ACLs are stored in
-  \_\_consumer_offsets topic
-  Zookeeper
-  /tmp directory on brokers
-  consumers
?
Zookeeper
<!--SR:!2024-08-23,17,290-->


How do you ensure message ordering if retries>0:
-  Set max.in.flight.requests.per.connection=1
-  Set max.in.flight.requests.per.connection>1
-  Set max.in.flight.requests.per.connection<1
-  Set max.in.flight.requests.per.connection=0
?
Set max.in.flight.requests.per.connection=1
<!--SR:!2024-08-21,15,290-->


Where does Kafka Connector for JDBC {in a distributed mode} source track its offset?
-  Special Kafka Topic
-  Zookeeper
-  Kafka Broker
-  HDFS File
-  Local File
?
Special Kafka Topic
<!--SR:!2024-07-19,4,270-->


The relationship of Broker to Partition with replication factor of 3 is
-  1:1
-  N:N
-  N:1
-  1:N
?
N:N
<!--SR:!2024-07-19,4,270-->


In a KafkaProducer program our send() was configured with a callback onCompletion. The send was called and the callback parameters has RecordMetadata object that was null. What does this tell us about send method:
-  Object metadata being null means there was an error during send
-  Object metadata being null means the transfer was successful
-  Object metadata being null is not enough information to determine if transfer was successful or not
?
Object metadata being null means there was an error during send
<!--SR:!2024-07-19,4,270-->


Where does Kafka Connector for HDFS Sink track its offset
-  Special Kafka Topic
-  Zookeeper
-  Kafka Broker
-  HDFS File
?
HDFS File
<!--SR:!2024-07-19,4,270-->


The relationship of Producer to Topic is
-  1:1
-  N:N
-  N:1
-  1:N  
?  
N:N


True or False: Key deserializer must be used even if you do not intend to use keys:: True


Where does Kafka Connector for Filestream Source track its offset?
-  Special Kafka Topic
-  Zookeeper
-  Kafka Broker
-  HDFS File
-  Local File  
?  
Local File


Group memberships for a consumer group are managed by
-  Zookeeper
-  Controller
-  Producer
-  Consumers
-  Group Coordinator
?
Group Coordinator
<!--SR:!2024-07-19,4,270-->


AVRO schemas are represented in what format
-  JSON
-  XML
-  YAML
-  Plain Text
-  CSV
?
JSON
<!--SR:!2024-07-19,4,270-->


Which class is used to create a builder object in the Kafka Streams Application:
-  Producer Class
-  StreamsBuilder Class
-  Kafka Class
-  ConfluentProducer Class
-  Comfluent Class
?
StreamsBuilder Class
<!--SR:!2024-07-19,4,270-->


Number of Group Leaders in a single consumer group with 5 consumers is
-  Two
-  One
-  Three
-  Five
-  Zero
?
One
<!--SR:!2024-07-19,4,270-->


Which component in Kafka handles schema evolution
-  Schema Registry
-  Brokers
-  Producers
-  Consumers
-  Rest Proxy
?
Schema Registry
<!--SR:!2024-07-19,4,270-->


Which of the following Kafka Streams operators are stateless? (Choose 3)
-  map
-  reduce
-  aggregate
-  count
-  filter
-  mapvalues  
?  
map, filter, mapvalues


With a Range Assignment strategy in place, what will the final outcome look like with given inputs: Topics: foo and bar Partitions: (foo-0 and foo-1) & (bar-0 and bar-1) Consumers: C1, C2, C3
-  c1:{foo-0,bar-0},c2:{foo-1,bar-1},c3{}
-  c1:{foo-0,bar-1},c2:{foo-1},c3{bar-0}
-  Invalid case
-  c1:{foo-0,foo-1},c2:{bar-0,bar-1},c3{}
?
c1:{foo-0,bar-0},c2:{foo-1,bar-1},c3{}
<!--SR:!2024-07-19,4,270-->


Consumer is reading data with new schema and data having old Schema is already stored in Kafka. This scenario is an example of which kind of compatibility Schema is written with the following fields: { "name": "suit", "type": "string"}, { "name": "card", "type": "string"} Consumer is expecting the following schema and assumes default for omitted size field { "name": "suit", "type": "string"}, { "name": "card", "type": "string"}, { "name": "size", "type": "string", "default": "" }
-  Backward
-  Forward
-  Full
-  None
-  Its an error Scenario
?
Forward
<!--SR:!2024-07-19,4,270-->


Which of the following defines filter operation correctly from a Streaming Application perspective?
-  Creates a new KStream containing only records from the previous KStream which meet some specified criteria
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Creates a new KStream containing only records from the previous KStream which meet some specified criteria
<!--SR:!2024-07-19,4,270-->


With a Round Robin strategy in place, what will the final outcome look like with given inputs: Topics: foo and bar Partitions: (foo-0 and foo-1) & (bar-0 and bar-1) Consumers: C1, C2, C3
-  c1:{foo-0,bar-0},c2:{foo-1,bar-1},c3{}
-  c1:{foo-1,bar-0},c2:{foo-1},c3{bar-0}
-  Invalid case
-  c1:{foo-0,bar-1},c2:{foo-1},c3{bar-0}  
?  
c1:{foo-0,bar-1},c2:{foo-1},c3{bar-0}


Producers have started to produce new data with new schema and Consumers are still reading data with old schema. The scenario is an example of which kind of compatibility Schema is written with the following fields: { "name": "suit", "type": "string"}, { "name": "card", "type": "string"} Consumer is expecting the following schema and ignores the additional card field { "name": "suit", "type": "string"},
-  Backward
-  Forward
-  Full
-  None
-  Its an error scenario  
?  
Forward


Which of the following defines map operation correctly from a Streaming Application perspective?
-  Creates a new KStream containing only records from the previous KStreamwhich meet some specified criteria
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Creates a new KStream by transforming each element in the current stream into a different element in the new stream
<!--SR:!2024-07-19,4,270-->


We have a topic with 5 partitions and we have 7 consumers. How many consumers will end up receiving the data
-  Seven
-  One
-  Three
-  Five
-  Zero
?
Five
<!--SR:!2024-07-19,4,270-->


Schema registry information is stored in
-  \_\_schemas topic
-  Zookeeper
-  /tmp directory on brokers
-  Consumers
?
\_\_schemas topic
<!--SR:!2024-07-19,4,270-->


Which of the following defines mapValues operation correctly from a Streaming Application perspective?
-  Creates a new KStream containing only records from the previous KStreamwhich meet some specified criteria
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
<!--SR:!2024-07-19,4,270-->


We have just installed Confluent Kafka and all the settings are default. After installation we issue the following command: # kafka-console-producer --broker-list :9092 --topic confluent >hello world What will happen once we press enter?
-  We get error and are thrown out of console
-  Topic confluent gets created and message is pushed to it
-  We get Topic does not exist error  
?  
Topic confluent gets created and message is pushed to it


Incompatibility with schema is detected and reported by?
-  The Kafka Broker
-  The Confluent Schema Registry
-  The Kafka Producer itself
-  Zookeeper
?
The Confluent Schema Registry
<!--SR:!2024-07-19,4,270-->


Which of the following defines flatMap operation correctly from a Streaming Application perspective?
-  Creates a new KStream containing only records from the previous KStreamwhich meet some specified criteria
-  Creates a new KStream by transforming each element in the current stream into a different element in the new stream
-  Creates a new KStream by transforming the value of each element in the current stream into a different element in the new stream
-  Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
?
Takes one record and produces zero, one, or more records. You can modify the record keys and values, including their types.
<!--SR:!2024-07-19,4,270-->


Which of the following is the correct command for creating a topic confluent with 2 partitions?
-  kafka-topics --create --zookeeper localhost:2181 --partitions 2 --topic confluent
-  kafka-topics --create --zookeeper localhost:9092 --partitions 2 --topic confluent
-  kafka-topics-create --zookeeper localhost:2181 --partitions 2 --topic confluent
?
kafka-topics --create --zookeeper localhost:2181 --partitions 2 --topic confluent
<!--SR:!2024-07-19,4,270-->


What is the Zero copy concept?
-  It is computer operation in which CPU doesn’t have to copy data from one memory location to another
-  It is Kafka operation in which partition is not copied from one machine to another
-  It is Java operation in which Garbage collection is done without copy process
-  None of these
?
It is computer operation in which CPU doesn’t have to copy data from one memory location to another
<!--SR:!2024-07-19,4,270-->


Are worker processes of Kafka Connect managed by Kafka Brokers?:: False
<!--SR:!2024-07-19,4,270-->


What is the best use case for KTable datatype in KStreams?
-  Maintaining Account Statement for each customer
-  Maintaining Account Balance for each customer
-  Maintaining Job Change History of a Job
-  None of the above
?
Maintaining Account Balance for each customer
<!--SR:!2024-07-19,4,270-->


What is Transactional Coordinator in Kafka?
-  A special Broker
-  A special module on any Broker
-  A thread running on any Broker
-  A thread running on certain Broker  
?  
A special module on any Broker


What is a connector in Kafka Connect?
-  JVM
-  Daemon
-  Jar
-  War
?
Jar
<!--SR:!2024-07-19,4,270-->


How to implement authentication in Kafka?
-  Using Sentry
-  Using Ranger
-  Using Zookeeper
-  Using Kerberos  
?  
Using Kerberos


Which of the below is not supported by Kafka?
-  Data in motion encryption
-  Data at rest encryption
-  LUKS encryption
-  Kerberos with LDAP authentication
?
Data at rest encryption
<!--SR:!2024-07-19,4,270-->


What’s the default path of log4j.properties?
-  /usr/lib/kafka
-  /var/log/kafka
-  /var/lib/kafka
-  /etc/kafka
?
 /etc/kafka
<!--SR:!2024-07-19,4,270-->

Authorization in Kafka is based on how many tuples match?
-  3
-  2
-  4
-  5  
?  
3


How do we identify brokers in a Kafka cluster?
-  Host Name
-  Broker Id
-  IP Address
-  Unique JVM Id
?
Broker Id
<!--SR:!2024-07-19,4,270-->


How to compute the number of Partitions?
-  max(t/p,t/c)
-  max(p/t,t/c)
-  max(t/p,c/t)
-  max(p/t,c/t)
?
max(t/p,t/c)
<!--SR:!2024-07-19,4,270-->


Which metrics are critical for understanding Broker performance?
-  LeaderCount
-  FollowCount
-  PartitionCount
-  ISRCount
?
LeaderCount
<!--SR:!2024-07-19,4,270-->


What is a valid unit of quota in Kafka?
-  Requests/sec
-  Bytes/s
-  Messages/s
-  None of the above  
?  
Bytes/s


How to configure Client quota?
-  Use kafka-acls command
-  Use kafka-configs command
-  Use kafka-topics command
-  Use kafka-admin command
?
Use kafka-configs command
<!--SR:!2024-07-19,4,270-->


The following concept allows Kafka to transfer data from a local file channel to a remote socket channel directly without going through the application space.
-  Consumer Groups
-  Partitions
-  Zero Copy Data Transfer
-  Java Heap based cache
?
Zero Copy Data Transfer
<!--SR:!2024-07-19,4,270-->


The default value of auto.commit.interval.ms is:
-  5 seconds
-  10 seconds
-  15 seconds
-  30 seconds
-  60 seconds
?
5 seconds
<!--SR:!2024-07-19,4,270-->


Which of the following are run modes for Kafka Connect Choose Two:
-  YARN
-  Local
-  Mesos
-  Standalone
-  Distributed
?
- Standalone
- Distributed
<!--SR:!2024-07-19,4,270-->


At the end of this code, which all topics will the consumer be sbscribed to: 
```java
Properties props = new Properties(); props.put(ConsumerConfig.BOOTSTRAP_SERVERS_CONFIG, "broker1:9092"); props.put(ConsumerConfig.GROUP_ID_CONFIG, "samplegroup"); props.put(ConsumerConfig.KEY_DESERIALIZER_CLASS_CONFIG,StringDeserializer.class); props.put(ConsumerConfig.VALUE_DESERIALIZER_CLASS_CONFIG,StringDeserializer.class);
KafkaConsumer consumer = new KafkaConsumer<>(props); consumer.subscribe(Arrays.asList("my_topic", "my_other_topic")); consumer.subscribe(Arrays.asList("last_topic"));
```
-  last_topic
-  my_topic, my_other_topic
-  Code throws error
-  my_topic, my_other_topic,last_topic  
?  
last_topic


Kafka Connect Configuration in a distributed modes are stored in
-  Special topic
-  Zookeeper
-  /tmp directory on brokers
-  Consumers
-  Producers
-  Workers  
?  
Special topic


For a topic with a replication factor 5, the number of leaders will be
-  Two
-  One
-  Three
-  Five
-  Zero
?
One
<!--SR:!2024-07-19,4,270-->


What should be the configurations looking like for High Throughput for Consumer Fetch Requests:
-  large fetch.min.bytes and large fetch.wait.max.ms
-  large fetch.min.bytes and small fetch.wait.max.ms
-  reasonable fetch.min.bytes and large fetch.wait.max.ms
-  None of the above  
?  
large fetch.min.bytes and large fetch.wait.max.ms


Which of the following is not a streaming framework?
-  Kafka Streams
-  Apache Storm
-  Apache Samza
-  Spark Streaming
-  Kafka Connect
-  Hive
?
-  Kafka Connect
-  Hive
<!--SR:!2024-07-19,4,270-->


True or False: All the writes in a replicated partition go to the leader and reads go to the followers:: False
<!--SR:!2024-07-19,4,270-->


The default value of `max.message.bytes` is:
-  1 MB
-  100 MB
-  10 MB
-  1 KB
?
1 MB
<!--SR:!2024-07-19,4,270-->


In a Kafka streams application which is the first place where stateful information is stored
-  Producer
-  Consumer
-  Zookeeper
-  Brokers
-  RocksDb  
?  
Brokers


Number of Controllers in a 40 broker cluster are
-  Two
-  One
-  Three
-  Five
-  Zero
?
One
<!--SR:!2024-07-19,4,270-->


Which class is used to create a Consumer in Kafka:
-  Consumer Class
-  KafkaConsumer Class
-  Kafka Class
-  ConfluentConsumer Class
-  Confluent Class
?
KafkaConsumer Class
<!--SR:!2024-07-19,4,270-->


We have got two records coming in a streaming application (orange,2) and (orange,5) We have decided it to treat them as a KStream and sum up the values. What will be the final result:
-  (orange,7)
-  (orange,2)
-  (orange,5)
-  (orange,3)
-  None of the above
?
(orange,7)
<!--SR:!2024-07-19,4,270-->


If a leader for a partition is lost due to failure, the new leader is elected by
-  Zookeeper
-  Controller
-  Producer
-  Consumers  
?  
Controller


How to temporarily stop consumption of new messages and resume it at a later point:
-  Stopping consumption temporarily is not possible
-  Use consumer.pause(partitions) and consumer.resume(partitions)
-  Use consumer.pause(topic) and consumer.resume(topic)
-  Use consumer.pause(message) and consumer.resume(message)  
?  
Use consumer.pause(partitions) and consumer.resume(partitions)


We have got two records coming in a streaming application (orange,2) and (orange,5) We have decided it to treat them as a KTable and sum up the values. What will be the final result
-  (orange,7)
-  (orange,2)
-  (orange,5)
-  (orange,3)
-  None of the above  
?  
(orange,5)


To gain knowledge about who is the leader for which partition, client sends a metadata request. The metadata request is sent to and served by:
-  Zookeeper
-  Any Broker
-  Producer
-  Consumers
?
Any Broker
<!--SR:!2024-07-19,4,270-->


Kafka uses which format to transport and store data on the brokers
-  String
-  bytearray
-  Avro
-  Parquet
-  Integer
-  Varchar
?
bytearray
<!--SR:!2024-07-19,4,270-->


Which of the following Kafka Streams operators are stateful? (Choose 3)
-  map
-  reduce
-  aggregate
-  count
-  Flatmap
?
-  reduce
-  aggregate
-  count
<!--SR:!2024-07-19,4,270-->


## References


## Flashcards