---
{"dg-publish":true,"permalink":"/reference/kafka-the-definitive-guide-v2-highlights/","title":"Kafka The Definitive Guide v2","tags":["✂️","📚"],"created":"2024-08-29T16:38:21.568-05:00","updated":"2024-11-10T13:55:33.064-06:00"}
---


# Kafka The Definitive Guide V2

![cover|150](https://readwise-assets.s3.amazonaws.com/static/images/default-book-icon-3.40504e56b01b.png)

## Metadata

## Highlights

#📫

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
>A batch is just a collection of messages, all of which are being produced to the same topic and partition. An individual round trip across the network for each message would result in excessive overhead, and collecting messages together into a batch reduces this. Of course, this is a trade-off between latency and throughput: the larger the batches, the more messages that can be handled per unit of time, but the longer it takes an individual message to propagate (Page 5) #✂️
{ #ref-745647007}


---

##### Schemas

##### Topics and Partitions

>[!QUOTE]  
>use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️
{ #ref-745647010}


---

>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that additional structure, or schema, be imposed on the message content so that it can be easily understood. There are many options available for message schema, depending on your application’s individual needs. Simplistic systems, such as JavaScript Object Notation (JSON) and Extensible Markup Language (XML), are easy to use and human readable. However, they lack features such as robust type handling and compatibility between schema versions. Many Kafka developers favor the use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️
{ #ref-745647011}


---

>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that additional structure, or schema, be imposed on the message content so that it can be easily understood. There are many options available for message schema, depending on your application’s individual needs. Simplistic systems, such as JavaScript Object Notation (JSON) and Extensible Markup Language (XML), are easy to use and human readable. However, they lack features such as robust type handling and compatibility between schema versions. Many Kafka developers favor the use of Apache Avro, which is a serialization framework originally developed for Hadoop (Page 5) #✂️
{ #ref-745647012}


---

>[!QUOTE]  
>While messages are opaque byte arrays to Kafka itself, it is recommended that additional structure, or schema, be imposed on the message content so that it can be easily understood (Page 5) #✂️
{ #ref-745647013}


---

>[!QUOTE]  
>Messages in Kafka are categorized into topics. The closest analogies for a topic are a database table or a folder in a filesystem (Page 5) #✂️
{ #ref-745647014}


---

>[!QUOTE]  
>Topics are additionally broken down into a number of partitions. Going back to the “commit log” description, a partition is a single log. Messages are written to it in an append-only fashion and are read in order from beginning to end (Page 5) #✂️
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
>The ofset—an integer value that continually increases—is another piece of metadata that Kafka adds to each message as it is produced. Each message in a given partition has a unique offset, and the following message has a greater offset (though not necessarily monotonically greater). By storing the next possible offset for each partition, typically in Kafka itself, a consumer can stop and restart without losing its place (Page 7) #✂️
{ #ref-745647021}


---

>[!QUOTE]  
>Consumers work as part of a consumer group, which is one or more consumers that work together to consume a topic. The group ensures that each partition is only consumed by one member (Page 7) #✂️
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
>Kafka brokers are designed to operate as part of a cluster. Within a cluster of brokers, one broker will also function as the cluster controller (elected automatically from the live members of the cluster). The controller is responsible for administrative operations, including assigning partitions to brokers and monitoring for broker failures (Page 8) #✂️
{ #ref-745647026}


---

>[!QUOTE]  
>A partition is owned by a single broker in the cluster, and that broker is called the leader of the partition. A replicated partition (as seen in Figure 1-7) is assigned to additional brokers, called followers of the partition. Replication provides redundancy of messages in the partition, such that one of the followers can take over leadership if there is a broker failure (Page 8) #✂️
{ #ref-745647027}


---

>[!QUOTE]  
>All producers must connect to the leader in order to publish messages, but consumers may fetch from either the leader or one of the followers (Page 8) #✂️
{ #ref-745647028}


---

>[!QUOTE]  
>key feature of Apache Kafka is that of retention, which is the durable storage of messages for some period of time. Kafka brokers are configured with a default retention setting for topics, either retaining messages for some period of time (e.g., 7 days) or until the partition reaches a certain size in bytes (e.g., 1 GB). Once these limits are reached, messages are expired and deleted (Page 8) #✂️
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
>Durable retention means that if a consumer falls behind, either due to slow processing or a burst in traffic, there is no danger of losing data. It also means that maintenance can be performed on consumers, taking applications offline for a short period of time, with no concern about messages backing up on the producer or getting lost (Page 11) #✂️
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
>ZooKeeper is designed to work as a cluster, called an ensemble, to ensure high availability. Due to the balancing algorithm used, it is recommended that ensembles contain an odd number of servers (e.g., 3, 5, and so on) as a majority of ensemble members (a quorum) must be working in order for ZooKeeper to respond to requests (Page 21) #✂️
{ #ref-745647057}


---

>[!QUOTE]  
>Consider running ZooKeeper in a five-node ensemble. To make configuration changes to the ensemble, including swapping a node, you will need to reload nodes one at a time (Page 22) #✂️
{ #ref-745647058}


---

>[!QUOTE]  
>To configure ZooKeeper servers in an ensemble, they must have a common configuration that lists all servers, and each server needs a myid file in the data directory that specifies the ID number of the server (Page 22) #✂️
{ #ref-745647059}


---

##### Installing a Kafka Broker

##### Confguring the Broker

>[!QUOTE]  
>Every Kafka broker must have an integer identifier, which is set using the broker.id configuration. By default, this integer is set to 0, but it can be any value. It is essential that the integer must be unique for each broker within a single Kafka cluster. The selection of this number is technically arbitrary, and it can be moved between brokers if necessary for maintenance tasks (Page 25) #✂️
{ #ref-745647062}


---

>[!QUOTE]  
>The new listeners config is a comma-separated list of URIs that we listen on with the listener names. If the listener name is not a common security protocol, then another config listener.security.protocol.map must also be configured. A listener is defined as <protocol>://<hostname>:<port>. An example of a legal listener config is PLAIN TEXT://localhost:9092,SSL://:9091. Specifying the hostname as 0.0.0.0 will bind to all interfaces. Leaving the hostname empty will bind it to the default interface. (Page 25) #✂️
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
>The num.partitions parameter determines how many partitions a new topic is created with, primarily when automatic topic creation is enabled (which is the default setting). This parameter defaults to one partition (Page 28) #✂️
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
>It is highly recommended to set the replication factor to at least 1 above the min.insync.replicas setting. For more fault-resistant settings, if you have large enough clusters and enough hardware, setting your replication factor to 2 above the min.insync.replicas (abbreviated as RF++) can be preferable. RF++ will allow easier maintenance and prevent outages (Page 29) #✂️
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
>Once the log segment has reached the size specified by the log.segment.bytes parameter, which defaults to 1 GB, the log segment is closed and a new one is opened. Once a log segment has been closed, it can be considered for expiration (Page 31) #✂️
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
>The Kafka broker limits the maximum size of a message that can be produced, configured by the message.max.bytes parameter, which defaults to 1000000, or 1 MB (Page 32) #✂️
{ #ref-745647082}


---

##### The Message Size Configured on the Kafka Broker Must Be Coordinated with the fetch.message.max.bytes Configuration on Consumer Clients. If This Value is Smaller Than message.max.bytes, Then Consumers That Encounter Larger Messages Will Fail to Fetch Those Messages, Resulting in a Situation Where the Consumer Gets Stuck and Cannot Proceed

>[!QUOTE]  
>Selecting Hardware (Page 33) #✂️
{ #ref-745647084}


---

>[!QUOTE]  
>Currently, in a well-configured environment, it is recommended to not have more than 14,000 partition replicas per broker and 1 million replicas per cluster (Page 38) #✂️
{ #ref-745647085}


---

>[!QUOTE]  
>There are only two requirements in the broker configuration to allow multiple Kafka brokers to join a single cluster. The first is that all brokers must have the same configuration for the zookeeper.connect parameter. This specifies the ZooKeeper ensemble and path where the cluster stores metadata. The second requirement is that all brokers in the cluster must have a unique value for the broker.id parameter. If two brokers attempt to join the same cluster with the same broker.id, the second broker will log an error and fail to start (Page 38) #✂️
{ #ref-745647086}


---

>[!QUOTE]  
>Regardless of which filesystem is chosen for the mount that holds the log segments, it is advisable to set the noatime mount option for the mount point. File metadata contains three timestamps: creation time (ctime), last modified time (mtime), and last access time (atime). By default, the atime is updated every time a file is read. This generates a large number of disk writes (Page 41) #✂️
{ #ref-745647087}


---

##### Production Concerns

>[!QUOTE]  
>It is now recommended for Kafka to use G1GC as the default garbage collector (Page 42) #✂️
{ #ref-745647089}


---

>[!QUOTE]  
>Kafka can assign new partitions to brokers in a rack-aware manner, making sure that replicas for a single partition do not share a rack. To do this, the broker.rack configuration for each broker must be set properly. (Page 44) #✂️
{ #ref-745647090}


---

>[!QUOTE]  
>This amount of traffic is generally minimal, and it does not justify the use of a dedicated ZooKeeper ensemble for a single Kafka cluster. In fact, many deployments will use a single ZooKeeper ensemble for multiple Kafka clusters (Page 44) #✂️
{ #ref-745647091}


---

>[!QUOTE]  
>Outside of using a single ensemble for multiple Kafka clusters, it is not recommended to share the ensemble with other applications, if it can be avoided. Kafka is sensitive to ZooKeeper latency and timeouts, and an interruption in communications with the ensemble will cause the brokers to behave unpredictably (Page 45) #✂️
{ #ref-745647092}


---

### Kafka Producers: Writing Messages to Kafka

>[!QUOTE]  
>While we ignore errors that may occur while sending messages to Kafka brokers or in the brokers themselves, we may still get an exception if the producer encountered errors before sending the message to Kafka. Those can be, for example, a SerializationException when it fails to serialize the message, a Buffer ExhaustedException or TimeoutException if the buffer is full, or an InterruptException if the sending thread was interrupted (Page 52) #✂️
{ #ref-745647094}


---

>[!QUOTE]  
>To use callbacks, you need a class that implements the org.apache.kafka. clients.producer.Callback interface, which has a single function—on Completion(). (Page 54) #✂️
{ #ref-745647095}


---

>[!QUOTE]  
>The callbacks execute in the producer’s main thread. This guarantees that when we send two messages to the same partition one after another, their callbacks will be executed in the same order that we sent them. But it also means that the callback should be reasonably fast to avoid delaying the producer and preventing other messages from being sent. It is not recommended to perform a blocking operation within the callback. Instead, you should use another thread to perform any blocking operation concurrently. (Page 54) #✂️
{ #ref-745647096}


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
>acks=0 The producer will not wait for a reply from the broker before assuming the message was sent successfully (Page 55) #✂️
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
>linger.ms controls the amount of time to wait for additional messages before sending the current batch. KafkaProducer sends a batch of messages either when the current batch is full or when the linger.ms limit is reached (Page 59) #✂️
{ #ref-745647106}


---

>[!QUOTE]  
>bufer.memory This config sets the amount of memory the producer will use to buffer messages waiting to be sent to brokers (Page 59) #✂️
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
>Setting the retries parameter to nonzero and the max.in. flight.requests.per.connection to more than 1 means that it is possible that the broker will fail to write the first batch of messages, succeed in writing the second (which was already in-flight), and then retry the first batch and succeed, thereby reversing the order. Since we want at least two in-flight requests for performance reasons, and a high number of retries for reliability reasons, the best solution is to set enable.idempotence=true. This guarantees message ordering with up to five in-flight requests and also guarantees that retries will not introduce duplicates (Page 60) #✂️
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
>To avoid this, you can set enable.idempotence=true. When the idempotent producer is enabled, the producer will attach a sequence number to each record it sends. If the broker receives records with the same sequence number, it will reject the second copy and the producer will receive the harmless DuplicateSequenceException (Page 61) #✂️
{ #ref-745647114}


---

>[!QUOTE]  
>Enabling idempotence requires max.in.flight.requests.per. connection to be less than or equal to 5, retries to be greater than 0, and acks=all. If incompatible values are set, a ConfigException will be thrown. (Page 61) #✂️
{ #ref-745647115}


---

>[!QUOTE]  
>Starting in the Apache Kafka 2.4 producer, the round-robin algorithm used in the default partitioner when handling null keys is sticky. This means that it will fill a batch of messages sent to a single partition before switching to the next partition (Page 69) #✂️
{ #ref-745647116}


---

>[!QUOTE]  
>In addition to the default partitioner, Apache Kafka clients also provide RoundRobin Partitioner and UniformStickyPartitioner. These provide random partition assignment and sticky random partition assignment even when messages have keys. These are useful when keys are important for the consuming application (for example, there are ETL applications that use the key from Kafka records as the primary key when loading data from Kafka to a relational database), but the workload may be skewed, so a single key may have a disproportionately large workload. Using the UniformStickyPartitioner will result in an even distribution of workload across all partitions. (Page 69) #✂️
{ #ref-745647117}


---

>[!QUOTE]  
>Headers are often used for lineage to indicate the source of the data in the record, and for routing or tracing messages based on header information without having to parse the message itself (perhaps the message is encrypted and the router doesn’t have permissions to access the data) (Page 71) #✂️
{ #ref-745647118}


---

>[!QUOTE]  
>Kafka has three quota types: produce, consume, and request. Produce and consume quotas limit the rate at which clients can send and receive data, measured in bytes per second. Request quotas limit the percentage of time the broker spends processing client requests (Page 73) #✂️
{ #ref-745647119}


---

>[!QUOTE]  
>Kafka has three quota types: produce, consume, and request. Produce and consume quotas limit the rate at which clients can send and receive data, measured in bytes per second. Request quotas limit the percentage of time the broker spends processing client requests. (Page 73) #✂️
{ #ref-745647120}


---

>[!QUOTE]  
>Quotas that are specified in Kafka’s configuration file are static, and you can only modify them by changing the configuration and then restarting all the brokers. Since new clients can arrive at any time, this is very inconvenient. Therefore the usual method of applying quotas to specific clients is through dynamic configuration that can be set using kafka-config.sh or the AdminClient API. (Page 74) #✂️
{ #ref-745647121}


---

>[!QUOTE]  
>To protect the broker from misbehaved clients sending additional requests while being throttled, the broker will also mute the communication channel with the client for the period of time needed to achieve compliance with the quota. (Page 74) #✂️
{ #ref-745647122}


---

### Kafka Consumers: Reading Data From Kafka

>[!QUOTE]  
>Kafka consumers are typically part of a consumer group. When multiple consumers are subscribed to a topic and belong to the same consumer group, each consumer in the group will receive messages from a different subset of the partitions in the topic. (Page 78) #✂️
{ #ref-745647124}


---

>[!QUOTE]  
>Keep in mind that there is no point in adding more consumers than you have partitions in a topic—some of the consumers will just be idle (Page 79) #✂️
{ #ref-745647125}


---

>[!QUOTE]  
>To summarize, you create a new consumer group for each application that needs all the messages from one or more topics. You add consumers to an existing consumer group to scale the reading and processing of messages from the topics, so each additional consumer in a group will only get a subset of the messages (Page 80) #✂️
{ #ref-745647126}


---

>[!QUOTE]  
>Moving partition ownership from one consumer to another is called a rebalance. Rebalances are important because they provide the consumer group with high availability and scalability (allowing us to easily and safely add and remove consumers), but in the normal course of events they can be fairly undesirable. (Page 81) #✂️
{ #ref-745647127}


---

>[!QUOTE]  
>During an eager rebalance, all consumers stop consuming, give up their ownership of all partitions, rejoin the consumer group, and get a brand-new partition assignment. This is essentially a short window of unavailability of the entire consumer group. The length of the window depends on the size of the consumer group as well as on several configuration parameters (Page 81) #✂️
{ #ref-745647128}


---

>[!QUOTE]  
>Cooperative rebalances (also called incremental rebalances) typically involve reassigning only a small subset of the partitions from one consumer to another, and allowing consumers to continue processing records from all the partitions that are not reassigned. (Page 81) #✂️
{ #ref-745647129}


---

>[!QUOTE]  
>Initially, the consumer group leader informs all the consumers that they will lose ownership of a subset of their partitions, then the consumers stop consuming from these partitions and give up their ownership in them. In the second phase, the consumer group leader assigns these now orphaned partitions to their new owners. This incremental approach may take a few iterations until a stable partition assignment is achieved, but it avoids the complete “stop the world” unavailability that occurs with the eager approach (Page 82) #✂️
{ #ref-745647130}


---

>[!QUOTE]  
>Consumers maintain membership in a consumer group and ownership of the partitions assigned to them by sending heartbeats to a Kafka broker designated as the group coordinator (this broker can be different for different consumer groups) (Page 82) #✂️
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
>How Does the Process of Assigning Partitions to Consumers Work? When a consumer wants to join a group, it sends a JoinGroup request to the group coordinator. The first consumer to join the group becomes the group leader. The leader receives a list of all consumers in the group from the group coordinator (this will include all consumers that sent a heartbeat recently and that are therefore considered alive) and is responsible for assigning a subset of partitions to each consumer. It uses an implementation of PartitionAssignor to decide which partitions should be handled by which consumer. Kafka has few built-in partition assignment policies, which we will discuss in more depth in the configuration section. After deciding on the partition assignment, the consumer group leader sends the list of assignments to the GroupCoordinator, which sends this information to all the consumers. Each consumer only sees its own assignment—the leader is the only client process that has the full list of consumers in the group and their assignments. This process repeats every time a rebalance happens. Static Group Membership By default, the identity of a consumer as a member of its consumer group is transient. When consumers leave a consumer group, the partitions that were assigned to the consumer are revoked, and when it rejoins, it is assigned a new member ID and a new set of partitions through the rebalance protocol. All this is true unless you configure a consumer with a unique group.instance.id, which makes the consumer a static member of the group. When a consumer first joins a consumer group as a static member of the group, it is assigned a set of partitions according to the partition assignment strategy the group is using, as normal. However, when this consumer shuts down, it does not automatically leave the group—it remains a member of the group until its session times out. When the consumer rejoins the group, it is recognized with its static identity and is reassigned the same partitions it previously held without triggering a rebalance. The group coordinator that caches the assignment for each member of the group does not need to trigger a rebalance but can just send the cache assignment to the rejoining static member. If two consumers join the same group with the same group.instance.id, the second consumer will get an error saying that a consumer with this ID already exists. Static (Page 83) #✂️
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
>It is also possible to call subscribe with a regular expression. The expression can match multiple topic names, and if someone creates a new topic with a name that matches, a rebalance will happen almost immediately and the consumers will start consuming from the new topic. This is useful for applications that need to consume from multiple topics and can handle the different types of data the topics will contain. Subscribing to multiple topics using a regular expression is most commonly used in applications that replicate data between Kafka and another system or streams processing applications (Page 85) #✂️
{ #ref-745647140}


---

>[!QUOTE]  
>The parameter we pass to poll() is a timeout interval and controls how long poll() will block if data is not available in the consumer buffer. If this is set to 0 or if there are records available already, poll() will return immediately; otherwise, it will wait for the specified number of milliseconds. (Page 86) #✂️
{ #ref-745647141}


---

>[!QUOTE]  
>poll() returns a list of records. Each record contains the topic and partition the record came from, the offset of the record within the partition, and, of course, the key and the value of the record (Page 86) #✂️
{ #ref-745647142}


---

>[!QUOTE]  
>The poll loop does a lot more than just get data. The first time you call poll() with a new consumer, it is responsible for finding the GroupCoordinator, joining the consumer group, and receiving a partition assignment. If a rebalance is triggered, it will be handled inside the poll loop as well, including related callbacks. This means that almost everything that can go wrong with a consumer or in the callbacks used in its listeners is likely to show up as an exception thrown by poll(). (Page 87) #✂️
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
>fetch.max.bytes This property lets you specify the maximum bytes that Kafka will return whenever the consumer polls a broker (50 MB by default). It is used to limit the size of memory that the consumer will use to store data that was returned from the server, irrespective of how many partitions or messages were returned (Page 89) #✂️
{ #ref-745647147}


---

>[!QUOTE]  
>max.poll.records This property controls the maximum number of records that a single call to poll() will return (Page 89) #✂️
{ #ref-745647148}


---

>[!QUOTE]  
>max.partition.fetch.bytes This property controls the maximum number of bytes the server will return per partition (1 MB by default) (Page 89) #✂️
{ #ref-745647149}


---

>[!QUOTE]  
>session.timeout.ms and heartbeat.interval.ms The amount of time a consumer can be out of contact with the brokers while still considered alive defaults to 10 seconds. If more than session.timeout.ms passes without the consumer sending a heartbeat to the group coordinator, it is considered dead and the group coordinator will trigger a rebalance of the consumer group to allocate partitions from the dead consumer to the other consumers in the group. This property is closely related to heartbeat.interval.ms, which controls how frequently the Kafka consumer will send a heartbeat to the group coordinator, whereas session.timeout.ms controls how long a consumer can go without sending a heartbeat. Therefore, those two properties are typically modified together—heartbeat. interval.ms must be lower than session.timeout.ms and is usually set to one-third (Page 89) #✂️
{ #ref-745647150}


---

>[!QUOTE]  
>max.poll.interval.ms This property lets you set the length of time during which the consumer can go without polling before it is considered dead. As mentioned earlier, heartbeats and session timeouts are the main mechanism by which Kafka detects dead consumers and takes their partitions away (Page 90) #✂️
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
>auto.ofset.reset This property controls the behavior of the consumer when it starts reading a partition for which it doesn’t have a committed offset, or if the committed offset it has is invalid (usually because the consumer was down for so long that the record with that offset was already aged out of the broker). The default is “latest,” which means that lacking a valid offset, the consumer will start reading from the newest records (records that were written after the consumer started running). The alternative is “earliest,” which means that lacking a valid offset, the consumer will read all the data in the partition, starting from the very beginning. Setting auto.offset.reset to none will cause an exception to be thrown when attempting to consume from an invalid offset (Page 91) #✂️
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
>ofsets.retention.minutes This is a broker configuration, but it is important to be aware of it due to its impact on consumer behavior. As long as a consumer group has active members (i.e., members that are actively maintaining membership in the group by sending heartbeats), the last offset committed by the group for each partition will be retained by Kafka, so it can be retrieved in case of reassignment or restart. However, once a group becomes empty, Kafka will only retain its committed offsets to the duration set by this configuration—7 days by default. Once the offsets are deleted, if the group becomes active again it will behave like a brand-new consumer group with no memory of anything it consumed in the past (Page 93) #✂️
{ #ref-745647166}


---

>[!QUOTE]  
>We call the action of updating the current position in the partition an offset commit. Unlike traditional message queues, Kafka does not commit records individually. Instead, consumers commit the last message they’ve successfully processed from a partition and implicitly assume that every message before the last was also successfully processed (Page 94) #✂️
{ #ref-745647167}


---

>[!QUOTE]  
>How does a consumer commit an offset? It sends a message to Kafka, which updates a special __consumer_offsets topic with the committed offset for each partition. As long as all your consumers are up, running, and churning away, this will have no impact. However, if a consumer crashes or a new consumer joins the consumer group, this will trigger a rebalance. After a rebalance, each consumer may be assigned a new set of partitions than the one it processed before. In order to know where to pick up the work, the consumer will read the latest committed offset of each partition and continue from there (Page 94) #✂️
{ #ref-745647168}


---

>[!QUOTE]  
>With autocommit enabled, when it is time to commit offsets, the next poll will commit the last offset returned by the previous poll. It doesn’t know which events were actually processed, so it is critical to always process all the events returned by poll() before calling poll() again (Page 96) #✂️
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
>If you use a cooperative rebalancing algorithm, note that: • onPartitionsAssigned() will be invoked on every rebalance, as a way of notifying the consumer that a rebalance happened. However, if there are no new partitions assigned to the consumer, it will be called with an empty collection. • onPartitionsRevoked() will be invoked in normal rebalancing conditions, but only if the consumer gave up the ownership of partitions. It will not be called with an empty collection. • onPartitionsLost() will be invoked in exceptional rebalancing conditions, and the partitions in the collection will already have new owners by the time the method is invoked. If you implemented all three methods, you are guaranteed that during a normal rebalance, onPartitionsAssigned() will be called by the new owner of the partitions that are reassigned only after the previous owner completed onPartitionsRevoked() and gave up its ownership. (Page 102) #✂️
{ #ref-745647172}


---

>[!QUOTE]  
>If you want to start reading all messages from the beginning of the partition, or you want to skip all the way to the end of the partition and start consuming only new messages, there are APIs specifically for that: seekToBeginning(Collection<Topic Partition> tp) and seekToEnd(Collection<TopicPartition> tp). (Page 104) #✂️
{ #ref-745647173}


---

>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only consumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. (Page 105) #✂️
{ #ref-745647174}


---

>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only consumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. The WakeupException doesn’t need to be handled, but before exiting the thread, you must call consumer.close(). Closing the consumer will commit offsets if needed and will send the group coordinator a message that the consumer is leaving the group (Page 105) #✂️
{ #ref-745647175}


---

>[!QUOTE]  
>When you decide to shut down the consumer, and you want to exit immediately even though the consumer may be waiting on a long poll(), you will need another thread to call consumer.wakeup(). If you are running the consumer loop in the main thread, this can be done from ShutdownHook. Note that consumer.wakeup() is the only consumer method that is safe to call from a different thread. Calling wakeup will cause poll() to exit with WakeupException, or if consumer.wakeup() was called while the thread was not waiting on poll, the exception will be thrown on the next iteration when poll() is called. The WakeupException doesn’t need to be handled, but before exiting the thread, you must call consumer.close(). Closing the consumer will commit offsets if needed and will send the group coordinator a message that the consumer is leaving the group. (Page 105) #✂️
{ #ref-745647176}


---

>[!QUOTE]  
>When you know exactly which partitions the consumer should read, you don’t subscribe to a topic—instead, you assign yourself a few partitions. A consumer can either subscribe to topics (and be (Page 110) #✂️
{ #ref-745647177}


---

### Managing Apache Kafka Programmatically
