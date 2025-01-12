---
{"dg-publish":true,"permalink":"/reference/kafka-the-definitive-guide-v2-highlights/","title":"Kafka The Definitive Guide v2","tags":["✂️","📚"],"created":"2024-07-13T13:43:04.220-05:00","updated":"2025-01-02T22:19:19.391-06:00"}
---

# Kafka The Definitive Guide v2

![cover|150](https://readwise-assets.s3.amazonaws.com/static/images/default-book-icon-3.40504e56b01b.png)
## Metadata

## Highlights

### Meet Kafka
#### Publish/Subscribe Messaging
>[!QUOTE]  
>Publish/subscribe (pub/sub) messaging is a pattern that is characterized by the sender (publisher) of a piece of data (message) not specifically directing it to a receiver. Instead, the publisher classifies the message somehow, and that receiver (subscriber) subscribes to receive certain classes of messages. (Page 1) #✂️ 
{ #ref-745646998}


---
#### How It Starts
#### Individual Queue Systems
#### Enter Kafka
##### Messages and Batches
>[!QUOTE]  
>Apache Kafka was developed as a publish/subscribe messaging system designed to solve this problem. It is often described as a “distributed commit log” or more recently as a “distributing streaming platform. (Page 4) #✂️ 
{ #ref-745647003}


---
>[!QUOTE]  
>Messages and Batches The unit of data within Kafka is called a message. If you are approaching Kafka from a database background, you can think of this as similar to a row or a record (Page 4) #✂️ 
{ #ref-745647004}


---
>[!QUOTE]  
>A message can have an optional piece of metadata, which is referred to as a key. The key is also a byte array and, as with the message, has no specific meaning to Kafka. Keys are used when messages are to be written to partitions in a more controlled manner (Page 4) #✂️ 
{ #ref-745647005}


---
>[!QUOTE]  
>A batch is just a collection of messages, all of which are being produced to the same topic and partition (Page 5) #✂️ 
{ #ref-745647006}


---
>[!QUOTE]  
>A batch is just a collection of messages, all of which are being produced to the same topic and partition. An indi‐ vidual round trip across the network for each message would result in excessive over‐ head, and collecting messages together into a batch reduces this. Of course, this is a trade-off between latency and throughput: the larger the batches, the more messages that can be handled per unit of time, but the longer it takes an individual message to propagate (Page 5) #✂️ 
{ #ref-745647007}


---
##### Schemas
##### Topics and Partitions
>[!QUOTE]  
>use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️ 
{ #ref-745647010}


---
>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that addi‐ tional structure, or schema, be imposed on the message content so that it can be easily understood. There are many options available for message schema, depending on your application’s individual needs. Simplistic systems, such as JavaScript Object Notation (JSON) and Extensible Markup Language (XML), are easy to use and human readable. However, they lack features such as robust type handling and com‐ patibility between schema versions. Many Kafka developers favor the use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️ 
{ #ref-745647011}


---
>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that addi‐ tional structure, or schema, be imposed on the message content so that it can be easily understood. There are many options available for message schema, depending on your application’s individual needs. Simplistic systems, such as JavaScript Object Notation (JSON) and Extensible Markup Language (XML), are easy to use and human readable. However, they lack features such as robust type handling and com‐ patibility between schema versions. Many Kafka developers favor the use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️ 
{ #ref-745647012}


---
>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that addi‐ tional structure, or schema, be imposed on the message content so that it can be easily understood (Page 5) #✂️ 
{ #ref-745647013}


---
>[!QUOTE]  
>Messages in Kafka are categorized into topics. The closest analogies for a topic are a database table or a folder in a filesystem (Page 5) #✂️ 
{ #ref-745647014}


---
>[!QUOTE]  
>Topics are additionally broken down into a number of partitions. Going back to the “commit log” description, a partition is a sin‐ gle log. Messages are written to it in an append-only fashion and are read in order from beginning to end (Page 5) #✂️ 
{ #ref-745647015}


---
>[!QUOTE]  
>Partitions are also the way that Kafka provides redundancy and scalability. Each partition can be hosted on a different server, which means that a single topic can be scaled horizontally across multiple servers to provide performance far beyond the ability of a single server. Additionally, partitions can be replicated, such that different servers will store a copy of the same partition in case one server fails. (Page 6) #✂️ 
{ #ref-745647016}


---
>[!QUOTE]  
>The term stream is often used when discussing data within systems like Kafka. Most often, a stream is considered to be a single topic of data, regardless of the number of partitions. This represents a single stream of data moving from the producers to the consumers. (Page 6) #✂️ 
{ #ref-745647017}


---
##### Producers and Consumers
>[!QUOTE]  
>Producers create new messages. In other publish/subscribe systems, these may be called publishers or writers. A message will be produced to a specific topic. By default, the producer will balance messages over all partitions of a topic evenly. In some cases, the producer will direct messages to specific partitions. This is typically done using the message key and a partitioner that will generate a hash of the key and map it to a specific partition. (Page 6) #✂️ 
{ #ref-745647019}


---
>[!QUOTE]  
>Consumers read messages. In other publish/subscribe systems, these clients may be called subscribers or readers. The consumer subscribes to one or more topics and reads the messages in the order in which they were produced to each partition. The consumer keeps track of which messages it has already consumed by keeping track of the offset of messages (Page 7) #✂️ 
{ #ref-745647020}


---
>[!QUOTE]  
>The ofset—an integer value that continually increases—is another piece of metadata that Kafka adds to each message as it is produced. Each message in a given partition has a unique offset, and the following message has a greater offset (though not necessarily monotonically greater). By storing the next pos‐ sible offset for each partition, typically in Kafka itself, a consumer can stop and restart without losing its place (Page 7) #✂️ 
{ #ref-745647021}


---
>[!QUOTE]  
>Consumers work as part of a consumer group, which is one or more consumers that work together to consume a topic. The group ensures that each partition is only con‐ sumed by one member (Page 7) #✂️ 
{ #ref-745647022}


---
>[!QUOTE]  
>The mapping of a consumer to a partition is often called ownership of the partition by the consumer (Page 7) #✂️ 
{ #ref-745647023}


---
##### Brokers and Clusters
>[!QUOTE]  
>A single Kafka server is called a broker. The broker receives messages from producers, assigns offsets to them, and writes the messages to storage on disk. It also services consumers, responding to fetch requests for partitions and responding with the messages that have been published (Page 8) #✂️ 
{ #ref-745647025}


---
>[!QUOTE]  
>Kafka brokers are designed to operate as part of a cluster. Within a cluster of brokers, one broker will also function as the cluster controller (elected automatically from the live members of the cluster). The controller is responsible for administrative opera‐ tions, including assigning partitions to brokers and monitoring for broker failures (Page 8) #✂️ 
{ #ref-745647026}


---
>[!QUOTE]  
>A partition is owned by a single broker in the cluster, and that broker is called the leader of the partition. A replicated partition (as seen in Figure 1-7) is assigned to additional brokers, called followers of the partition. Replication provides redundancy of mes‐ sages in the partition, such that one of the followers can take over leadership if there is a broker failure (Page 8) #✂️ 
{ #ref-745647027}


---
>[!QUOTE]  
>All producers must connect to the leader in order to publish mes‐ sages, but consumers may fetch from either the leader or one of the followers (Page 8) #✂️ 
{ #ref-745647028}


---
>[!QUOTE]  
>key feature of Apache Kafka is that of retention, which is the durable storage of messages for some period of time. Kafka brokers are configured with a default reten‐ tion setting for topics, either retaining messages for some period of time (e.g., 7 days) or until the partition reaches a certain size in bytes (e.g., 1 GB). Once these limits are reached, messages are expired and deleted (Page 8) #✂️ 
{ #ref-745647029}


---
>[!QUOTE]  
>Individual topics can also be configured with their own retention settings so that messages are stored for only as long as they are useful (Page 9) #✂️ 
{ #ref-745647030}


---
>[!QUOTE]  
>Topics can also be configured as log compacted, which means that Kafka will retain only the last message produced with a specific key. This can be useful for changelog-type data, where only the last update is interesting (Page 9) #✂️ 
{ #ref-745647031}


---
##### Multiple Clusters
>[!QUOTE]  
>The Kafka project includes a tool called MirrorMaker, used for replicating data to other clusters. At its core, MirrorMaker is simply a Kafka consumer and producer, linked together with a queue. Messages are consumed from one Kafka cluster and produced to another. (Page 9) #✂️ 
{ #ref-745647033}


---
#### Why Kafka?
##### Multiple Producers
##### Multiple Consumers
##### Disk-Based Retention
>[!QUOTE]  
>Durable retention means that if a consumer falls behind, either due to slow processing or a burst in traffic, there is no danger of losing data. It also means that maintenance can be performed on consum‐ ers, taking applications offline for a short period of time, with no concern about mes‐ sages backing up on the producer or getting lost (Page 11) #✂️ 
{ #ref-745647038}


---
##### Scalable
##### High Performance
##### Platform Features
#### The Data Ecosystem
##### Use Cases
#### Kafka’s Origin
##### LinkedIn’s Problem
##### The Birth of Kafka
##### Open Source
##### Commercial Engagement
##### The Name
#### Getting Started with Kafka
### Installing Kafka
#### Environment Setup
##### Choosing an Operating System
##### Installing Java
##### Installing ZooKeeper
>[!QUOTE]  
>Apache Kafka uses Apache ZooKeeper to store metadata about the Kafka cluster, as well as consumer client details, as shown in Figure 2-1. ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services (Page 20) #✂️ 
{ #ref-745647056}


---
>[!QUOTE]  
>ZooKeeper is designed to work as a cluster, called an ensemble, to ensure high availa‐ bility. Due to the balancing algorithm used, it is recommended that ensembles con‐ tain an odd number of servers (e.g., 3, 5, and so on) as a majority of ensemble members (a quorum) must be working in order for ZooKeeper to respond to requests (Page 21) #✂️ 
{ #ref-745647057}


---
>[!QUOTE]  
>Consider running ZooKeeper in a five-node ensemble. To make configuration changes to the ensemble, including swapping a node, you will need to reload nodes one at a time (Page 22) #✂️ 
{ #ref-745647058}


---
>[!QUOTE]  
>To configure ZooKeeper servers in an ensemble, they must have a common configu‐ ration that lists all servers, and each server needs a myid file in the data directory that specifies the ID number of the server (Page 22) #✂️ 
{ #ref-745647059}


---
##### Installing a Kafka Broker
##### Confguring the Broker
>[!QUOTE]  
>Every Kafka broker must have an integer identifier, which is set using the broker.id configuration. By default, this integer is set to 0, but it can be any value. It is essential that the integer must be unique for each broker within a single Kafka cluster. The selection of this number is technically arbitrary, and it can be moved between brokers if necessary for maintenance tasks (Page 25) #✂️ 
{ #ref-745647062}


---
>[!QUOTE]  
>The new listeners config is a comma-separated list of URIs that we listen on with the listener names. If the lis‐ tener name is not a common security protocol, then another config listener.security.protocol.map must also be configured. A listener is defined as <protocol>://<hostname>:<port>. An example of a legal listener config is PLAIN TEXT://localhost:9092,SSL://:9091. Specifying the hostname as 0.0.0.0 will bind to all interfaces. Leaving the hostname empty will bind it to the default interface. (Page 25) #✂️ 
{ #ref-745647063}


---
>[!QUOTE]  
>The location of the ZooKeeper used for storing the broker metadata is set using the zookeeper.connect configuration parameter (Page 25) #✂️ 
{ #ref-745647064}


---
>[!QUOTE]  
>It is generally considered to be good practice to use a chroot path for the Kafka cluster. This allows the ZooKeeper ensemble to be shared with other applications, including other Kafka clusters, without a conflict (Page 26) #✂️ 
{ #ref-745647065}


---
>[!QUOTE]  
>Kafka persists all messages to disk, and these log segments are stored in the directory specified in the log.dir configuration. For multiple directories, the config log.dirs is preferable. If this value is not set, it will default back to log.dir. log.dirs is a comma-separated list of paths on the local system (Page 26) #✂️ 
{ #ref-745647066}


---
>[!QUOTE]  
>num.recovery.threads.per.data.dir Kafka uses a configurable pool of threads for handling log segments. Currently, this thread pool is used: • When starting normally, to open each partition’s log segments • When starting after a failure, to check and truncate each partition’s log segments • When shutting down, to cleanly close log segments (Page 26) #✂️ 
{ #ref-745647067}


---
>[!QUOTE]  
>The default Kafka configuration specifies that the broker should automatically create a topic under the following circumstances: • When a producer starts writing messages to the topic • When a consumer starts reading messages from the topic • When any client requests metadata for the topic (Page 27) #✂️ 
{ #ref-745647068}


---
>[!QUOTE]  
>In order to ensure a Kafka cluster doesn’t become unbalanced by having all topic leadership on one broker, this config can be specified to ensure leadership is balanced as much as possible. It enables a background thread that checks the distribution of partitions at regular intervals (this interval is configurable via leader. imbalance.check.interval.seconds) (Page 27) #✂️ 
{ #ref-745647069}


---
>[!QUOTE]  
>delete.topic.enable Depending on your environment and data retention guidelines, you may wish to lock down a cluster to prevent arbitrary deletions of topics. Disabling topic deletion can be set by setting this flag to false (Page 27) #✂️ 
{ #ref-745647070}


---
>[!QUOTE]  
>The num.partitions parameter determines how many partitions a new topic is cre‐ ated with, primarily when automatic topic creation is enabled (which is the default setting). This parameter defaults to one partition (Page 28) #✂️ 
{ #ref-745647071}


---
>[!QUOTE]  
>default.replication.factor If auto-topic creation is enabled, this configuration sets what the replication factor should be for new topics. (Page 29) #✂️ 
{ #ref-745647072}


---
>[!QUOTE]  
>It is highly recommended to set the replication factor to at least 1 above the min.insync.replicas setting (Page 29) #✂️ 
{ #ref-745647073}


---
>[!QUOTE]  
>It is highly recommended to set the replication factor to at least 1 above the min.insync.replicas setting. For more fault-resistant settings, if you have large enough clusters and enough hardware, setting your replication factor to 2 above the min.insync.replicas (abbreviated as RF++) can be preferable. RF++ will allow eas‐ ier maintenance and prevent outages (Page 29) #✂️ 
{ #ref-745647074}


---
>[!QUOTE]  
>log.retention.ms The most common configuration for how long Kafka will retain messages is by time. The default is specified in the configuration file using the log.retention.hours parameter, and it is set to 168 hours, or one week (Page 30) #✂️ 
{ #ref-745647075}


---
>[!QUOTE]  
>Another way to expire messages is based on the total number of bytes of messages retained. This value is set using the log.retention.bytes parameter, and it is applied per partition. This means that if you have a topic with 8 partitions, and log.retention.bytes is set to 1 GB, the amount of data retained for the topic will be 8 GB at most (Page 30) #✂️ 
{ #ref-745647076}


---
>[!QUOTE]  
>Once the log segment has reached the size specified by the log.segment.bytes parameter, which defaults to 1 GB, the log seg‐ ment is closed and a new one is opened. Once a log segment has been closed, it can be considered for expiration (Page 31) #✂️ 
{ #ref-745647077}


---
>[!QUOTE]  
>Adjusting the size of the log segments can be important if topics have a low produce rate. For example, if a topic receives only 100 megabytes per day of messages, and log.segment.bytes is set to the default, it will take 10 days to fill one segment. As messages cannot be expired until the log segment is closed, if log.retention.ms is set to 604800000 (1 week), there will actually be up to 17 days of messages retained until the closed log segment expires (Page 31) #✂️ 
{ #ref-745647078}


---
>[!QUOTE]  
>Another way to control when log segments are closed is by using the log.roll.ms parameter, which specifies the amount of time after which a log segment should be closed (Page 32) #✂️ 
{ #ref-745647079}


---
>[!QUOTE]  
>By default, there is no setting for log.roll.ms, which results in only closing log segments by size. (Page 32) #✂️ 
{ #ref-745647080}


---
>[!QUOTE]  
>When configuring your cluster for data durability, setting min.insync.replicas to 2 ensures that at least two replicas are caught up and “in sync” with the producer. This is used in tandem with setting the producer config to ack “all” requests. This will ensure that at least two replicas (leader and one other) acknowledge a write for it to be successful. (Page 32) #✂️ 
{ #ref-745647081}


---
>[!QUOTE]  
>The Kafka broker limits the maximum size of a message that can be produced, con‐ figured by the message.max.bytes parameter, which defaults to 1000000, or 1 MB (Page 32) #✂️ 
{ #ref-745647082}


---
##### The message size configured on the Kafka broker must be coordi‐ nated with the fetch.message.max.bytes configuration on con‐ sumer clients. If this value is smaller than message.max.bytes, then consumers that encounter larger messages will fail to fetch those messages, resulting in a situation where the consumer gets stuck and cannot proceed
>[!QUOTE]  
>Selecting Hardware (Page 33) #✂️ 
{ #ref-745647084}


---
>[!QUOTE]  
>Currently, in a well-configured envi‐ ronment, it is recommended to not have more than 14,000 partition replicas per broker and 1 million replicas per cluster (Page 38) #✂️ 
{ #ref-745647085}


---
>[!QUOTE]  
>There are only two requirements in the broker configuration to allow multiple Kafka brokers to join a single cluster. The first is that all brokers must have the same config‐ uration for the zookeeper.connect parameter. This specifies the ZooKeeper ensem‐ ble and path where the cluster stores metadata. The second requirement is that all brokers in the cluster must have a unique value for the broker.id parameter. If two brokers attempt to join the same cluster with the same broker.id, the second broker will log an error and fail to start (Page 38) #✂️ 
{ #ref-745647086}


---
>[!QUOTE]  
>Regardless of which filesystem is chosen for the mount that holds the log segments, it is advisable to set the noatime mount option for the mount point. File metadata con‐ tains three timestamps: creation time (ctime), last modified time (mtime), and last access time (atime). By default, the atime is updated every time a file is read. This generates a large number of disk writes (Page 41) #✂️ 
{ #ref-745647087}


---
##### Production Concerns
>[!QUOTE]  
>It is now recommended for Kafka to use G1GC as the default garbage collector (Page 42) #✂️ 
{ #ref-745647089}


---
>[!QUOTE]  
>Kafka can assign new partitions to brokers in a rack-aware manner, making sure that replicas for a single partition do not share a rack. To do this, the broker.rack config‐ uration for each broker must be set properly. (Page 44) #✂️ 
{ #ref-745647090}


---
>[!QUOTE]  
>This amount of traffic is generally minimal, and it does not justify the use of a dedicated ZooKeeper ensemble for a single Kafka cluster. In fact, many deployments will use a single Zoo‐ Keeper ensemble for multiple Kafka clusters (Page 44) #✂️ 
{ #ref-745647091}


---
>[!QUOTE]  
>Outside of using a single ensemble for multiple Kafka clusters, it is not recommended to share the ensemble with other applications, if it can be avoided. Kafka is sensitive to ZooKeeper latency and timeouts, and an interruption in communications with the ensemble will cause the brokers to behave unpredictably (Page 45) #✂️ 
{ #ref-745647092}


---
### Kafka Producers: Writing Messages to Kafka
>[!QUOTE]  
>While we ignore errors that may occur while sending messages to Kafka brokers or in the brokers themselves, we may still get an exception if the producer encountered errors before sending the message to Kafka. Those can be, for exam‐ ple, a SerializationException when it fails to serialize the message, a Buffer ExhaustedException or TimeoutException if the buffer is full, or an InterruptException if the sending thread was interrupted (Page 52) #✂️ 
{ #ref-745647094}


---
>[!QUOTE]  
>To use callbacks, you need a class that implements the org.apache.kafka. clients.producer.Callback interface, which has a single function—on Completion(). (Page 54) #✂️ 
{ #ref-745647095}


---
>[!QUOTE]  
>The callbacks execute in the producer’s main thread. This guaran‐ tees that when we send two messages to the same partition one after another, their callbacks will be executed in the same order that we sent them. But it also means that the callback should be reason‐ ably fast to avoid delaying the producer and preventing other mes‐ sages from being sent. It is not recommended to perform a blocking operation within the callback. Instead, you should use another thread to perform any blocking operation concurrently. (Page 54) #✂️ 
{ #ref-745647096}


---
>[!QUOTE]  
>(record, new DemoProducerCallback()); To use callbacks, you need a class that implements the org.apache.kafka. clients.producer.Callback interface, which has a single function—on Completion(). If Kafka returned an error, onCompletion() will have a nonnull exception. Here we “handle” it by printing, but production code will probably have more robust error handling functions. The records are the same as before. And we pass a Callback object along when sending the record. The callbacks execute in the producer’s main thread. This guaran‐ tees that when we send two messages to the same partition one after another, their callbacks will be executed in the same order that we sent them. But it also means that the callback should be reason‐ ably fast to avoid delaying the producer and preventing other mes‐ sages from being sent. It is not recommended to perform a blocking operation within the callback. Instead, you should use another thread to perform any blocking operation concurrently. Confguring Producers So far we’ve seen very few configuration parameters for the producers—just the mandatory bootstrap.servers URI and serializers. The producer has a large number of configuration parameters that are documented in Apache Kafka documentation, and many have reasonable defaults, so there is no reason to tinker with every single parameter. However, some of the parameters have a significant impact on memory use, performance, and reliability of the producers. We will review those here. 54 | Chapter 3: Kafka Producers: Writing Messages to Kafka (Page 54) #✂️ 
{ #ref-824785881}


---
>[!QUOTE]  
>client.id is a logical identifier for the client and the application it is used in. This can be any string and will be used by the brokers to identify messages sent from the client. (Page 55) #✂️ 
{ #ref-745647097}


---
>[!QUOTE]  
>The acks parameter controls how many partition replicas must receive the record before the producer can consider the write successful. By default, Kafka will respond that the record was written successfully after the leader received the record (Page 55) #✂️ 
{ #ref-745647098}


---
>[!QUOTE]  
>acks=0 The producer will not wait for a reply from the broker before assuming the mes‐ sage was sent successfully (Page 55) #✂️ 
{ #ref-745647099}


---
>[!QUOTE]  
>acks=1 The producer will receive a success response from the broker the moment the leader replica receives the message (Page 55) #✂️ 
{ #ref-745647100}


---
>[!QUOTE]  
>acks=all The producer will receive a success response from the broker once all in sync replicas receive the message (Page 55) #✂️ 
{ #ref-745647101}


---
>[!QUOTE]  
>You will see that with lower and less reliable acks configuration, the producer will be able to send records faster. This means that you trade off reliability for producer latency.However, end-to-end latency is measured from the time a record was produced until it is available for consumers to read and is identical for all three options. The reason is that, in order to maintain consistency, Kafka will not allow consumers to read records until they are written to all in sync replicas.Therefore, if you care about end-to-end latency, rather than just the producer latency, there is no trade-off to make: you will get the same end-to-end latency if you choose the most reliable option. (Page 56) #✂️ 
{ #ref-745647102}


---
>[!QUOTE]  
>max.block.ms This parameter controls how long the producer may block when calling send() and when explicitly requesting metadata via partitionsFor(). Those methods may block when the producer’s send buffer is full or when metadata is not available. When max.block.ms is reached, a timeout exception is thrown (Page 57) #✂️ 
{ #ref-745647103}


---
>[!QUOTE]  
>delivery.timeout.ms This configuration will limit the amount of time spent from the point a record is ready for sending (send() returned successfully and the record is placed in a batch) until either the broker responds or the client gives up, including time spent on retries (Page 57) #✂️ 
{ #ref-745647104}


---
>[!QUOTE]  
>request.timeout.ms This parameter controls how long the producer will wait for a reply from the server when sending data. Note that this is the time spent waiting on each producer request before giving up; it does not include retries (Page 58) #✂️ 
{ #ref-745647105}


---
>[!QUOTE]  
>linger.ms controls the amount of time to wait for additional messages before send‐ ing the current batch. KafkaProducer sends a batch of messages either when the cur‐ rent batch is full or when the linger.ms limit is reached (Page 59) #✂️ 
{ #ref-745647106}


---
>[!QUOTE]  
>bufer.memory This config sets the amount of memory the producer will use to buffer messages wait‐ ing to be sent to brokers (Page 59) #✂️ 
{ #ref-745647107}


---
>[!QUOTE]  
>compression.type By default, messages are sent uncompressed. This parameter can be set to snappy, gzip, lz4, or zstd, in which case the corresponding compression algorithms will be used to compress the data before sending it to the brokers (Page 59) #✂️ 
{ #ref-745647108}


---
>[!QUOTE]  
>batch.size When multiple records are sent to the same partition, the producer will batch them together. This parameter controls the amount of memory in bytes (not messages!) that will be used for each batch. (Page 59) #✂️ 
{ #ref-745647109}


---
>[!QUOTE]  
>max.in.fight.requests.per.connection This controls how many message batches the producer will send to the server without receiving responses (Page 60) #✂️ 
{ #ref-745647110}


---
>[!QUOTE]  
>Setting the retries parameter to nonzero and the max.in. flight.requests.per.connection to more than 1 means that it is possible that the broker will fail to write the first batch of messages, succeed in writing the second (which was already in-flight), and then retry the first batch and succeed, thereby reversing the order. Since we want at least two in-flight requests for performance rea‐ sons, and a high number of retries for reliability reasons, the best solution is to set enable.idempotence=true. This guarantees mes‐ sage ordering with up to five in-flight requests and also guarantees that retries will not introduce duplicates (Page 60) #✂️ 
{ #ref-745647111}


---
>[!QUOTE]  
>max.request.size This setting controls the size of a produce request sent by the producer. It caps both the size of the largest message that can be sent and the number of messages that the producer can send in one request (Page 60) #✂️ 
{ #ref-745647112}


---
>[!QUOTE]  
>receive.bufer.bytes and send.bufer.bytes These are the sizes of the TCP send and receive buffers used by the sockets when writing and reading data. If these are set to –1, the OS defaults will be used. It is a good idea to increase these when producers or consumers communicate with brokers in a different datacenter, because those network links typically have higher latency and lower bandwidth (Page 61) #✂️ 
{ #ref-745647113}


---
>[!QUOTE]  
>To avoid this, you can set enable.idempotence=true. When the idempotent pro‐ ducer is enabled, the producer will attach a sequence number to each record it sends. If the broker receives records with the same sequence number, it will reject the sec‐ ond copy and the producer will receive the harmless DuplicateSequenceException (Page 61) #✂️ 
{ #ref-745647114}


---
>[!QUOTE]  
>Enabling idempotence requires max.in.flight.requests.per. connection to be less than or equal to 5, retries to be greater than 0, and acks=all. If incompatible values are set, a ConfigException will be thrown. (Page 61) #✂️ 
{ #ref-745647115}


---
>[!QUOTE]  
>Starting in the Apache Kafka 2.4 producer, the round-robin algorithm used in the default partitioner when han‐ dling null keys is sticky. This means that it will fill a batch of messages sent to a single partition before switching to the next partition (Page 69) #✂️ 
{ #ref-745647116}


---
>[!QUOTE]  
>In addition to the default partitioner, Apache Kafka clients also provide RoundRobin Partitioner and UniformStickyPartitioner. These provide random partition assignment and sticky random partition assignment even when messages have keys. These are useful when keys are important for the consuming application (for exam‐ ple, there are ETL applications that use the key from Kafka records as the primary key when loading data from Kafka to a relational database), but the workload may be skewed, so a single key may have a disproportionately large workload. Using the UniformStickyPartitioner will result in an even distribution of workload across all partitions. (Page 69) #✂️ 
{ #ref-745647117}


---
>[!QUOTE]  
>Headers are often used for lineage to indicate the source of the data in the record, and for routing or tracing messages based on header information without having to parse the message itself (perhaps the message is encrypted and the router doesn’t have permissions to access the data) (Page 71) #✂️ 
{ #ref-745647118}


---
>[!QUOTE]  
>Kafka has three quota types: pro‐ duce, consume, and request. Produce and consume quotas limit the rate at which cli‐ ents can send and receive data, measured in bytes per second. Request quotas limit the percentage of time the broker spends processing client requests (Page 73) #✂️ 
{ #ref-745647119}


---
>[!QUOTE]  
>Kafka has three quota types: pro‐ duce, consume, and request. Produce and consume quotas limit the rate at which cli‐ ents can send and receive data, measured in bytes per second. Request quotas limit the percentage of time the broker spends processing client requests. (Page 73) #✂️ 
{ #ref-745647120}


---
>[!QUOTE]  
>Quotas that are specified in Kafka’s configuration file are static, and you can only modify them by changing the configuration and then restarting all the brokers. Since new clients can arrive at any time, this is very inconvenient. Therefore the usual method of applying quotas to specific clients is through dynamic configuration that can be set using kafka-config.sh or the AdminClient API. (Page 74) #✂️ 
{ #ref-745647121}


---
>[!QUOTE]  
>To protect the broker from misbehaved clients sending addi‐ tional requests while being throttled, the broker will also mute the communication channel with the client for the period of time needed to achieve compliance with the quota. (Page 74) #✂️ 
{ #ref-745647122}


---
### Kafka Consumers: Reading Data from Kafka
>[!QUOTE]  
>Kafka consumers are typically part of a consumer group. When multiple consumers are subscribed to a topic and belong to the same consumer group, each consumer in the group will receive messages from a different subset of the partitions in the topic. (Page 78) #✂️ 
{ #ref-745647124}


---
>[!QUOTE]  
>Keep in mind that there is no point in adding more consumers than you have partitions in a topic—some of the consumers will just be idle (Page 79) #✂️ 
{ #ref-745647125}


---
>[!QUOTE]  
>To summarize, you create a new consumer group for each application that needs all the messages from one or more topics. You add consumers to an existing consumer group to scale the reading and processing of messages from the topics, so each addi‐ tional consumer in a group will only get a subset of the messages (Page 80) #✂️ 
{ #ref-745647126}


---
>[!QUOTE]  
>Moving partition ownership from one consumer to another is called a rebalance. Rebalances are important because they provide the consumer group with high availa‐ bility and scalability (allowing us to easily and safely add and remove consumers), but in the normal course of events they can be fairly undesirable. (Page 81) #✂️ 
{ #ref-745647127}


---
>[!QUOTE]  
>During an eager rebalance, all consumers stop consuming, give up their owner‐ ship of all partitions, rejoin the consumer group, and get a brand-new partition assignment. This is essentially a short window of unavailability of the entire con‐ sumer group. The length of the window depends on the size of the consumer group as well as on several configuration parameters (Page 81) #✂️ 
{ #ref-745647128}


---
>[!QUOTE]  
>Cooperative rebalances (also called incremental rebalances) typically involve reas‐ signing only a small subset of the partitions from one consumer to another, and allowing consumers to continue processing records from all the partitions that are not reassigned. (Page 81) #✂️ 
{ #ref-745647129}


---
>[!QUOTE]  
>Initially, the consumer group leader informs all the consumers that they will lose ownership of a subset of their partitions, then the consumers stop consuming from these partitions and give up their ownership in them. In the second phase, the consumer group leader assigns these now orphaned partitions to their new owners. This incremental approach may take a few iterations until a stable parti‐ tion assignment is achieved, but it avoids the complete “stop the world” unavaila‐ bility that occurs with the eager approach (Page 82) #✂️ 
{ #ref-745647130}


---
>[!QUOTE]  
>Consumers maintain membership in a consumer group and ownership of the parti‐ tions assigned to them by sending heartbeats to a Kafka broker designated as the group coordinator (this broker can be different for different consumer groups) (Page 82) #✂️ 
{ #ref-745647131}


---
>[!QUOTE]  
>When a consumer wants to join a group, it sends a JoinGroup request to the group coordinator. The first consumer to join the group becomes the group leader. The leader receives a list of all consumers in the group from the group coordinator (this will include all consumers that sent a heartbeat recently and that are therefore considered alive) and is responsible for assigning a subset of partitions to each consumer. It uses an implementation of PartitionAssignor to decide which partitions should be handled by which consumer. Kafka has few built-in partition assignment policies, which we will discuss in more depth in the configuration section. After deciding on the partition assignment, the consumer group leader sends the list of assignments to the GroupCoordinator, which sends this information to all the consumers. Each consumer only sees its own assignment—the leader is the only client process that has the full list of consumers in the group and their assignments. This process repeats every time a rebalance happens (Page 83) #✂️ 
{ #ref-745647132}


---
>[!QUOTE]  
>Static group membership is useful when your application maintains local state or cache that is populated by the partitions that are assigned to each consumer. When re-creating this cache is time-consuming, you don’t want this process to happen every time a consumer restarts. On the flip side, it is important to remember that the (Page 83) #✂️ 
{ #ref-745647133}


---
>[!QUOTE]  
>How Does the Process of Assigning Partitions to Consumers Work? When a consumer wants to join a group, it sends a JoinGroup request to the group coordinator. The first consumer to join the group becomes the group leader. The leader receives a list of all consumers in the group from the group coordinator (this will include all consumers that sent a heartbeat recently and that are therefore considered alive) and is responsible for assigning a subset of partitions to each consumer. It uses an implementation of PartitionAssignor to decide which partitions should be handled by which consumer. Kafka has few built-in partition assignment policies, which we will discuss in more depth in the configuration section. After deciding on the partition assignment, the consumer group leader sends the list of assignments to the GroupCoordinator, which sends this information to all the consumers. Each consumer only sees its own assignment—the leader is the only client process that has the full list of consumers in the group and their assignments. This process repeats every time a rebalance happens. Static Group Membership By default, the identity of a consumer as a member of its consumer group is transient. When consumers leave a consumer group, the partitions that were assigned to the consumer are revoked, and when it rejoins, it is assigned a new member ID and a new set of partitions through the rebalance protocol. All this is true unless you configure a consumer with a unique group.instance.id, which makes the consumer a static member of the group. When a consumer first joins a consumer group as a static member of the group, it is assigned a set of parti‐ tions according to the partition assignment strategy the group is using, as normal. However, when this consumer shuts down, it does not automatically leave the group—it remains a member of the group until its session times out. When the con‐ sumer rejoins the group, it is recognized with its static identity and is reassigned the same partitions it previously held without triggering a rebalance. The group coordi‐ nator that caches the assignment for each member of the group does not need to trig‐ ger a rebalance but can just send the cache assignment to the rejoining static member. If two consumers join the same group with the same group.instance.id, the second consumer will get an error saying that a consumer with this ID already exists. Static (Page 83) #✂️ 
{ #ref-745647134}


---
>[!QUOTE]  
>When a consumer wants to join a group, it sends a JoinGroup request to the group coordinator. The first consumer to join the group becomes the group leader. The leader receives a list of all consumers in the group from the group coordinator (this will include all consumers that sent a heartbeat recently and that are therefore considered alive) and is responsible for assigning a subset of partitions to each consumer. It uses an implementation of PartitionAssignor to decide which partitions should be handled by which consumer. Kafka has few built-in partition assignment policies, which we will discuss in more depth in the configuration section. After deciding on the partition assignment, the consumer group leader sends the list of assignments to the GroupCoordinator, which sends this information to all the consumers. Each consumer only sees its own assignment—the leader is the only client process that has the full list of consumers in the group and their assignments. This process repeats every time a rebalance happens (Page 83) #✂️ 
{ #ref-745647135}


---
>[!QUOTE]  
>Static group membership is useful when your application maintains local state or cache that is populated by the partitions that are assigned to each consumer. When re-creating this cache is time-consuming, you don’t want this process to happen every time a consumer restarts (Page 83) #✂️ 
{ #ref-745647136}


---
>[!QUOTE]  
>It is important to note that static members of consumer groups do not leave the group proactively when they shut down, and detecting when they are “really gone” depends on the session.timeout.ms configuration. You’ll want to set it high enough to avoid triggering rebalances on a simple application restart but low enough to allow automatic reassignment of their partitions when there is more significant downtime, to avoid large gaps in processing these partitions (Page 84) #✂️ 
{ #ref-745647137}


---
>[!QUOTE]  
>To start, we just need to use the three mandatory properties: bootstrap.servers, key.deserializer, and value.deserializer (Page 84) #✂️ 
{ #ref-745647138}


---
>[!QUOTE]  
>There is a fourth property, which is not strictly mandatory but very commonly used. The property is group.id, and it specifies the consumer group the KafkaConsumer instance belongs to (Page 84) #✂️ 
{ #ref-745647139}


---
>[!QUOTE]  
>It is also possible to call subscribe with a regular expression. The expression can match multiple topic names, and if someone creates a new topic with a name that matches, a rebalance will happen almost immediately and the consumers will start consuming from the new topic. This is useful for applications that need to consume from multiple topics and can handle the different types of data the topics will contain. Subscribing to multiple topics using a regular expression is most commonly used in applications that replicate data between Kafka and another system or streams pro‐ cessing applications (Page 85) #✂️ 
{ #ref-745647140}


---
>[!QUOTE]  
>The parameter we pass to poll() is a timeout interval and controls how long poll() will block if data is not avail‐ able in the consumer buffer. If this is set to 0 or if there are records available already, poll() will return immediately; otherwise, it will wait for the specified number of milliseconds. (Page 86) #✂️ 
{ #ref-745647141}


---
>[!QUOTE]  
>poll() returns a list of records. Each record contains the topic and partition the record came from, the offset of the record within the partition, and, of course, the key and the value of the record (Page 86) #✂️ 
{ #ref-745647142}


---
>[!QUOTE]  
>The poll loop does a lot more than just get data. The first time you call poll() with a new consumer, it is responsible for finding the GroupCoordinator, joining the con‐ sumer group, and receiving a partition assignment. If a rebalance is triggered, it will be handled inside the poll loop as well, including related callbacks. This means that almost everything that can go wrong with a consumer or in the callbacks used in its listeners is likely to show up as an exception thrown by poll(). (Page 87) #✂️ 
{ #ref-745647143}


---
>[!QUOTE]  
>You can’t have multiple consumers that belong to the same group in one thread, and you can’t have multiple threads safely use the same consumer. One consumer per thread is the rule. To run multiple consumers in the same group in one application, you will need to run each in its own thread (Page 87) #✂️ 
{ #ref-745647144}


---
>[!QUOTE]  
>This property allows a consumer to specify the minimum amount of data that it wants to receive from the broker when fetching records, by default one byte. If a broker receives a request for records from a consumer but the new records amount to fewer bytes than fetch.min.bytes, the broker will wait until more messages are available before sending the records back to the consumer. (Page 88) #✂️ 
{ #ref-745647145}


---
>[!QUOTE]  
>By setting fetch.min.bytes, you tell Kafka to wait until it has enough data to send before responding to the consumer. fetch.max.wait.ms lets you control how long to wait. By default, Kafka will wait up to 500 ms (Page 88) #✂️ 
{ #ref-745647146}


---
>[!QUOTE]  
>fetch.max.bytes This property lets you specify the maximum bytes that Kafka will return whenever the consumer polls a broker (50 MB by default). It is used to limit the size of memory that the consumer will use to store data that was returned from the server, irrespec‐ tive of how many partitions or messages were returned (Page 89) #✂️ 
{ #ref-745647147}


---
>[!QUOTE]  
>max.poll.records This property controls the maximum number of records that a single call to poll() will return (Page 89) #✂️ 
{ #ref-745647148}


---
>[!QUOTE]  
>max.partition.fetch.bytes This property controls the maximum number of bytes the server will return per parti‐ tion (1 MB by default) (Page 89) #✂️ 
{ #ref-745647149}


---
>[!QUOTE]  
>session.timeout.ms and heartbeat.interval.ms The amount of time a consumer can be out of contact with the brokers while still considered alive defaults to 10 seconds. If more than session.timeout.ms passes without the consumer sending a heartbeat to the group coordinator, it is considered dead and the group coordinator will trigger a rebalance of the consumer group to allocate partitions from the dead consumer to the other consumers in the group. This property is closely related to heartbeat.interval.ms, which controls how frequently the Kafka consumer will send a heartbeat to the group coordinator, whereas session.timeout.ms controls how long a consumer can go without sending a heart‐ beat. Therefore, those two properties are typically modified together—heartbeat. interval.ms must be lower than session.timeout.ms and is usually set to one-third (Page 89) #✂️ 
{ #ref-745647150}


---
>[!QUOTE]  
>max.poll.interval.ms This property lets you set the length of time during which the consumer can go without polling before it is considered dead. As mentioned earlier, heartbeats and ses‐ sion timeouts are the main mechanism by which Kafka detects dead consumers and takes their partitions away (Page 90) #✂️ 
{ #ref-745647151}


---
>[!QUOTE]  
>Even with max.poll.records defined, the interval between calls to poll() is difficult to predict, and max.poll.interval.ms is used as a fail-safe or backstop. It has to be an interval large enough that it will very rarely be reached by a healthy consumer but low enough to avoid significant impact from a hanging consumer. The default value is 5 minutes (Page 90) #✂️ 
{ #ref-745647152}


---
>[!QUOTE]  
>default.api.timeout.ms This is the timeout that will apply to (almost) all API calls made by the consumer when you don’t specify an explicit timeout while calling the API. The default is 1 minute (Page 90) #✂️ 
{ #ref-745647153}


---
>[!QUOTE]  
>request.timeout.ms This is the maximum amount of time the consumer will wait for a response from the broker (Page 90) #✂️ 
{ #ref-745647154}


---
>[!QUOTE]  
>auto.ofset.reset This property controls the behavior of the consumer when it starts reading a partition for which it doesn’t have a committed offset, or if the committed offset it has is inva‐ lid (usually because the consumer was down for so long that the record with that off‐ set was already aged out of the broker). The default is “latest,” which means that lacking a valid offset, the consumer will start reading from the newest records (records that were written after the consumer started running). The alternative is “earliest,” which means that lacking a valid offset, the consumer will read all the data in the partition, starting from the very beginning. Setting auto.offset.reset to none will cause an exception to be thrown when attempting to consume from an invalid offset (Page 91) #✂️ 
{ #ref-745647155}


---
>[!QUOTE]  
>enable.auto.commit This parameter controls whether the consumer will commit offsets automatically, and defaults to true. Set it to false if you prefer to control when offsets are committed, which is necessary to minimize duplicates and avoid missing data (Page 91) #✂️ 
{ #ref-745647156}


---
>[!QUOTE]  
>Range Assigns to each consumer a consecutive subset of partitions from each topic it subscribes to (Page 91) #✂️ 
{ #ref-745647157}


---
>[!QUOTE]  
>RoundRobin Takes all the partitions from all subscribed topics and assigns them to consumers sequentially, one by one (Page 92) #✂️ 
{ #ref-745647158}


---
>[!QUOTE]  
>Sticky The Sticky Assignor has two goals: the first is to have an assignment that is as balanced as possible, and the second is that in case of a rebalance, it will leave as many assignments as possible in place, minimizing the overhead associated with moving partition assignments from one consumer to another (Page 92) #✂️ 
{ #ref-745647159}


---
>[!QUOTE]  
>Cooperative Sticky This assignment strategy is identical to that of the Sticky Assignor but supports cooperative rebalances in which consumers can continue consuming from the partitions that are not reassigned (Page 92) #✂️ 
{ #ref-745647160}


---
>[!QUOTE]  
>The partition.assignment.strategy allows you to choose a partition assignment strategy. The default is org.apache.kafka.clients.consumer.RangeAssignor, which implements the Range strategy described earlier (Page 92) #✂️ 
{ #ref-745647161}


---
>[!QUOTE]  
>client.id This can be any string, and will be used by the brokers to identify requests sent from the client, such as fetch requests. It is used in logging and metrics, and for quotas. (Page 93) #✂️ 
{ #ref-745647162}


---
>[!QUOTE]  
>client.rack By default, consumers will fetch messages from the leader replica of each partition. However, when the cluster spans multiple datacenters or multiple cloud availability zones, there are advantages both in performance and in cost to fetching messages from a replica that is located in the same zone as the consumer. To enable fetching from the closest replica, you need to set the client.rack configuration and identify the zone in which the client is located (Page 93) #✂️ 
{ #ref-745647163}


---
>[!QUOTE]  
>group.instance.id This can be any unique string and is used to provide a consumer with static group membership (Page 93) #✂️ 
{ #ref-745647164}


---
>[!QUOTE]  
>receive.bufer.bytes and send.bufer.bytes These are the sizes of the TCP send and receive buffers used by the sockets when writing and reading data. If these are set to –1, the OS defaults will be used. It can be a good idea to increase these when producers or consumers communicate with brokers in a different datacenter, because those network links typically have higher latency and lower bandwidth. (Page 93) #✂️ 
{ #ref-745647165}


---
>[!QUOTE]  
>ofsets.retention.minutes This is a broker configuration, but it is important to be aware of it due to its impact on consumer behavior. As long as a consumer group has active members (i.e., mem‐ bers that are actively maintaining membership in the group by sending heartbeats), the last offset committed by the group for each partition will be retained by Kafka, so it can be retrieved in case of reassignment or restart. However, once a group becomes empty, Kafka will only retain its committed offsets to the duration set by this configu‐ ration—7 days by default. Once the offsets are deleted, if the group becomes active again it will behave like a brand-new consumer group with no memory of anything it consumed in the past (Page 93) #✂️ 
{ #ref-745647166}


---
>[!QUOTE]  
>We call the action of updating the current position in the partition an offset commit. Unlike traditional message queues, Kafka does not commit records individually. Instead, consumers commit the last message they’ve successfully processed from a partition and implicitly assume that every message before the last was also success‐ fully processed (Page 94) #✂️ 
{ #ref-745647167}


---
>[!QUOTE]  
>How does a consumer commit an offset? It sends a message to Kafka, which updates a special __consumer_offsets topic with the committed offset for each partition. As long as all your consumers are up, running, and churning away, this will have no impact. However, if a consumer crashes or a new consumer joins the consumer group, this will trigger a rebalance. After a rebalance, each consumer may be assigned a new set of partitions than the one it processed before. In order to know where to pick up the work, the consumer will read the latest committed offset of each partition and continue from there (Page 94) #✂️ 
{ #ref-745647168}


---
>[!QUOTE]  
>With autocommit enabled, when it is time to commit offsets, the next poll will com‐ mit the last offset returned by the previous poll. It doesn’t know which events were actually processed, so it is critical to always process all the events returned by poll() before calling poll() again (Page 96) #✂️ 
{ #ref-745647169}


---
>[!QUOTE]  
>A simple pattern to get the commit order right for asynchronous retries is to use a monotonically increasing sequence number. Increase the sequence number every time you commit, and add the sequence number at the time of the commit to the commitAsync callback. When you’re getting ready to send a retry, check if the commit sequence number the callback got is equal to the instance variable; if it is, there was no newer commit and it is safe to retry. If the instance sequence number is higher, don’t retry because a newer commit was already sent. (Page 99) #✂️ 
{ #ref-745647170}


---
>[!QUOTE]  
>The Consumer API allows you to run your own code when partitions are added or removed from the consumer. You do this by passing a ConsumerRebalanceListener when calling the subscribe() method we discussed previously (Page 101) #✂️ 
{ #ref-745647171}


---
>[!QUOTE]  
>If you use a cooperative rebalancing algorithm, note that: • onPartitionsAssigned() will be invoked on every rebalance, as a way of notifying the consumer that a rebalance happened. However, if there are no new partitions assigned to the con‐ sumer, it will be called with an empty collection. • onPartitionsRevoked() will be invoked in normal rebalanc‐ ing conditions, but only if the consumer gave up the owner‐ ship of partitions. It will not be called with an empty collection. • onPartitionsLost() will be invoked in exceptional rebalanc‐ ing conditions, and the partitions in the collection will already have new owners by the time the method is invoked. If you implemented all three methods, you are guaranteed that dur‐ ing a normal rebalance, onPartitionsAssigned() will be called by the new owner of the partitions that are reassigned only after the previous owner completed onPartitionsRevoked() and gave up its ownership. (Page 102) #✂️ 
{ #ref-745647172}


---
>[!QUOTE]  
>If you want to start reading all messages from the beginning of the partition, or you want to skip all the way to the end of the partition and start consuming only new messages, there are APIs specifically for that: seekToBeginning(Collection<Topic Partition> tp) and seekToEnd(Collection<TopicPartition> tp). (Page 104) #✂️ 
{ #ref-745647173}


---
>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only con‐ sumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. (Page 105) #✂️ 
{ #ref-745647174}


---
>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only con‐ sumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. The WakeupException doesn’t need to be handled, but before exiting the thread, you must call consumer.close(). Closing the consumer will com‐ mit offsets if needed and will send the group coordinator a message that the con‐ sumer is leaving the group (Page 105) #✂️ 
{ #ref-745647175}


---
>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only con‐ sumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. The WakeupException doesn’t need to be handled, but before exiting the thread, you must call consumer.close(). Closing the consumer will com‐ mit offsets if needed and will send the group coordinator a message that the con‐ sumer is leaving the group. (Page 105) #✂️ 
{ #ref-745647176}


---
>[!QUOTE]  
>When you know exactly which partitions the consumer should read, you don’t sub‐ scribe to a topic—instead, you assign yourself a few partitions. A consumer can either subscribe to topics (and be (Page 110) #✂️ 
{ #ref-745647177}


---
>[!QUOTE]  
>When you know exactly which partitions the consumer should read, you don’t sub‐ scribe to a topic—instead, you assign yourself a few partitions. A consumer can either subscribe to topics (and be part of a consumer group) or assign itself partitions, but not both at the same time (Page 110) #✂️ 
{ #ref-824785880}


---
### Managing Apache Kafka Programmatically
#### AdminClient Overview
>[!QUOTE]  
>If you start an AdminClient, eventually you want to close it. It is important to remem‐ ber that when you call close, there could still be some AdminClient operations in progress. Therefore, the close method accepts a timeout parameter. Once you call close, you can’t call any other methods and send any more requests, but the client will wait for responses until the timeout expires. After the timeout expires, the client will abort all ongoing operations with timeout exception and release all resources. Calling close without a timeout implies that the client will wait as long as it takes for all ongoing operations to complete (Page 116) #✂️ 
{ #ref-824785883}


---
#### Essential Topic Management
#### Confguration Management
#### Consumer Group Management
#### Cluster Metadata
#### Advanced Admin Operations
### Kafka Internals
#### Cluster Membership
>[!QUOTE]  
>Every time a broker process starts, it registers itself with its ID in ZooKeeper by creating an ephemeral node. (Page 135) #✂️ 
{ #ref-824785891}


---
>[!QUOTE]  
>Kafka brokers, the controller, and some of the ecosystem tools subscribe to the /brokers/ids path in ZooKeeper where brokers are registered so that they get notified when brokers are added or removed. (Page 135) #✂️ 
{ #ref-824785892}


---
#### When a broker loses connectivity to ZooKeeper (usually as a result of the broker stopping, but this can also happen as a result of network partition or a long garbagecollection pause), the ephemeral node that the broker created when starting will be automatically removed from ZooKeeper.
>[!QUOTE]  
>Even though the node representing the broker is gone when the broker is stopped, the broker ID still exists in other data structures. For example, the list of replicas of each topic (see “Replication” on page 139) contains the broker IDs for the replica. (Page 136) #✂️ 
{ #ref-824785894}


---
>[!QUOTE]  
>The Controller (Page 136) #✂️ 
{ #ref-824785895}


---
>[!QUOTE]  
>The first broker that starts in the cluster becomes the controller by creating an ephemeral node in ZooKeeper called /controller (Page 136) #✂️ 
{ #ref-824785896}


---
>[!QUOTE]  
>When the controller broker is stopped or loses connectivity to ZooKeeper, the ephemeral node will disappear. This includes any scenario in which the ZooKeeper client used by the controller stops sending heartbeats to ZooKeeper for longer than zookeeper.session.timeout.ms (Page 136) #✂️ 
{ #ref-824785897}


---
>[!QUOTE]  
>The controller epoch in the message, which allows brokers to ignore messages from old controllers, is a form of zombie fencing. (Page 137) #✂️ 
{ #ref-824785898}


---
>[!QUOTE]  
>When the controller first comes up, it has to read the latest replica state map from ZooKeeper before it can start managing the cluster metadata and performing leader elections (Page 137) #✂️ 
{ #ref-824785899}


---
>[!QUOTE]  
>To summarize, Kafka uses ZooKeeper’s ephemeral node feature to elect a controller and to notify the controller when nodes join and leave the cluster. The controller is responsible for electing leaders among the partitions and replicas whenever it notices nodes join and leave the cluster. The controller uses the epoch number to prevent a “split brain” scenario where two nodes believe each is the current controller (Page 137) #✂️ 
{ #ref-824785900}


---
>[!QUOTE]  
>In the new architecture, the controller nodes are a Raft quorum that manages the log of metadata events. This log contains information about each change to the cluster metadata. Everything that is currently stored in ZooKeeper, such as topics, partitions, ISRs, configurations, and so on, will be stored in this log (Page 139) #✂️ 
{ #ref-824785901}


---
>[!QUOTE]  
>Brokers will register with the controller quorum and will remain registered until unregistered by an admin, so once a broker shuts down, it is offline but still regis‐ tered. Brokers that are online but are not up-to-date with the latest metadata will be fenced and will not be able to serve client requests. The new fenced state will prevent cases where a client produces events to a broker that is no longer a leader but is too out-of-date to be aware that it isn’t a leader (Page 139) #✂️ 
{ #ref-824785902}


---
#### Replication
>[!QUOTE]  
>Leader replica Each partition has a single replica designated as the leader. All produce requests go through the leader to guarantee consistency. Clients can consume from either the lead replica or its followers. (Page 140) #✂️ 
{ #ref-824785904}


---
>[!QUOTE]  
>Follower replica All replicas for a partition that are not leaders are called followers. Unless config‐ ured otherwise, followers don’t serve client requests; their main job is to replicate messages from the leader and stay up-to-date with the most recent messages the leader has. If a leader replica for a partition crashes, one of the follower replicas will be promoted to become the new leader for the partition. (Page 140) #✂️ 
{ #ref-824785905}


---
>[!QUOTE]  
>The amount of time a follower can be inactive or behind before it is considered out of sync is controlled by the replica.lag.time.max.ms configuration parameter (Page 141) #✂️ 
{ #ref-824785906}


---
>[!QUOTE]  
>tion. We discuss this in depth in Chapter 7 when we discuss reliability guarantees. In (Page 141) #✂️ 
{ #ref-824785907}


---
>[!QUOTE]  
>In addition to the current leader, each partition has a preferred leader—the replica that was the leader when the topic was originally created. It is preferred because when partitions are first created, the leaders are balanced among brokers (Page 141) #✂️ 
{ #ref-824785908}


---
>[!QUOTE]  
>In addition to the current leader, each partition has a preferred leader—the replica that was the leader when the topic was originally created. It is preferred because when partitions are first created, the leaders are balanced among brokers. As a result, we expect that when the preferred leader is indeed the leader for all partitions in the clus‐ ter, load will be evenly balanced between brokers. By default, Kafka is configured with auto.leader.rebalance.enable=true, (Page 141) #✂️ 
{ #ref-824785909}


---
>[!QUOTE]  
>In addition to the current leader, each partition has a preferred leader—the replica that was the leader when the topic was originally created. It is preferred because when partitions are first created, the leaders are balanced among brokers. As a result, we expect that when the preferred leader is indeed the leader for all partitions in the clus‐ ter, load will be evenly balanced between brokers. By default, Kafka is configured with auto.leader.rebalance.enable=true (Page 141) #✂️ 
{ #ref-824785910}


---
>[!QUOTE]  
>All requests have a standard header that includes: • Request type (also called API key) • Request version (so the brokers can handle clients of different versions and respond accordingly) • Correlation ID: a number that uniquely identifies the request and also appears in the response and in the error logs (the ID is used for troubleshooting) • Client ID: used to identify the application that sent the request (Page 142) #✂️ 
{ #ref-824785911}


---
>[!QUOTE]  
>For each port the broker listens on, the broker runs an acceptor thread that creates a connection and hands it over to a processor thread for handling. The number of pro‐ cessor threads (also called network threads) is configurable. The network threads are responsible for taking requests from client connections, placing them in a request queue, and picking up responses from a response queue and sending them back to cli‐ ents. At times, responses to clients have to be delays—consumers only receive respon‐ ses when data is available, and admin clients receive a response to a DeleteTopic request after topic deletion is underway. The delayed responses are held in a purga‐ tory until they can be completed (Page 143) #✂️ 
{ #ref-824785912}


---
>[!QUOTE]  
>Produce requests Sent by producers and contain messages the clients write to Kafka brokers (Page 143) #✂️ 
{ #ref-824785913}


---
>[!QUOTE]  
>Fetch requests Sent by consumers and follower replicas when they read messages from Kafka brokers (Page 143) #✂️ 
{ #ref-824785914}


---
>[!QUOTE]  
>Admin requests Sent by admin clients when performing metadata operations such as creating and deleting topics (Page 143) #✂️ 
{ #ref-824785915}


---
>[!QUOTE]  
>How do the clients know where to send the requests? Kafka clients use another request type called a metadata request, which includes a list of topics the client is interested in. The server response specifies which partitions exist in the topics, the replicas for each partition, and which replica is the leader. Metadata requests can be sent to any broker because all brokers have a metadata cache that contains this information (Page 144) #✂️ 
{ #ref-824785916}


---
>[!QUOTE]  
>Clients typically cache this information and use it to direct produce and fetch requests to the correct broker for each partition. They also need to occasionally refresh this information (refresh intervals are controlled by the metadata. max.age.ms configuration parameter) by sending another metadata request so they know if the topic metadata changed (Page 144) #✂️ 
{ #ref-824785917}


---
>[!QUOTE]  
>if acks is set to all, the request will be stored in a buffer called purgatory until the leader observes that the follower replicas replicated the message, at which point a response is sent to the client. (Page 145) #✂️ 
{ #ref-824785918}


---
>[!QUOTE]  
>• A magic number indicating the current version of the message format (here we’re documenting v2). • The offset of the first message in the batch and the difference from the offset of the last message—those are preserved even if the batch is later compacted and some messages are removed. The offset of the first message is set to 0 when the producer creates and sends the batch. The broker that first persists this batch (the partition leader) replaces this with the real offset. • The timestamps of the first message and the highest timestamp in the batch. The timestamps can be set by the broker if the timestamp type is set to append time rather than create time. • Size of the batch, in bytes. • The epoch of the leader that received the batch (this is used when truncating messages after leader election; KIP-101 and KIP-279 explain the usage in detail). • Checksum for validating that the batch is not corrupted. • Sixteen bits indicating different attributes: compression type, timestamp type (timestamp can be set at the client or at the broker), and whether the batch is part of a transaction or is a control batch. • Producer ID, producer epoch, and the first sequence in the batch—these are all used for exactly-once guarantees. • And, of course, the set of messages that are part of the batch. (Page 154) #✂️ 
{ #ref-824785919}


---
>[!QUOTE]  
>Each record includes: • Size of the record, in bytes • Attributes—currently there are no record-level attributes, so this isn’t used • The difference between the offset of the current record and the first offset in the batch • The difference, in milliseconds, between the timestamp of this record and the first timestamp in the batch • The user payload: key, value, and headers (Page 154) #✂️ 
{ #ref-824785920}


---
>[!QUOTE]  
>If compaction is enabled when Kafka starts (using the awkwardly named log.cleaner.enabled configuration), each broker will start a compaction manager thread and a number of compaction threads. These are responsible for performing the compaction tasks. Each thread chooses the partition with the highest ratio of dirty messages to total partition size and cleans this partition (Page 157) #✂️ 
{ #ref-824785921}


---
### Reliable Data Delivery
#### Reliability Guarantees
>[!QUOTE]  
>Kafka provides order guarantee of messages in a partition. If message B was writ‐ ten after message A, using the same producer in the same partition, then Kafka guarantees that the offset of message B will be higher than message A, and that consumers will read message B after message A. (Page 162) #✂️ 
{ #ref-824785924}


---
>[!QUOTE]  
>Produced messages are considered “committed” when they were written to the partition on all its in-sync replicas (but not necessarily flushed to disk). Produc‐ ers can choose to receive acknowledgments of sent messages when the message was fully committed, when it was written to the leader, or when it was sent over the network (Page 162) #✂️ 
{ #ref-824785925}


---
>[!QUOTE]  
>Messages that are committed will not be lost as long as at least one replica remains alive. (Page 162) #✂️ 
{ #ref-824785926}


---
>[!QUOTE]  
>Consumers can only read messages that are committed. (Page 162) #✂️ 
{ #ref-824785927}


---
#### Replication
>[!QUOTE]  
>A replica is considered in sync if it is the leader for a partition, or if it is a follower that: • Has an active session with ZooKeeper—meaning that it sent a heartbeat to Zoo‐ Keeper in the last 6 seconds (configurable). • Fetched messages from the leader in the last 10 seconds (configurable). • Fetched the most recent messages from the leader in the last 10 seconds. That is, it isn’t enough that the follower is still getting messages from the leader; it must have had no lag at least once in the last 10 seconds (configurable (Page 163) #✂️ 
{ #ref-824785929}


---
#### Broker Confguration
>[!QUOTE]  
>So how do we determine the right number of replicas for a topic? There are a few key considerations: Availability A partition with just one replica will become unavailable even during a routine restart of a single broker. The more replicas we have, the higher availability we can expect. Durability Each replica is a copy of all the data in a partition. If a partition has a single rep‐ lica and the disk becomes unusable for any reason, we’ve lost all the data in the partition. With more copies, especially on different storage devices, the probabil‐ ity of losing all of them is reduced. Troughput With each additional replica, we multiply the inter-broker traffic. If we produce to a partition at a rate of 10 MBps, then a single replica will not generate any rep‐ lication traffic. If we have 2 replicas, then we’ll have 10 MBps replication traffic, with 3 replicas it will be 20 MBps, and with 5 replicas it will be 40 MBps. We need to take this into account when planning the cluster size and capacity. End-to-end latency Each produced record has to be replicated to all in-sync replicas before it is avail‐ able for consumers. In theory, with more replicas, there is higher probability that one of these replicas is a bit slow and therefore will slow the consumers down. In practice, if one broker becomes slow for any reason, it will slow down every cli‐ ent that tries using it, regardless of replication factor. (Page 165) #✂️ 
{ #ref-824785931}


---
>[!QUOTE]  
>Cost This is the most common reason for using a replication factor lower than 3 for noncritical data. The more replicas we have of our data, the higher the storage and network costs. Since many storage systems already replicate each block 3 times, it sometimes makes sense to reduce costs by configuring Kafka with a rep‐ lication factor of 2. Note that this will still reduce availability compared to a repli‐ cation factor of 3, but durability will be guaranteed by the storage device (Page 166) #✂️ 
{ #ref-824785932}


---
>[!QUOTE]  
>zookeeper.session.timeout.ms is the time interval during which a Kafka broker can stop sending heartbeats to ZooKeeper without ZooKeeper considering the broker dead and removing it from the cluster. In version 2.5.0, this value was increased from 6 seconds to 18 seconds, in order to increase the stability of Kafka clusters in cloud environments where network latencies show higher variance (Page 168) #✂️ 
{ #ref-824785933}


---
>[!QUOTE]  
>If a replica did not fetch from the leader or did not catch up to the latest messages on the leader for longer than replica.lag.time.max.ms, it will become out of sync. This was increased from 10 seconds to 30 seconds in release 2.5.0 to improve resilience of the cluster and avoid unnecessary flapping (Page 168) #✂️ 
{ #ref-824785934}


---
>[!QUOTE]  
>Kafka will flush messages to disk when rotating segments (by default 1 GB in size) and before restarts but will otherwise rely on Linux page cache to flush messages when it becomes full (Page 169) #✂️ 
{ #ref-824785935}


---
#### Using Consumers in a Reliable System
#### Validating System Reliability
### Exactly-Once Semantics
#### Idempotent Producer
>[!QUOTE]  
>When we enable the idempotent producer, each message will include a unique identi‐ fied producer ID (PID) and a sequence number. These, together with the target topic and partition, uniquely identify each message. Brokers use these unique identifiers to track the last five messages produced to every partition on the broker. To limit the number of previous sequence numbers that have to be tracked for each partition, we also require that the producers will use max.inflight.requests=5 or lower (the default is 5) (Page 182) #✂️ 
{ #ref-824785940}


---
>[!QUOTE]  
>The leader keeps updating its in-memory producer state with the five last sequence IDs every time a new message is produced. Follower replicas update their own inmemory buffers every time they replicate new messages from the leader. This means that when a follower becomes a leader, it already has the latest sequence numbers in memory, and validation of newly produced messages can continue without any issues or delays. (Page 184) #✂️ 
{ #ref-824785941}


---
>[!QUOTE]  
>Kafka’s idempotent producer only prevents duplicates in case of retries that are caused by the producer’s internal logic. Calling producer.send() twice with the same message will create a duplicate, and the idempotent producer won’t prevent it (Page 184) #✂️ 
{ #ref-824785942}


---
>[!QUOTE]  
>The idempotent producer will only prevent duplicates caused by the retry mechanism of the producer itself, whether the retry is (Page 185) #✂️ 
{ #ref-824785943}


---
>[!QUOTE]  
>Transactions are useful for any stream processing application where accuracy is important, and especially where stream processing includes aggregation and/or joins (Page 187) #✂️ 
{ #ref-824785944}


---
>[!QUOTE]  
>Exactly-once processing means that consuming, processing, and producing are done atomically. Either the offset of the original message is committed and the result is successfully produced or neither of these things happen. We need to make sure that partial results—where the offset is committed but the result isn’t produced, or vice versa—can’t happen. (Page 188) #✂️ 
{ #ref-824785945}


---
>[!QUOTE]  
>To use transactions and perform atomic multipartition writes, we use a transactional producer. A transactional producer is simply a Kafka producer that is configured with a transactional.id and has been initialized using initTransactions(). (Page 189) #✂️ 
{ #ref-824785946}


---
>[!QUOTE]  
>We control the consumption of messages that were written transactionally by setting the isolation.level configuration. If set to read_committed, calling consumer.poll() after subscribing to a set of topics will return messages that were either part of a successfully committed transaction or that were written nontransac‐ tionally; it will not return messages that were part of an aborted transaction or a transaction that is still open. The default isolation.level value, read_uncommitted, will return all records, including those that belong to open or aborted transactions. (Page 190) #✂️ 
{ #ref-824785947}


---
>[!QUOTE]  
>To guarantee that messages will be read in order, read_committed mode will not return messages that were produced after the point when the first still-open transac‐ tion began (known as the Last Stable Offset, or LSO). Those messages will be with‐ held until that transaction is committed or aborted by the producer, or until they reach transaction.timeout.ms (default of 15 minutes) and are aborted by the broker. Holding a transaction open for a long duration will introduce higher end-toend latency by delaying consumers. (Page 190) #✂️ 
{ #ref-824785948}


---
>[!QUOTE]  
>As explained earlier, transactions were added to Kafka to provide multipartition atomic writes (but not reads) and to fence zombie producers in stream processing applications. As a result, they provide exactly-once guarantees when used within chains of consume-process-produce stream processing tasks. In other contexts, trans‐ actions will either straight-out not work or will require additional effort in order to achieve the guarantees we want (Page 191) #✂️ 
{ #ref-824785949}


---
>[!QUOTE]  
>The most common and most recommended way to use transactions is to enable exactly-once guarantees in Kafka Streams. This way, we will not use transactions directly at all, but rather Kafka Streams will use them for us behind the scenes to pro‐ vide the guarantees we need. Transactions were designed with this use case in mind, so using them via Kafka Streams is the easiest and most likely to work as expected (Page 193) #✂️ 
{ #ref-824785950}


---
>[!QUOTE]  
>1. Log the existence of an ongoing transaction, including the partitions involved 2. Log the intent to commit or abort—once this is logged, we are doomed to com‐ mit or abort eventually 3. Write all the transaction markers to all the partitions 4. Log the completion of the transaction To implement this basic algorithm, Kafka needs a transaction log. We use an internal topic called __transaction_state. (Page 198) #✂️ 
{ #ref-824785951}


---
#### Performance of Transactions
### Building Data Pipelines
>[!QUOTE]  
>One of the most important considerations in a data pipeline is reconciling different data formats and data types. The data types supported vary among different databases and other storage systems. You may be loading XMLs and relational data into Kafka, using Avro within Kafka, and then need to convert data to JSON when writing it to Elasticsearch, to Parquet when writing to HDFS, and to CSV when writing to S3 (Page 206) #✂️ 
{ #ref-824785954}


---
>[!QUOTE]  
>Kafka itself and the Connect API are completely agnostic when it comes to data for‐ mats. (Page 206) #✂️ 
{ #ref-824785955}


---
>[!QUOTE]  
>Kafka Connect has its own in-memory objects that include data types and schemas, but as we’ll soon discuss, it allows for pluggable converters to allow storing these records in any format. This means that no matter which data format you use for Kafka, it does not restrict your choice of connectors. (Page 206) #✂️ 
{ #ref-824785956}


---
>[!QUOTE]  
>Many sources and sinks have a schema; we can read the schema from the source with the data, store it, and use it to validate compatibility or even update the schema in the sink database. (Page 206) #✂️ 
{ #ref-824785957}


---
>[!QUOTE]  
>In addition, when writing data from Kafka to external systems, sink connectors are responsible for the format in which the data is written to the external system. Some connectors choose to make this format pluggable. (Page 206) #✂️ 
{ #ref-824785958}


---
>[!QUOTE]  
>In addition, when writing data from Kafka to external systems, sink connectors are responsible for the format in which the data is written to the external system. Some connectors choose to make this format pluggable. For example, the S3 connector allows a choice between Avro and Parquet formats. (Page 206) #✂️ 
{ #ref-824785959}


---
>[!QUOTE]  
>Kafka Connect includes the Single Message Transformation feature, which trans‐ forms records while they are being copied from a source to Kafka, or from Kafka to a target. This includes routing messages to different topics, filtering messages, chang‐ ing data types, redacting specific fields, and more (Page 207) #✂️ 
{ #ref-824785960}


---
>[!QUOTE]  
>ELT stands for Extract-Load-Transform and means that the data pipeline does only minimal transformation (mostly around data type conversion), with the goal of mak‐ ing sure the data that arrives at the target is as similar as possible to the source data. (Page 207) #✂️ 
{ #ref-824785961}


---
>[!QUOTE]  
>ETL, which stands for Extract-Transform-Load, means that the data pipeline is responsible for making mod‐ ifications to the data as it passes through. It has the perceived benefit of saving time and storage because you don’t need to store the data, modify it, and store it again. Depending on the transformations, this benefit is sometimes real, but sometimes it shifts the burden of computation and storage to the data pipeline itself, which may or may not be desirable. (Page 207) #✂️ 
{ #ref-824785962}


---
>[!QUOTE]  
>In terms of data pipelines, the main security concerns are usually: • Who has access to the data that is ingested into Kafka? • Can we make sure the data going through the pipe is encrypted? This is mainly a concern for data pipelines that cross datacenter boundaries. • Who is allowed to make modifications to the pipelines? • If the data pipeline needs to read or write from access-controlled locations, can it authenticate properly? • Is our PII (Personally Identifiable Information) handling compliant with laws and regulations regarding its storage, access and use? (Page 208) #✂️ 
{ #ref-824785963}


---
>[!QUOTE]  
>These days it is not recommended to store credentials in configuration files, since this means that the configuration files have to be handled with extra care and have restric‐ ted access. A common solution is to use an external secret management system such as HashiCorp Vault. Kafka Connect includes support for external secret configura‐ tion. (Page 208) #✂️ 
{ #ref-824785964}


---
>[!QUOTE]  
>If you need to connect Kafka to a datastore and a connector does not exist yet, you can choose between writing an app using the Kafka clients or the Connect API. Con‐ nect is recommended because it provides out-of-the-box features like configuration management, offset storage, parallelization, error handling, support for different data types, and standard management REST APIs (Page 210) #✂️ 
{ #ref-824785965}


---
>[!QUOTE]  
>As we’ve seen, Kafka clients are clients embedded in your own application. It allows your application to write data to Kafka or to read data from Kafka. Use Kafka clients when you can modify the code of the application that you want to connect an appli‐ cation to and when you want to either push data into Kafka or pull data from Kafka. (Page 210) #✂️ 
{ #ref-824785966}


---
>[!QUOTE]  
>You will use Connect to connect Kafka to datastores that you did not write and whose code or APIs you cannot or will not modify. Connect will be used to pull data from the external datastore into Kafka or push data from Kafka to an external store (Page 210) #✂️ 
{ #ref-824785967}


---
>[!QUOTE]  
>Kafka Connect is a part of Apache Kafka and provides a scalable and reliable way to copy data between Kafka and other datastores. It provides APIs and a runtime to develop and run connector plug-ins—libraries that Kafka Connect executes and that are responsible for moving the data (Page 211) #✂️ 
{ #ref-824785968}


---
>[!QUOTE]  
>Kafka Connect runs as a cluster of worker pro‐ cesses. You install the connector plug-ins on the workers and then use a REST API to configure and manage connectors, which run with a specific configuration (Page 211) #✂️ 
{ #ref-824785969}


---
>[!QUOTE]  
>Connectors start additional tasks to move large amounts of data in parallel and use the available resources on the worker nodes more efficiently (Page 211) #✂️ 
{ #ref-824785970}


---
>[!QUOTE]  
>Source connector tasks just need to read data from the source system and provide Connect data objects to the worker processes (Page 211) #✂️ 
{ #ref-824785971}


---
>[!QUOTE]  
>Sink connector tasks get connector data objects from the workers and are responsible for writing them to the target data system (Page 211) #✂️ 
{ #ref-824785972}


---
>[!QUOTE]  
>Kafka Connect uses convertors to support storing those data objects in Kafka in different formats—JSON format support is part of Apache Kafka, and the Confluent Schema Registry provides Avro, Protobuf, and JSON Schema converters (Page 211) #✂️ 
{ #ref-824785973}


---
>[!QUOTE]  
>Kafka Connect ships with Apache Kafka, so there is no need to install it separately (Page 211) #✂️ 
{ #ref-824785974}


---
>[!QUOTE]  
>For production use, especially if you are planning to use Connect to move large amounts of data or run many connectors, you should run Connect on separate servers from your Kafka brokers. In this case, install Apache Kafka on all the machines, and simply start the brokers on some servers and start Connect on other servers (Page 211) #✂️ 
{ #ref-824785975}


---
>[!QUOTE]  
>Starting a Connect worker is very similar to starting a broker—you call the start script with a properties file: bin/connect-distributed.sh config/connect-distributed.properties (Page 211) #✂️ 
{ #ref-824785976}


---
>[!QUOTE]  
>bootstrap.servers A list of Kafka brokers that Connect will work with. Connectors will pipe their data either to or from those brokers. You don’t need to specify every broker in the cluster, but it’s recommended to specify at least three. (Page 212) #✂️ 
{ #ref-824785977}


---
>[!QUOTE]  
>group.id All workers with the same group ID are part of the same Connect cluster. A con‐ nector started on the cluster will run on any worker, and so will its tasks (Page 212) #✂️ 
{ #ref-824785978}


---
>[!QUOTE]  
>plugin.path Kafka Connect uses a pluggable architecture where connectors, converters, trans‐ formations, and secret providers can be downloaded and added to the platform. In order to do this, Kafka Connect has to be able to find and load those plug-ins. We can configure one or more directories as locations where connectors and their dependencies can be found. (Page 212) #✂️ 
{ #ref-824785979}


---
>[!QUOTE]  
>key.converter and value.converter Connect can handle multiple data formats stored in Kafka. The two configura‐ tions set the converter for the key and value part of the message that will be stored in Kafka. The default is JSON format using the JSONConverter included in Apache Kafka. These configurations can also be set to AvroConverter, Protobuf Converter, or JscoSchemaConverter, which are part of the Confluent Schema Registry. (Page 212) #✂️ 
{ #ref-824785980}


---
>[!QUOTE]  
>key.converter and value.converter Connect can handle multiple data formats stored in Kafka. The two configura‐ tions set the converter for the key and value part of the message that will be stored in Kafka. The default is JSON format using the JSONConverter included in Apache Kafka. These configurations can also be set to AvroConverter, Protobuf Converter, or JscoSchemaConverter, which are part of the Confluent Schema Registry. Some converters include converter-specific configuration parameters. You need to prefix these parameters with key.converter. or value.converter., depend‐ ing on whether you want to apply them to the key or value converter. For example, JSON messages can include a schema or be schema-less. To support either, you can set key.converter.schemas.enable=true or false, respectively. The same configuration can be used for the value converter by setting value.converter.schemas.enable to true or false (Page 212) #✂️ 
{ #ref-824785981}


---
>[!QUOTE]  
>key.converter and value.converter Connect can handle multiple data formats stored in Kafka. The two configura‐ tions set the converter for the key and value part of the message that will be stored in Kafka. The default is JSON format using the JSONConverter included in Apache Kafka. These configurations can also be set to AvroConverter, Protobuf Converter, or JscoSchemaConverter, which are part of the Confluent Schema Registry. Some converters include converter-specific configuration parameters. You need to prefix these parameters with key.converter. or value.converter., depend‐ ing on whether you want to apply them to the key or value converter. For example, JSON messages can include a schema or be schema-less. To support either, you can set key.converter.schemas.enable=true or false, respectively. The same configuration can be used for the value converter by setting value.converter.schemas.enable to true or false (Page 212) #✂️ 
{ #ref-824785982}


---
>[!QUOTE]  
>rest.host.name and rest.port Connectors are typically configured and monitored through the REST API of Kafka Connect. You can configure the specific port for the REST API. (Page 213) #✂️ 
{ #ref-824785983}


---
>[!QUOTE]  
>Take note that Kafka Connect also has a standalone mode. It is similar to distributed mode—you just run bin/connectstandalone.sh instead of bin/connect-distributed.sh. You can also pass in a connector configuration file on the command line instead of through the REST API (Page 214) #✂️ 
{ #ref-824785984}


---
>[!QUOTE]  
>Note the changes from the source configuration: the class we are using is now File StreamSink rather than FileStreamSource. We still have a file property, but now it refers to the destination file rather than the source of the records, and instead of specifying a topic, you specify topics. Note the plurality—you can write multiple top‐ ics into one file with the sink, while the source only allows writing into one topic (Page 216) #✂️ 
{ #ref-824785985}


---
>[!QUOTE]  
>Copying records from MySQL to Kafka and from there to Elastic is rather useful on its own, but ETL pipelines typically involve a transformation step. In the Kafka eco‐ system we separate transformations to single message transformations (SMTs), which are stateless, and stream processing, which can be stateful (Page 223) #✂️ 
{ #ref-824785986}


---
>[!QUOTE]  
>SMTs can be done within Kafka Connect transforming messages while they are being copied, often without writing any code. More complex transformations, which typically involve joins or aggregation, will require the stateful Kafka Streams framework. We’ll discuss Kafka Streams in a later chapter. (Page 223) #✂️ 
{ #ref-824785987}


---
>[!QUOTE]  
>Apache Kafka includes the following SMTs: Cast Change data type of a field. MaskField Replace the contents of a field with null. This is useful for removing sensitive or personally identifying data. Filter Drop or include all messages that match a specific condition. Built-in conditions include matching on a topic name, a particular header, or whether the message is a tombstone (that is, has a null value). Flatten Transform a nested data structure to a flat one. This is done by concatenating all the names of all fields in the path to a specific value (Page 223) #✂️ 
{ #ref-824785988}


---
>[!QUOTE]  
>HeaderFrom Move or copy fields from the message into the header. InsertHeader Add a static string to the header of each message. InsertField Add a new field to a message, either using values from its metadata such as offset, or with a static value. RegexRouter Change the destination topic using a regular expression and a replacement string. ReplaceField Remove or rename a field in the message. TimestampConverter Modify the time format of a field—for example, from Unix Epoch to a String. TimestampRouter Modify the topic based on the message timestamp. This is mostly useful in sink connectors when we want to copy messages to specific table partitions based on their timestamp and the topic field is used to find an equivalent dataset in the destination system. (Page 224) #✂️ 
{ #ref-824785989}


---
>[!QUOTE]  
>Connector plug-ins implement the Connector API, which includes two parts: Connectors The connector is responsible for three important things: • Determining how many tasks will run for the connector • Deciding how to split the data-copying work between the tasks • Getting configurations for the tasks from the workers and passing them along (Page 226) #✂️ 
{ #ref-824785990}


---
>[!QUOTE]  
>For example, the JDBC source connector will connect to the database, discover the existing tables to copy, and based on that decide how many tasks are needed—choosing the lower of tasks.max configuration and the number of tables. (Page 226) #✂️ 
{ #ref-824785991}


---
>[!QUOTE]  
>Once it decides how many tasks will run, it will generate a configuration for each task—using both the connector configuration (e.g., connection.url) and a list of tables it assigns for each task to copy. The taskConfigs() method returns a list of maps (i.e., a configuration for each task we want to run). The workers are then responsible for starting the tasks and giving each one its own unique configuration so that it will copy a unique subset of tables from the data‐ base. Note that when you start the connector via the REST API, it may start on any node, and subsequently the tasks it starts may also execute on any node. (Page 226) #✂️ 
{ #ref-824785992}


---
>[!QUOTE]  
>Tasks Tasks are responsible for actually getting the data in and out of Kafka. All tasks are initialized by receiving a context from the worker. Source context includes an object that allows the source task to store the offsets of source records (e.g., in the file connector, the offsets are positions in the file; in the JDBC source connector, the offsets can be a timestamp column in a table). Context for the sink connector includes methods that allow the connector to control the records it receives from Kafka—this is used for things like applying back pressure and retrying and stor‐ ing offsets externally for exactly-once delivery. After tasks are initialized, they are started with a Properties object that contains the configuration the Connector created for the task (Page 226) #✂️ 
{ #ref-824785993}


---
>[!QUOTE]  
>Once tasks are started, source tasks poll an external system and return lists of records that the worker sends to Kafka brokers. Sink tasks receive records from Kafka through the worker and are responsible for writing the records to an external system (Page 226) #✂️ 
{ #ref-824785994}


---
>[!QUOTE]  
>Workers Kafka Connect’s worker processes are the “container” processes that execute the con‐ nectors and tasks. They are responsible for handling the HTTP requests that define connectors and their configuration, as well as for storing the connector configuration in an internal Kafka topic, starting the connectors and their tasks, and passing the appropriate configurations along (Page 227) #✂️ 
{ #ref-824785995}


---
>[!QUOTE]  
>If a worker process is stopped or crashes, other workers in a Connect cluster will recognize that (using the heartbeats in Kafka’s con‐ sumer protocol) and reassign the connectors and tasks that ran on that worker to the remaining workers. If a new worker joins a Connect cluster, other workers will notice that and assign connectors or tasks to it to make sure load is balanced among all workers fairly. Workers are also responsible for automatically committing offsets for both source and sink connectors into internal Kafka topics and for handling retries when tasks throw errors (Page 227) #✂️ 
{ #ref-824785996}


---
>[!QUOTE]  
>The best way to understand workers is to realize that connectors and tasks are responsible for the “moving data” part of data integration, while the workers are responsible for the REST API, configuration management, reliability, high availabil‐ ity, scaling, and load balancing (Page 227) #✂️ 
{ #ref-824785997}


---
>[!QUOTE]  
>Converters and Connect’s data model The last piece of the Connect API puzzle is the connector data model and the con‐ verters. Kafka’s Connect API includes a data API, which includes both data objects and a schema that describes that data. For example, the JDBC source reads a column from a database and constructs a Connect Schema object based on the data types of the columns returned by the database. It then uses the schema to construct a Struct that contains all the fields in the database record. For each column, we store the col‐ umn name and the value in that column. Every source connector does something similar—read an event from the source system and generate a Schema and Value pair. Sink connectors do the opposite—get a Schema and Value pair and use the Schema to parse the values and insert them into the target system. (Page 227) #✂️ 
{ #ref-824785998}


---
>[!QUOTE]  
>Though source connectors know how to generate objects based on the Data API, there is still a question of how Connect workers store these objects in Kafka. This is where the converters come in. When users configure the worker (or the connector), they choose which converter they want to use to store data in Kafka. At the moment, the available choices are primitive types, byte arrays, strings, Avro, JSON, JSON sche‐ mas, or Protobufs (Page 228) #✂️ 
{ #ref-824785999}


---
>[!QUOTE]  
>The opposite process happens for sink connectors. When the Connect worker reads a record from Kafka, it uses the configured converter to convert the record from the format in Kafka (i.e., primitive types, byte arrays, strings, Avro, JSON, JSON schema, or Protobufs) to the Connect Data API record and then passes it to the sink connec‐ tor, which inserts it into the destination system (Page 228) #✂️ 
{ #ref-824786000}


---
>[!QUOTE]  
>For source connectors, this means that the records the connector returns to the Con‐ nect workers include a logical partition and a logical offset. Those are not Kafka par‐ titions and Kafka offsets but rather partitions and offsets as needed in the source system (Page 228) #✂️ 
{ #ref-824786001}


---
>[!QUOTE]  
>When the source connector returns a list of records, which includes the source parti‐ tion and offset for each record, the worker sends the records to Kafka brokers. If the brokers successfully acknowledge the records, the worker then stores the offsets of the records it sent to Kafka (Page 228) #✂️ 
{ #ref-824786002}


---
>[!QUOTE]  
>pluggable and is usually a Kafka topic; you can control the topic name with the offset.storage.topic configuration. In addition, Connect uses Kafka topics to store the configuration of all the connectors we’ve created and the status of each con‐ nector—these use names configured by config.storage.topic and status. storage.topic, respectively (Page 229) #✂️ 
{ #ref-824786004}


---
>[!QUOTE]  
>Sink connectors have an opposite but similar workflow: they read Kafka records, which already have a topic, partition, and offset identifiers. Then they call the connector put() method that should store those records in the destination system. If the connector reports success, they commit the offsets they’ve given to the connector back to Kafka, using the usual consumer commit methods (Page 229) #✂️ 
{ #ref-824786005}


---
### Cross-Cluster Data Mirroring
>[!QUOTE]  
>Regional and central clusters In some cases, the company has one or more datacenters in different geographi‐ cal regions, cities, or continents. (Page 234) #✂️ 
{ #ref-824786007}


---
>[!QUOTE]  
>High availability (HA) and disaster recovery (DR) The applications run on just one Kafka cluster and don’t need data from other locations, but you are concerned about the possibility of the entire cluster becoming unavailable for some reason (Page 234) #✂️ 
{ #ref-824786008}


---
>[!QUOTE]  
>Regulatory compliance Companies operating in different countries may need to use different configura‐ tions and policies to conform to legal and regulatory requirements in each coun‐ try (Page 234) #✂️ 
{ #ref-824786009}


---
>[!QUOTE]  
>Cloud migrations Many companies these days run their business in both an on-premises datacenter and a cloud provider. Often, applications run on multiple regions of the cloud provider for redundancy, and sometimes multiple cloud providers are used (Page 234) #✂️ 
{ #ref-824786010}


---
#### Use Cases of Cross-Cluster Mirroring
>[!QUOTE]  
>Aggregation of data from edge clusters Several industries, including retail, telecommunications, transportation, and healthcare, generate data from small devices with limited connectivity. An aggre‐ gate cluster with high availability can be used to support analytics and other use cases for data from a large number of edge clusters (Page 235) #✂️ 
{ #ref-824786011}


---
#### Multicluster Architectures
##### Some Realities of Cross-Datacenter Communication
>[!QUOTE]  
>High latencies Latency of communication between two Kafka clusters increases as the distance and the number of network hops between the two clusters increase (Page 235) #✂️ 
{ #ref-824786015}


---
>[!QUOTE]  
>Limited bandwidth Wide area networks (WANs) typically have far lower available bandwidth than what you’ll see inside a single datacenter, and the available bandwidth can vary from minute to minute (Page 235) #✂️ 
{ #ref-824786016}


---
>[!QUOTE]  
>Higher costs Regardless of whether you are running Kafka on premise or in the cloud, there are higher costs to communicate between clusters. This is partly because the bandwidth is limited and adding bandwidth can be prohibitively expensive, and also because of the prices vendors charge for transferring data among datacen‐ ters, regions, and clouds. (Page 235) #✂️ 
{ #ref-824786017}


---
>[!QUOTE]  
>We’ll talk more about tuning Kafka for cross-datacenter communication, but the fol‐ lowing principles will guide most of the architectures we’ll discuss next: • No less than one cluster per datacenter. • Replicate each event exactly once (barring retries due to errors) between each pair of datacenters. • When possible, consume from a remote datacenter rather than produce to a remote datacenter. (Page 236) #✂️ 
{ #ref-824786018}


---
### Securing Kafka
>[!QUOTE]  
>A secure deployment must guarantee: Client authenticity When Alice establishes a client connection to the broker, the broker should authenticate the client to ensure that the message is really coming from Alice. Server authenticity Before sending a message to the leader broker, Alice’s client should verify that the connection is to the real broker. Data privacy All connections where the message flows, as well as all disks where messages are stored, should be encrypted or physically secured to prevent eavesdroppers from reading the data and to ensure that data cannot be stolen. Data integrity Message digests should be included for data transmitted over insecure networks to detect tampering. Access control Before writing the message to the log, the leader broker should verify that Alice is authorized to write to customerOrders. Before returning messages to Bob’s con‐ sumer, the broker should verify that Bob is authorized to read from the topic. If Bob’s consumer uses group management, the broker should also verify that Bob has access to the consumer group. Auditability An audit trail that shows all operations that were performed by brokers, Alice, Bob, and other clients should be logged. Availability Brokers should apply quotas and limits to avoid some users hogging all the avail‐ able bandwidth or overwhelming the broker with denial-of-service attacks. Zoo‐ Keeper should be locked down to ensure availability of the Kafka cluster since broker availability is dependent on ZooKeeper availability and the integrity of metadata stored in ZooKeeper. (Page 267) #✂️ 
{ #ref-824786020}


---
>[!QUOTE]  
>Kafka supports four security protocols using two standard technologies, TLS and SASL. Transport Layer Security (TLS), commonly referred to by the name of its pre‐ decessor, Secure Sockets Layer (SSL), supports encryption as well as client and server authentication. Simple Authentication and Security Layer (SASL) is a framework for providing authentication using different mechanisms in connection-oriented proto‐ cols. Each Kafka security protocol combines a transport layer (PLAINTEXT or SSL) with an optional authentication layer (SSL or SASL): PLAINTEXT PLAINTEXT transport layer with no authentication. Is suitable only for use within private networks for processing data that is not sensitive since no authen‐ tication or encryption is used. SSL SSL transport layer with optional SSL client authentication. Is suitable for use in insecure networks since client and server authentication as well as encryption are supported. SASL_PLAINTEXT PLAINTEXT transport layer with SASL client authentication. Some SASL mech‐ anisms also support server authentication. Does not support encryption and hence is suitable only for use within private networks. SASL_SSL SSL transport layer with SASL authentication. Is suitable for use in insecure net‐ works since client and server authentication as well as encryption are supported (Page 268) #✂️ 
{ #ref-824786021}


---
>[!QUOTE]  
>Kafka brokers support the following SASL mechanisms out of the box with customizable callbacks to integrate with existing security infrastructure: GSSAPI Kerberos authentication is supported using SASL/GSSAPI and can be used to integrate with Kerberos servers like Active Directory or OpenLDAP. PLAIN Username/password authentication that is typically used with a custom serverside callback to verify passwords from an external password store. SCRAM-SHA-256 and SCRAM-SHA-512 Username/password authentication available out of the box with Kafka without the need for additional password stores. OAUTHBEARER Authentication using OAuth bearer tokens that is typically used with custom call‐ backs to acquire and validate tokens granted by standard OAuth servers (Page 275) #✂️ 
{ #ref-824786022}


---
>[!QUOTE]  
>SASL/GSSAPI Kerberos is a widely used network authentication protocol that uses strong cryptogra‐ phy to support secure mutual authentication over an insecure network. Generic Secu‐ rity Service Application Program Interface (GSS-API) is a framework for providing security services to applications using different authentication mechanisms. RFC-4752 introduces the SASL mechanism GSSAPI for authentication using GSSAPI’s Kerberos V5 mechanism. The availability of open source as well as enterprisegrade commercial implementations of Kerberos servers has made Kerberos a popular choice for authentication across many sectors with strict security requirements. Kafka supports Kerberos authentication using SASL/GSSAPI. Confguring SASL/GSSAPI. Kafka uses GSSAPI security providers included in the Java runtime environment to support secure authentication using Kerberos. JAAS config‐ uration for GSSAPI includes the path of a keytab file that contains the mapping of principals to their long-term keys in encrypted form. To configure GSSAPI for brok‐ ers, create a keytab for each broker with a principal that includes the broker’s host‐ name. Broker hostnames are verified by clients to ensure server authenticity and prevent man-in-the-middle attacks. Kerberos requires a secure DNS service for host name lookup during authentication. In deployments where forward and reverse lookup do not match, the Kerberos configuration file krb5.conf on clients can be con‐ figured to set rdns=false to disable reverse lookup. JAAS configuration for each broker should include the Kerberos V5 login module from the Java runtime, the path‐ name of the keytab file, and the full broker principal (Page 276) #✂️ 
{ #ref-824786023}


---
>[!QUOTE]  
>Going back to the example data flow at the start of this chapter, we reviewed the options available for different aspects of security throughout the flow: Client authenticity When Alice’s client establishes connection to a Kafka broker, a listener using SASL or SSL with client authentication can verify that the connection is really from Alice and not an imposter. Reauthentication can configured to limit expo‐ sure in case a user is compromised. (Page 303) #✂️ 
{ #ref-824786024}


---
>[!QUOTE]  
>Server authenticity Alice’s client can verify that its connection is to the genuine broker using SSL with hostname validation or using SASL mechanisms with mutual authentica‐ tion, like Kerberos or SCRAM. Data privacy Use of SSL to encrypt data in transit protects data from eavesdroppers. Disk or volume encryption protects data at rest even if the disk is stolen. For highly sensi‐ tive data, end-to-end encryption provides fine-grained data access control and ensures that cloud providers and platform administrators with physical access to network and disks cannot access the data. Data integrity SSL can be used to detect tampering of data over an insecure network. Digital signatures can be included in messages to verify integrity when using end-to-end encryption. Access control Every operation performed by Alice, Bob, and even brokers is authorized using a customizable authorizer. Kafka has a built-in authorizer that enables fine-grained access control using ACLs. Auditability Authorizer logs and request logs can be used to track operations and attempted operations for auditing and anomaly detection. Availability A combination of quotas and configuration options to manage connections can be used to protect brokers from denial-of-service attacks. ZooKeeper can be secured using SSL, SASL, and ACLs to ensure that the metadata needed to ensure the availability of Kafka brokers is secure. (Page 304) #✂️ 
{ #ref-824786025}


---
### Administering Kafka
#### Topic Operations
>[!QUOTE]  
>The --describe command also has several useful options for filtering the output. These can be helpful for diagnosing cluster issues more easily. For these commands we generally do not specify the --topic argument because the intention is to find all topics or partitions in a cluster that match the criteria. These options will not work with the list command. Here is a list of useful pairings to use: --topics-with-overrides This will describe only the topics that have configurations that differ from the cluster defaults. (Page 308) #✂️ 
{ #ref-824786031}


---
>[!QUOTE]  
>-exclude-internal The previously mentioned command will remove all topics from the list that begin with the double underscore naming convention. The following commands are used to help find topic partitions that may have problems: --under-replicated-partitions This shows all partitions where one or more of the replicas are not in sync with the leader. This isn’t necessarily bad, as cluster maintenance, deployments, and rebalances will cause under-replicated partitions (or URPs) but is something to be aware of. --at-min-isr-partitions This shows all partitions where the number of replicas, including the leader, exactly match the setting for minimum in-sync replicas (ISRs). These topics are still available for producer or consumer clients, but all redundancy has been lost, and they are in danger of becoming unavailable. --under-min-isr-partitions This shows all partitions where the number of ISRs is below the configured mini‐ mum for successful produce actions. These partitions are effectively in read-only mode and cannot be produced to. --unavailable-partitions This shows all topic partitions without a leader. This is a serious situation and indicates that the partition is offline and unavailable for producer or consumer clients. (Page 309) #✂️ 
{ #ref-824786032}


---
#### Consumer Groups
>[!QUOTE]  
>Here is an example of exporting the offsets for the topic “my-topic” that is being con‐ sumed by the consumer group named “my-consumer” to a file named ofsets.csv: # kafka-consumer-groups.sh --bootstrap-server localhost:9092 --export --group my-consumer --topic my-topic --reset-offsets --to-current --dry-run > offsets.csv (Page 314) #✂️ 
{ #ref-824786033}


---
##### In the following example, we import the offsets for the consumer group named “myconsumer” from the file we created in the last example named ofsets.csv: # kafka-consumer-groups.sh --bootstrap-server localhost:9092 --reset-offsets --group my-consumer --from-file offsets.csv --execute
#### Dynamic Confguration Changes
>[!QUOTE]  
>Overriding Topic Confguration Defaults (Page 315) #✂️ 
{ #ref-824786042}


---
>[!QUOTE]  
>The format of the command to change a topic configuration is: kafka-configs.sh --bootstrap-server localhost:9092 --alter --entity-type topics --entity-name <topic-name> --add-config <key>=<value>[,<key>=<value>... (Page 316) #✂️ 
{ #ref-824786038}


---
>[!QUOTE]  
>Here is an example of setting the retention for the topic named “my-topic” to 1 hour (3,600,000 ms): # kafka-configs.sh --bootstrap-server localhost:9092 --alter --entity-type topics --entity-name my-topic --add-config retention.ms=3600000 Updated config for topic: "my-topic". (Page 316) #✂️ 
{ #ref-824786039}


---
>[!QUOTE]  
>Confguration key Description cleanup.policy If set to compact, the messages in this topic will be discarded and only the most recent message with a given key is retained (log compacted). compression.type The compression type used by the broker when writing message batches for this topic to disk. delete.retention.ms How long, in milliseconds, deleted tombstones will be retained for this topic. Only valid for log compacted topics. file.delete.delay.ms How long, in milliseconds, to wait before deleting log segments and indices for this topic from disk. flush.messages How many messages are received before forcing a fush of this topic’s messages to disk. flush.ms How long, in milliseconds, before forcing a fush of this topic’s messages to disk.follower.replication. throttled.replicas A list of replicas for which log replication should be throttled by the follower. index.interval.bytes How many bytes of messages can be produced between entries in the log segment’s index.leader.replication. throttled.replica A list of replicas for which log replication should be throttled by the leader. max.compaction.lag.ms Maximum time limit a message won’t be eligible for compaction in the log. max.message.bytes The maximum size of a single message for this topic, in bytes. message.downconver sion.enable Allows the message format version to be down-converted to the previous version if enabled with some overhead. message.format.version The message format version that the broker will use when writing messages to disk. Must be a valid API version number.message.timestamp. difference.max.ms The maximum allowed diference, in milliseconds, between the message timestamp and the broker timestamp when the message is received. This is only valid if the message.timestamp.type is set to CreateTime. (Page 316) #✂️ 
{ #ref-824786040}


---
>[!QUOTE]  
>Confguration key Description message.timestamp.type Which timestamp to use when writing messages to disk. Current values are Create Time for the timestamp specifed by the client and LogAppendTime for the time when the message is written to the partition by the broker.min.cleanable. dirty.ratio How frequently the log compactor will attempt to compact partitions for this topic, expressed as a ratio of the number of uncompacted log segments to the total number of log segments. Only valid for log compacted topics. min.compaction.lag.ms Minimum time a message will remain uncompacted in the log. min.insync.replicas The minimum number of replicas that must be in sync for a partition of the topic to be considered available. preallocate If set to true, log segments for this topic should be preallocated when a new segment is rolled. retention.bytes The amount of messages, in bytes, to retain for this topic. retention.ms How long messages should be retained for this topic, in milliseconds. segment.bytes The amount of messages, in bytes, that should be written to a single log segment in a partition. segment.index.bytes The maximum size, in bytes, of a single log segment index. segment.jitter.ms A maximum number of milliseconds that is randomized and added to segment.ms when rolling log segments. segment.ms How frequently, in milliseconds, the log segment for each partition should be rotated.unclean.leader. election.enable If set to false, unclean leader elections will not be permitted for this topic (Page 317) #✂️ 
{ #ref-824786041}


---
##### Overriding Client and User Confguration Defaults
>[!QUOTE]  
>Confguration key Description consumer_bytes_rate The amount of messages, in bytes, that a single client ID is allowed to consume from a single broker in one second. producer_bytes_rate The amount of messages, in bytes, that a single client ID is allowed to produce to a single broker in one second. controller_mutations_rate The rate at which mutations are accepted for the create topics request, the create partitions request, and the delete topics request. The rate is accumulated by the number of partitions created or deleted. request_percentage The percentage per quota window (out of a total of (num.io.threads + num.network.threads) × 100%) for requests from the user or client (Page 318) #✂️ 
{ #ref-824786044}


---
##### Overriding Broker Confguration Defaults
>[!QUOTE]  
>min.insync.replicas Adjusts the minimum number of replicas that need to acknowledge a write for a produce request to be successful when producers have set acks to all (or –1) (Page 318) #✂️ 
{ #ref-824786046}


---
>[!QUOTE]  
>unclean.leader.election.enable Allows replicas to be elected as leader even if it results in data loss. This is useful when it is permissible to have some lossy data, or to turn on for short times to unstick a Kafka cluster if unrecoverable data loss cannot be avoided. max.connections The maximum number of connections allowed to a broker at any time. We can also use max.connections.per.ip and max.connections.per.ip.overrides for more fine-tuned throttling (Page 319) #✂️ 
{ #ref-824786047}


---
#### Producing and Consuming
>[!QUOTE]  
>The console producer has many command-line arguments available to use with the --producer-property option for adjusting its behavior. Some of the more useful options are: --batch-size Specifies the number of messages sent in a single batch if they are not being sent synchronously. --timeout If a producer is running in asynchronous mode, this provides the max amount of time waiting for the batch size before producing to avoid long waits on lowproducing topics. --compression-codec <string> Specify the type of compression to be used when producing messages. Valid types can be one of the following: none, gzip, snappy, zstd, or lz4. The default value is gzip. --sync Produce messages synchronously, waiting for each message to be acknowledged before sending the next one. Producing and Consuming | 321 (Page 321) #✂️ 
{ #ref-824786048}


---
>[!QUOTE]  
>Checking Tool Versions It is very important to use a consumer that is the same version as your Kafka cluster. Older console consumers can potentially dam‐ age the cluster by interacting with the cluster or ZooKeeper in incorrect ways. As in other commands, the connection string to the cluster will be the --bootstrapserver option; however, you can choose from two options for selecting the topics to consume: --topic (Page 323) #✂️ 
{ #ref-824786050}


---
>[!QUOTE]  
>--topic Specifies a single topic to consume from. --whitelist A regular expression matching all topics to consume from (remember to prop‐ erly escape the regex so that it is not processed improperly by the shell) (Page 323) #✂️ 
{ #ref-824786051}


---
>[!QUOTE]  
>--formatter <classname> Specifies a message formatter class to be used to decode the messages. This defaults to kafka.tools.DefaultMessageFormatter. --from-beginning Consume messages in the topic(s) specified from the oldest offset. Otherwise, consumption starts from the latest offset. --max-messages <int> The maximum number of messages to consume before exiting. --partition <int> Consume only from the partition with the ID given. --offset The offset ID to consume from, if provided (<int>). Other valid options are earliest, which will consume from the beginning, and latest, which will start consuming from the most recent offset. --skip-message-on-error Skip a message if there is an error when processing instead of halting. Useful for debugging. (Page 324) #✂️ 
{ #ref-824786052}


---
>[!QUOTE]  
>kafka.tools.LoggingMessageFormatter Outputs messages using the logger, rather than standard out. Messages are printed at the INFO level and include the timestamp, key, and value. kafka.tools.ChecksumMessageFormatter Prints only message checksums. kafka.tools.NoOpMessageFormatter Consumes messages but does not output them at all. (Page 324) #✂️ 
{ #ref-824786053}


---
>[!QUOTE]  
>The kafka.tools.DefaultMessageFormatter also has several useful options that can be passed using the --property command-line option, shown in Table 12-4. Table 12-4. Message formatter properties Property Description print.timestamp Set to true to display the timestamp of each message (if available). print.key Set to true to display the message key in addition to the value. print.offset Set to true to display the message ofset in addition to the value. print.partition Set to true to display the topic partition a message is consumed from. key.separator Specify the delimiter character to use between the message key and message value when printing. line.separator Specify the delimiter character to use between messages. key.deserializer Provide a class name that is used to deserialize the message key before printing. value.deserializer Provide a class name that is used to deserialize the message value before printing. (Page 325) #✂️ 
{ #ref-824786054}


---
#### Partition Management
>[!QUOTE]  
>As an example, starting a preferred leader election for all topics in a cluster can be executed with the following command: # kafka-leader-election.sh --bootstrap-server localhost:9092 --election-type PREFERRED --all-topic-partitions # It is also possible to start elections on specific partitions or topics (Page 326) #✂️ 
{ #ref-824786056}


---
>[!QUOTE]  
>Once we’ve defined our JSON file, we can use it to generate a set of partition moves to move the topics listed in the file topics.json to the brokers with IDs 5 and 6: # kafka-reassign-partitions.sh --bootstrap-server localhost:9092 --topics-to-move-json-file topics.json --broker-list 5,6 --generate {"version":1, "partitions":[{"topic":"foo1","partition":2,"replicas":[1,2]}, {"topic":"foo1","partition":0,"replicas":[3,4]}, {"topic":"foo2","partition":2,"replicas":[1,2]}, {"topic":"foo2","partition":0,"replicas":[3,4]}, {"topic":"foo1","partition":1,"replicas":[2,3]}, {"topic":"foo2","partition":1,"replicas":[2,3]}] } Proposed partition reassignment configuration {"version":1, "partitions":[{"topic":"foo1","partition":2,"replicas":[5,6]}, {"topic":"foo1","partition":0,"replicas":[5,6]}, {"topic":"foo2","partition":2,"replicas":[5,6]}, {"topic":"foo2","partition":0,"replicas":[5,6]}, {"topic":"foo1","partition":1,"replicas":[5,6]}, {"topic":"foo2","partition":1,"replicas":[5,6]}] } (Page 328) #✂️ 
{ #ref-824786057}


---
>[!QUOTE]  
>To execute the proposed partition reassignment from the file expand-clusterreassignment.json, run the following command: # kafka-reassign-partitions.sh --bootstrap-server localhost:9092 --reassignment-json-file expand-cluster-reassignment.json --execute (Page 329) #✂️ 
{ #ref-824786058}


---
#### Other Tools
>[!QUOTE]  
>Client ACLs A command-line tool, kafka-acls.sh, is provided for interacting with access controls for Kafka clients. This includes full features for authorizer properties, set up for deny or allow principles, cluster- or topic-level restrictions, ZooKeeper TLS file configuration, and much more. Lightweight MirrorMaker A lightweight kafka-mirror-maker.sh script is available for mirroring data. A more in-depth look at replication can be found in Chapter 10. Testing tools There are several other scripts used for testing Kafka or helping to perform upgrades of features. kafka-broker-api-versions.sh helps to easily identify different versions of usable API elements when upgrading from one Kafka ver‐ sion to another and check for compatibility issues. There are producer and con‐ sumer performance tests scripts. There are several scripts to help administer ZooKeeper as well. There is also trogdor.sh, which is a test framework designed to run benchmarks and other workloads to attempt to stress test the system (Page 335) #✂️ 
{ #ref-824786060}


---
#### Unsafe Operations
### Monitoring Kafka
#### Metric Basics
>[!QUOTE]  
>All of the metrics exposed by Kafka can be accessed via the Java Management Exten‐ sions (JMX) interface. (Page 339) #✂️ 
{ #ref-828167615}


---
>[!QUOTE]  
>Table 13-1. Metric sources Category Description Application metrics These are the metrics you get from Kafka itself, from the JMX interface. Logs Another type of monitoring data that comes from Kafka itself. Because it is some form of text or structured data, and not just a number, it requires a little more processing. Infrastructure metrics These metrics come from systems that you have in front of Kafka but are still within the request path and under your control. An example is a load balancer. Synthetic clients This is data from tools that are external to your Kafka deployment, just like a client, but are under your direct control and are typically not performing the same work as your clients. An external monitor like Kafka Monitor falls in this category. Client metrics These are metrics that are exposed by the Kafka clients that connect to your cluster. (Page 340) #✂️ 
{ #ref-828167616}


---
>[!QUOTE]  
>A metric that is destined for alerting is useful for a very short period of time—typi‐ cally, not much longer than the amount of time it takes to respond to a problem. You can measure this on the order of hours, or maybe days. These metrics will be con‐ sumed by automation that responds to known problems for you, as well as the human operators in cases where automation does not exist yet (Page 341) #✂️ 
{ #ref-828167617}


---
>[!QUOTE]  
>Data that is primarily for debugging has a longer time horizon because you are fre‐ quently diagnosing problems that have existed for some time, or taking a deeper look at a more complex problem (Page 341) #✂️ 
{ #ref-828167618}


---
>[!QUOTE]  
>There is a third type of data that you will need eventually, and that is historical data on your application. The most common use for historical data is for capacity management purposes, and so it includes information about resources used, including compute resources, storage, and network (Page 342) #✂️ 
{ #ref-828167619}


---
#### Service-Level Objectives
>[!QUOTE]  
>One area of monitoring that is especially critical for infrastructure services, such as Kafka, is that of service-level objectives, or SLOs. This is how we communicate to our clients what level of service they can expect from the infrastructure service (Page 343) #✂️ 
{ #ref-828167621}


---
>[!QUOTE]  
>A service-level indicator (SLI) is a metric that describes one aspect of a service’s relia‐ bility. It should be closely aligned with your client’s experience, so it is usually true that the more objective these measurements are, the better they are (Page 343) #✂️ 
{ #ref-828167622}


---
>[!QUOTE]  
>A service-level objective (SLO), which can also be called a service-level threshold (SLT), combines an SLI with a target value. A common way to express the target is by the number of nines (99.9% is “three nines”), though it is by no means required (Page 343) #✂️ 
{ #ref-828167623}


---
>[!QUOTE]  
>A service-level agreement (SLA) is a contract between a service provider and a client. It usually includes several SLOs, as well as details about how they are measured and reported, how the client seeks support from the service provider, and penalties that the service provider will be subject to if they are not performing within the SLA (Page 344) #✂️ 
{ #ref-828167624}


---
##### What Metrics Make Good SLIs?
>[!QUOTE]  
>Availability Is the client able to make a request and get a response? Latency How quickly is the response returned? Quality Does the response include a proper response? Security Are the request and response appropriately protected, whether that is authorization or encryption? Throughput Can the client get enough data, fast enough (Page 345) #✂️ 
{ #ref-828167626}


---
>[!QUOTE]  
>In short, SLOs should inform your primary alerts. The reason for this is that the SLOs describe problems from your customers’ point of view, and those are the ones that you should be concerned about first (Page 345) #✂️ 
{ #ref-828167627}


---
#### Kafka Broker Metrics
>[!QUOTE]  
>Absent a problem identified at the OS or hardware level, however, the cause is almost always an imbalance in the load of the Kafka cluster. While Kafka attempts to keep the data within the cluster evenly spread across all brokers, this does not mean that client access to that data is evenly distributed. It also does not detect issues such as hot partitions (Page 347) #✂️ 
{ #ref-828167629}


---
>[!QUOTE]  
>Overloaded clusters are another problem that is easy to detect. If the cluster is bal‐ anced, and many of the brokers are showing elevated latency for requests or a low request handler pool idle ratio, you are reaching the limits of your brokers to serve traffic for this cluster (Page 348) #✂️ 
{ #ref-828167630}


---
>[!QUOTE]  
>One of the most popular metrics to use when monitoring Kafka is under-replicated partitions. This measurement, provided on each broker in a cluster, gives a count of the number of partitions for which the broker is the leader replica, where the follower replicas are not caught up. This single measurement provides insight into a number of problems with the Kafka cluster, from a broker being down to resource exhaustion (Page 348) #✂️ 
{ #ref-828167631}


---
>[!QUOTE]  
>A steady (unchanging) number of under-replicated partitions reported by many of the brokers in a cluster normally indicates that one of the brokers in the cluster is off‐ line. (Page 349) #✂️ 
{ #ref-828167632}


---
>[!QUOTE]  
>If the number of under-replicated partitions is fluctuating, or if the number is steady but there are no brokers offline, this typically indicates a performance issue in the cluster. (Page 349) #✂️ 
{ #ref-828167633}


---
>[!QUOTE]  
>Cluster problems usually fall into one of two categories: • Unbalanced load • Resource exhaustion The first problem, unbalanced partitions or leadership, is the easiest to find even though fixing it can be an involved process. In order to diagnose this problem, you will need several metrics from the brokers in the cluster: • Partition count • Leader partition count (Page 350) #✂️ 
{ #ref-828167634}


---
>[!QUOTE]  
>• All topics messages in rate • All topics bytes in rate • All topics bytes out rate (Page 351) #✂️ 
{ #ref-828167635}


---
>[!QUOTE]  
>Another common cluster performance issue is exceeding the capacity of the brokers to serve requests. There are many possible bottlenecks that could slow things down: CPU, disk IO, and network throughput are a few of the most common (Page 351) #✂️ 
{ #ref-828167636}


---
>[!QUOTE]  
>Exhausting any of these resources will typically show up as the same problem: underreplicated partitions. It’s critical to remember that the broker replication process operates in exactly the same way that other Kafka clients do (Page 352) #✂️ 
{ #ref-828167637}


---
>[!QUOTE]  
>The more common type of hardware failure that leads to a performance degradation in Kafka is a disk failure (Page 353) #✂️ 
{ #ref-828167638}


---
##### Broker Metrics
>[!QUOTE]  
>The active controller count metric indicates whether the broker is currently the con‐ troller for the cluster. The metric will either be 0 or 1, with 1 showing that the broker is currently the controller. At all times, only one broker should be the controller, and one broker must always be the controller in the cluster. If two brokers say that they are currently the controller, this means that you have a problem where a controller thread that should have exited has become stuck. This can cause problems with not being able to execute administrative tasks, such as partition moves, properly. To rem‐ edy this, you will need to restart both brokers at the very least. However, when there is an extra controller in the cluster, there will often be problems performing a safe shutdown of a broker, and you will need to force stop the broker instead (Page 354) #✂️ 
{ #ref-828167640}


---
>[!QUOTE]  
>If no broker claims to be the controller in the cluster, the cluster will fail to respond properly in the face of state changes, including topic or partition creation, or broker failures. (Page 355) #✂️ 
{ #ref-828167641}


---
>[!QUOTE]  
>The controller queue size metric indicates how many requests the controller is cur‐ rently waiting to process for the brokers. The metric will be 0 or more, with the value fluctuating frequently as new requests from brokers come in and administrative actions, such as creating partitions, moving partitions, and processing leader changes happen. Spikes in the metric are to be expected, but if this value continuously increa‐ ses, or stays steady at a high value and does not drop, it indicates that the controller may be stuck (Page 355) #✂️ 
{ #ref-828167642}


---
>[!QUOTE]  
>Kafka uses two thread pools for handling all client requests: network threads and request handler threads (also called I/O threads). The network threads are responsible for reading and writing data to the clients across the network. This does not require significant processing, which means that exhaustion of the network threads is less of a concern (Page 355) #✂️ 
{ #ref-828167643}


---
>[!QUOTE]  
>The request handler idle ratio metric indicates the percentage of time the request handlers are not in use. The lower this number, the more loaded the broker is.Expe‐ rience tells us that idle ratios lower than 20% indicate a potential problem, and lower than 10% is usually an active performance problem (Page 356) #✂️ 
{ #ref-828167644}


---
>[!QUOTE]  
>The all topics bytes in rate, expressed in bytes per second, is useful as a measurement of how much message traffic your brokers are receiving from producing clients. This is a good metric to trend over time to help you determine when you need to expand the cluster or do other growth-related work (Page 357) #✂️ 
{ #ref-828167645}


---
>[!QUOTE]  
>The all topics bytes out rate, similar to the bytes in rate, is another overall growth met‐ ric. In this case, the bytes out rate shows the rate at which consumers are reading messages out. The outbound bytes rate may scale differently than the inbound bytes rate, thanks to Kafka’s capacity to handle multiple consumers with ease (Page 358) #✂️ 
{ #ref-828167646}


---
>[!QUOTE]  
>While the byte rates described previously show the broker traffic in absolute terms of bytes, the messages in rate shows the number of individual messages, regardless of their size, produced per second. This is useful as a growth metric as a different meas‐ ure of producer traffic (Page 359) #✂️ 
{ #ref-828167647}


---
>[!QUOTE]  
>The partition count for a broker generally doesn’t change that much, as it is the total number of partitions assigned to that broker. This includes every replica the broker has, regardless of whether it is a leader or follower for that partition (Page 359) #✂️ 
{ #ref-828167648}


---
>[!QUOTE]  
>The leader count metric shows the number of partitions that the broker is currently the leader for. As with most other measurements in the brokers, this one should be generally even across the brokers in the cluster (Page 359) #✂️ 
{ #ref-828167649}


---
>[!QUOTE]  
>Along with the under-replicated partitions count, the ofine partitions count is a criti‐ cal metric for monitoring (see Table 13-13). This measurement is only provided by the broker that is the controller for the cluster (all other brokers will report 0) and shows the number of partitions in the cluster that currently have no leader. Partitions without leaders can happen for two main reasons: • All brokers hosting replicas for this partition are down • No in-sync replica can take leadership due to message-count mismatches (with unclean leader election disabled) (Page 360) #✂️ 
{ #ref-828167650}


---
>[!QUOTE]  
>At a minimum, you should collect at least the average and one of the higher percentiles (either 99% or 99.9%) for the total time metric, as well as the requests per second metric, for every request type. This gives a view into the overall performance of requests to the Kafka broker. If you can, you should also collect those measure‐ ments for the other six timing metrics for each request type, as this will allow you to narrow down any performance problems to a specific phase of request processing (Page 363) #✂️ 
{ #ref-828167651}


---
>[!QUOTE]  
>In addition to the many metrics available on the broker that describe the operation of the Kafka broker in general, there are topic- and partition-specific metrics. In larger clusters these can be numerous, and it may not be possible to collect all of them into a metrics system as a matter of normal operations. However, they are quite useful for debugging specific issues with a client (Page 364) #✂️ 
{ #ref-828167652}


---
>[!QUOTE]  
>For the JVM, the critical thing to monitor is the status of garbage collection (GC). The particular beans that you must monitor for this information will vary depending on the particular Java Runtime Environment (JRE) that you are using, as well as the specific GC settings in use (Page 366) #✂️ 
{ #ref-828167653}


---
>[!QUOTE]  
>The record-error-rate is one attribute that you will definitely want to set an alert for. This metric should always be zero, and if it is anything greater than that, the pro‐ ducer is dropping messages it is trying to send to the Kafka brokers (Page 371) #✂️ 
{ #ref-828167654}


---
>[!QUOTE]  
>The other metric to alert on is the request-latency-avg. This is the average amount of time a produce request sent to the brokers takes. You should be able to establish a baseline value for what this number should be in normal operations, and set an alert threshold above that (Page 371) #✂️ 
{ #ref-828167655}


---
>[!QUOTE]  
>In addition to these critical metrics, it is always good to know how much message traffic your producer is sending. Three attributes will provide three different views of this. The outgoing-byte-rate describes the messages in absolute size in bytes per second. The record-send-rate describes the traffic in terms of the number of mes‐ sages produced per second. Finally, the request-rate provides the number of pro‐ duce requests sent to the brokers per second (Page 371) #✂️ 
{ #ref-828167656}


---
>[!QUOTE]  
>There are also metrics that describe the size of records, requests, and batches. The request-size-avg metric provides the average size of the produce requests being sent to the brokers in bytes. The batch-size-avg provides the average size of a single message batch (which, by definition, is comprised of messages for a single topic parti‐ tion) in bytes. (Page 371) #✂️ 
{ #ref-828167657}


---
>[!QUOTE]  
>The last overall producer metric attribute that is recommended is record-queuetime-avg. This measurement is the average amount of time, in milliseconds, that a single message waits in the producer, after the application sends it, before it is actually produced to Kafka (Page 372) #✂️ 
{ #ref-828167658}


---
>[!QUOTE]  
>For the fetch manager (Page 373) #✂️ 
{ #ref-828167659}


---
>[!QUOTE]  
>For the fetch manager, the one attribute you may want to set up monitoring and alerts for is fetch-latency-avg. As with the equivalent request-latency-avg in the producer client, this metric tells us how long fetch requests to the brokers take. The problem with alerting on this metric is that the latency is governed by the consumer configurations fetch.min.bytes and fetch.max.wait.ms (Page 373) #✂️ 
{ #ref-828167660}


---
>[!QUOTE]  
>To know how much message traffic your consumer client is handling, you should capture the bytes-consumed-rate or the records-consumed-rate, or preferably both. These metrics describe the message traffic consumed by this client instance in bytes per second and messages per second, respectively (Page 374) #✂️ 
{ #ref-828167661}


---


*New highlights added December 29, 2024 at 5:09 PM* 
#### Stream Processing
#### What Is Stream Processing?
>[!QUOTE]  
>First and foremost, a data stream is an abstraction representing an unbounded dataset. Unbounded means infinite and ever growing. The dataset is unbounded because over time, new records keep arriving (Page 383) #✂️ 
{ #ref-831086515}


---
>[!QUOTE]  
>Event streams are ordered There is an inherent notion of which events occur before or after other events. (Page 383) #✂️ 
{ #ref-831086516}


---
>[!QUOTE]  
>Immutable data records Events, once occurred, can never be modified (Page 383) #✂️ 
{ #ref-831086517}


---
>[!QUOTE]  
>Event streams are replayable (Page 384) #✂️ 
{ #ref-831086518}


---
>[!QUOTE]  
>Stream processing is a programming paradigm—just like requestresponse and batch processing (Page 384) #✂️ 
{ #ref-831086519}


---
>[!QUOTE]  
>Stream processing This is a continuous and nonblocking option. Stream processing fills the gap between the request-response world, where we wait for events that take two milliseconds to process, and the batch processing world, where data is processed once a day and takes eight hours to complete. Most business processes don’t require an immediate response within milliseconds but can’t wait for the next day either (Page 385) #✂️ 
{ #ref-831086520}


---
#### Stream Processing Concepts
##### Topology
>[!QUOTE]  
>A stream processing application includes one or more processing topologies. A pro‐ cessing topology starts with one or more source streams that are passed through a graph of stream processors connected through event streams, until results are written (Page 385) #✂️ 
{ #ref-831086523}


---
##### Time
>[!QUOTE]  
>Event time This is the time the events we are tracking occurred and the record was created (Page 386) #✂️ 
{ #ref-831086525}


---
>[!QUOTE]  
>Log append time This is the time the event arrived at the Kafka broker and was stored there, also called ingestion time (Page 386) #✂️ 
{ #ref-831086526}


---
>[!QUOTE]  
>Processing time This is the time at which a stream processing application received the event in order to perform some calculation (Page 387) #✂️ 
{ #ref-831086527}


---
>[!QUOTE]  
>Kafka Streams assigns time to each event based on the TimestampExtractor inter‐ face. Developers of Kafka Streams applications can use different implementations of this interface, which can use either of the three time semantics explained previously or a completely different choice of timestamp, including extracting a timestamp from the contents of the event itself (Page 387) #✂️ 
{ #ref-831086528}


---
>[!QUOTE]  
>When Kafka Streams writes output to a Kafka topic, it assigns a timestamp to each event based on the following rules: • When the output record maps directly to an input record, the output record will use the same timestamp as the input. • When the output record is a result of an aggregation, the timestamp of the out‐ put record will be the maximum timestamp used in the aggregation. • When the output record is a result of joining two streams, the timestamp of the output record is the largest of the two records being joined. When a stream and a table are joined, the timestamp from the stream record is used. • Finally, if the output record was generated by a Kafka Streams function that gen‐ erates data in a specific schedule regardless of input, such as punctuate(), the output timestamp will depend on the current internal times of the stream pro‐ cessing app. (Page 387) #✂️ 
{ #ref-831086529}


---
##### State
>[!QUOTE]  
>Stream processing becomes really interesting when we have operations that involve multiple events: counting the number of events by type, moving averages, joining two streams to create an enriched stream of information, etc. In those cases, it is not enough to look at each event by itself; we need to keep track of more information— how many events of each type did we see this hour, all events that require joining, sums, averages, etc. We call this information a state (Page 388) #✂️ 
{ #ref-831086531}


---
>[!QUOTE]  
>Local or internal state State that is accessible only by a specific instance of the stream processing appli‐ cation. This state is usually maintained and managed with an embedded, inmemory database running within the application. The advantage of local state is that it is extremely fast. The disadvantage is that we are limited to the amount of memory available (Page 388) #✂️ 
{ #ref-831086532}


---
>[!QUOTE]  
>External state State that is maintained in an external data store, often a NoSQL system like Cas‐ sandra. The advantages of an external state are its virtually unlimited size and the fact that it can be accessed from multiple instances of the application or even from different applications. The downside is the extra latency and complexity introduced with an additional system, as well as availability—the application needs to handle the possibility that the external system is not available (Page 389) #✂️ 
{ #ref-831086533}


---
##### Stream-Table Duality
>[!QUOTE]  
>A table is a collection of records, each identi‐ fied by its primary key and containing a set of attributes as defined by a schema. Table records are mutable (i.e., tables allow update and delete operations). Querying a table allows checking the state of the data at a specific point in time (Page 389) #✂️ 
{ #ref-831086535}


---
>[!QUOTE]  
>Unlike tables, streams contain a history of changes. A stream is a string of events wherein each event caused a change. A table contains a current state of the world, which is the result of many changes. From this description, it is clear that streams and tables are two sides of the same coin—the world always changes, and sometimes we are interested in the events that caused those changes, whereas other times we are interested in the current state of the world (Page 389) #✂️ 
{ #ref-831086536}


---
>[!QUOTE]  
>To convert a stream to a table, we need to apply all the changes that the stream con‐ tains. This is also called materializing the stream (Page 389) #✂️ 
{ #ref-831086537}


---
##### Time Windows
>[!QUOTE]  
>Most operations on streams are windowed operations, operating on slices of time: moving averages, top products sold this week, 99th percentile load on the system, etc. Join operations on two streams are also windowed—we join events that occurred at the same slice of time (Page 390) #✂️ 
{ #ref-831086539}


---
>[!QUOTE]  
>Size of the window Do we want to calculate the average of all events in every five-minute window? Every 15-minute window (Page 390) #✂️ 
{ #ref-831086540}


---
>[!QUOTE]  
>How ofen the window moves (advance interval) Five-minute averages can update every minute, second, or every time there is a new event. Windows for which the size is a fixed time interval are called hopping windows. When the advance interval is equal to the window size, it is called a tumbling window. (Page 391) #✂️ 
{ #ref-831086541}


---
>[!QUOTE]  
>How long the window remains updatable (grace period) Our five-minute moving average calculated the average for the 00:00–00:05 win‐ dow. Now, an hour later, we are getting a few more input records with their event time showing 00:02. Do we update the result for the 00:00–00:05 period? Or do we let bygones be bygones (Page 391) #✂️ 
{ #ref-831086542}


---
##### Processing Guarantees
>[!QUOTE]  
>Every applica‐ tion that uses the Kafka Streams library can enable exactly-once guarantees by setting processing.guarantee to exactly_once (Page 392) #✂️ 
{ #ref-831086544}


---
#### Stream Processing Design Patterns
##### Single-Event Processing
>[!QUOTE]  
>The most basic pattern of stream processing is the processing of each event in isola‐ tion. This is also known as a map/flter pattern because it is commonly used to filter unnecessary events from the stream or transform each event (Page 392) #✂️ 
{ #ref-831086547}


---
##### Processing with Local State
>[!QUOTE]  
>These aggregations require maintaining a state. In our example, in order to calculate the minimum and average price each day, we need to store the minimum value, the sum, and the number of records we’ve seen up until the current time. All this can be done using local state (rather than a shared state) because each opera‐ tion in our example is a group by aggregate. That is, we perform the aggregation per stock symbol, not on the entire stock market in general. We use a Kafka partitioner to make sure that all events with the same stock symbol are written to the same parti‐ tion (Page 393) #✂️ 
{ #ref-831086549}


---
>[!QUOTE]  
>There are several issues a stream processing application must address: Memory usage The local state ideally fits into the memory available to the application instance. Some local stores allow spilling to disk, but this has significant performance impact. Persistence We need to make sure the state is not lost when an application instance shuts down and that the state can be recovered when the instance starts again or is replaced by a different instance. This is something that Kafka Streams handles very well—local state is stored in-memory using embedded RocksDB, which also persists the data to disk for quick recovery after restarts (Page 394) #✂️ 
{ #ref-831086550}


---
>[!QUOTE]  
>There are several issues a stream processing application must address: Memory usage The local state ideally fits into the memory available to the application instance. Some local stores allow spilling to disk, but this has significant performance impact. Persistence We need to make sure the state is not lost when an application instance shuts down and that the state can be recovered when the instance starts again or is replaced by a different instance. This is something that Kafka Streams handles very well—local state is stored in-memory using embedded RocksDB, which also persists the data to disk for quick recovery after restarts. But all the changes to the local state are also sent to a Kafka topic. If a stream’s node goes down, the local state is not lost—it can be easily re-created by rereading the events from the Kafka topic (Page 394) #✂️ 
{ #ref-831086551}


---
>[!QUOTE]  
>Rebalancing Partitions sometimes get reassigned to a different consumer. When this happens, the instance that loses the partition must store the last good state, and the instance that receives the partition must know to recover the correct state. (Page 395) #✂️ 
{ #ref-831086552}


---
##### Multiphase Processing/Repartitioning
##### Processing with External Lookup: Stream-Table Join
>[!QUOTE]  
>To get good performance and availability, we need to cache the information from the database in our stream processing application. Managing this cache can be challeng‐ ing though—how do we prevent the information in the cache from getting stale? If we refresh events too often, we are still hammering the database, and the cache isn’t helping much. If we wait too long to get new events, we are doing stream processing with stale information. But if we can capture all the changes that happen to the database table in a stream of events, we can have our stream processing job listen to this stream and update the cache based on database change events. Capturing changes to the database as events in a stream is known as change data capture (CDC), and Kafka Connect has multiple connectors capable of performing CDC and converting database tables to a stream of change events. This allows us to keep our own private copy of the table and be noti‐ fied whenever there is a database change event so we can update our own copy accordingly. (Page 397) #✂️ 
{ #ref-831086555}


---
>[!QUOTE]  
>We refer to this as a stream-table join because one of the streams represents changes to a locally cached table. (Page 397) #✂️ 
{ #ref-831086556}


---
##### Table-Table Join
>[!QUOTE]  
>Joining two tables is always nonwindowed and joins the current state of both tables at the time the operation is performed. With Kafka Streams, we can perform an equijoin, in which both tables have the same key that is partitioned in the same way, and therefore the join operation can be efficiently distributed between a large number of application instances and machines (Page 398) #✂️ 
{ #ref-831086558}


---
>[!QUOTE]  
>Kafka Streams also supports foreign-key join of two tables—the key of one stream or table is joined with an arbitrary field from another stream or table (Page 398) #✂️ 
{ #ref-831086559}


---
##### Streaming Join
>[!QUOTE]  
>When we use a stream to represent a table, we can ignore most of the history in the stream because we only care about the current state in the table. But when we join two streams, we are joining the entire history, trying to match events in one stream with events in the other stream that have the same key and hap‐ pened in the same time windows. This is why a streaming join is also called a win‐ dowed join (Page 398) #✂️ 
{ #ref-831086561}


---
>[!QUOTE]  
>Kafka Streams supports equi-joins, where streams, queries, and clicks are parti‐ tioned on the same keys, which are also the join keys (Page 399) #✂️ 
{ #ref-831086562}


---
>[!QUOTE]  
>Kafka Streams supports equi-joins, where streams, queries, and clicks are parti‐ tioned on the same keys, which are also the join keys. This way, all the click events from user_id:42 end up in partition 5 of the clicks topic, and all the search events for user_id:42 end up in partition 5 of the search topic. Kafka Streams then makes sure that partition 5 of both topics is assigned to the same task (Page 399) #✂️ 
{ #ref-831086563}


---
##### Out-of-Sequence Events
>[!QUOTE]  
>Recognize that an event is out of sequence—this requires that the application examines the event time and discovers that it is older than the current time. • Define a time period during which it will attempt to reconcile out-of-sequence events. Perhaps a three-hour delay should be reconciled, and events over three weeks old can be thrown away. • Have an in-band capability to reconcile this event. This is the main difference between streaming apps and batch jobs. If we have a daily batch job and a few events arrived after the job completed, we can usually just rerun yesterday’s job and update the events. With stream processing, there is no “rerun yesterday’s job”—the same continuous process needs to handle both old and new events at any given moment. • Be able to update results. If the results of the stream processing are written into a database, a put or update is enough to update the results. If the stream app sends results by email, updates may be trickier (Page 400) #✂️ 
{ #ref-831086565}


---
##### Reprocessing
>[!QUOTE]  
>We have an improved version of our stream processing application. We want to run the new version of the application on the same event stream as the old, pro‐ duce a new stream of results that does not replace the first version, compare the results between the two versions, and at some point move clients to use the new results instead of the existing ones. (Page 400) #✂️ 
{ #ref-831086567}


---
>[!QUOTE]  
>The existing stream processing app is buggy. We fix the bug, and we want to reprocess the event stream and recalculate our results (Page 401) #✂️ 
{ #ref-831086568}


---
>[!QUOTE]  
>Spinning up the new version of the application as a new consumer group • Configuring the new version to start processing from the first offset of the input topics (so it will get its own copy of all events in the input streams) • Letting the new application continue processing, and switching the client appli‐ cations to the new result stream when the new version of the processing job has caught up (Page 401) #✂️ 
{ #ref-831086569}


---
##### Interactive Queries
>[!QUOTE]  
>In some cases, however, it is desirable to take a shortcut and read the results from the state store itself. This is common when the result is a table (e.g., the top 10 best-selling books) and the stream of results is really a stream of updates to this table—it is much faster and easier to just read the table directly from the stream processing application state (Page 401) #✂️ 
{ #ref-831086571}


---
#### Kafka Streams by Example
#### Kafka Streams: Architecture Overview
##### Building a Topology
>[!QUOTE]  
>Every streams application implements and executes one topology. Topology (also called DAG, or directed acyclic graph, in other stream processing frameworks) is a set of operations and transitions that every event moves through from input to output. (Page 410) #✂️ 
{ #ref-831086575}


---
#### Optimizing a Topology
>[!QUOTE]  
>Currently, Apache Kafka only contains a few optimizations, mostly around reusing topics where possible. These can be enabled by setting StreamsConfig. TOPOLOGY_OPTIMIZATION to StreamsConfig.OPTIMIZE and calling build(props). If you only call build() without passing the config, optimization is still disabled (Page 411) #✂️ 
{ #ref-831086577}


---
#### Testing a Topology
>[!QUOTE]  
>The main testing tool for Kafka Streams applications is TopologyTestDriver (Page 412) #✂️ 
{ #ref-831086579}


---
>[!QUOTE]  
>These tests look like normal unit tests. We define input data, produce it to mock input topics, run the topology with the test driver, read the results from mock output topics, and validate the result by comparing it to expected values (Page 412) #✂️ 
{ #ref-831086580}


---
>[!QUOTE]  
>Unit tests are typically complemented by integration tests, and for Kafka Streams, there are two popular integration test frameworks: EmbeddedKafkaCluster and Test containers (Page 412) #✂️ 
{ #ref-831086581}


---
#### Scaling a Topology
>[!QUOTE]  
>Kafka Streams scales by allowing multiple threads of executions within one instance of the application and by supporting load balancing between distributed instances of the application (Page 412) #✂️ 
{ #ref-831086583}


---
>[!QUOTE]  
>The Streams engine parallelizes execution of a topology by splitting it into tasks. The number of tasks is determined by the Streams engine and depends on the number of partitions in the topics that the application processes. Each task is responsible for a subset of the partitions: the task will subscribe to those partitions and consume events from them. For every event it consumes, the task will execute all the processing steps that apply to this partition in order before eventually writing the result to the sink. Those tasks are the basic unit of parallelism in Kafka Streams, because each task can execute independently of others (Page 412) #✂️ 
{ #ref-831086584}


---
>[!QUOTE]  
>The developer of the application can choose the number of threads each application instance will execute. If multiple threads are available, every thread will execute a subset of the tasks that the application creates. If multiple instances of the application are running on multiple servers, different tasks will execute for each thread on each server. (Page 413) #✂️ 
{ #ref-831086585}


---
>[!QUOTE]  
>Sometimes a processing step may require input from multiple partitions, which could create dependencies between tasks. For example, if we join two streams, as we did in the ClickStream example in “ClickStream Enrichment” on page 408, we need data from a partition in each stream before we can emit a result. Kafka Streams handles this situation by assigning all the partitions needed for one join to the same task so that the task can consume from all the relevant partitions and perform the join inde‐ pendently. This is why Kafka Streams currently requires that all topics that participate in a join operation have the same number of partitions and be partitioned based on the join key. Kafka Streams: Architecture Overview | 413 (Page 413) #✂️ 
{ #ref-831086586}


---
>[!QUOTE]  
>Another example of dependencies between tasks is when our application requires repartitioning. For instance, in the ClickStream example, all our events are keyed by the user ID. But what if we want to generate statistics per page? Or per zip code? Kafka Streams will repartition the data by zip code and run an aggregation of the data with the new partitions. If task 1 processes the data from partition 1 and reaches a processor that repartitions the data (groupBy operation), it will need to shufe, or send events to other tasks (Page 414) #✂️ 
{ #ref-831086587}


---
##### Surviving Failures
>[!QUOTE]  
>So if the application fails and needs to restart, it can look up its last position in the stream from Kafka and continue its processing from the last offset it committed before failing. Note that if the local state store is lost (e.g., because we needed to replace the server it was stored on), the streams application can always re-create it from the change log it stores in Kafka (Page 415) #✂️ 
{ #ref-831086589}


---
>[!QUOTE]  
>If a task failed but there are threads or other instances of the streams application that are active, the task will restart on one of the available threads. This is similar to how consumer groups handle the failure of one of the consumers in the group by assigning partitions to one of the remaining consumers (Page 415) #✂️ 
{ #ref-831086590}


---
>[!QUOTE]  
>Therefore, reducing recovery time often boils down to reducing the time it takes to recover the state. A key technique is to make sure all Kafka Streams topics are config‐ ured for aggressive compaction—by setting a low min.compaction.lag.ms and con‐ figuring the segment size to 100 MB instead of the default 1 GB (recall that the last segment in each partition, the active segment, is not compacted) (Page 416) #✂️ 
{ #ref-831086591}


---
>[!QUOTE]  
>For an even faster recovery, we recommend configuring standby replica—those are tasks that simply shadow active tasks in a stream processing application and keep the current state warm on a different server. When failover occurs, they already have the most current state and are ready to continue processing with almost no downtime. (Page 416) #✂️ 
{ #ref-831086592}


---
#### Stream Processing Use Cases
#### How to Choose a Stream Processing Framework

