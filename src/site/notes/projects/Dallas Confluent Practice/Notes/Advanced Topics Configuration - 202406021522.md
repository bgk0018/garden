---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/advanced-topics-configuration-202406021522/","tags":["♣️/kafka","📖"],"created":"2024-06-01T21:20:02.236-05:00","updated":"2024-11-10T12:52:39.000-06:00"}
---


# Advanced Topics Configuration

## Changing a Topic Configuration

- There are default configurations on all brokers for creating topics
- You may want to change some of these defaults when you create for performance and topic behavior purposes
	- Replication factor
	- Number of partitions
	- Message size
	- Compression
	- Log CleanUp Policy
	- Min Insync Replicas
	- etc

You can use `kafka-configs` CLI to add/alter a config value

Example `kafka-configs --bootstrap-server localhost:9092 --entity-type topics --entity-name configured-topic --alter --add-config min.insync.replicas=2`

## Segment and Indexes

Topics are made of partitions and partitions are made of segments. There's only one active segment at a time. The active segment is the one being written to.

Active segment can change either based on time or bytes in the segment:

- `log.segment.bytes`
- `log.segment.ms`

2 indexes are available for segments:

- Positional offset in the partition (file position 1, 2, 3)
- Timestamp based offset

These help kafka find messages in the correct segment.

- Smaller `log.segment.bytes` (default 1gb) means:
	- More segments per partition
	- Log Compaction happens more often
	- Kafka must keep more files opened (which can leead to an error of 'too many open files')

We want to tune our segment count based on our throughput (high throughput versus low throughput)

- Smaller `log.segment.ms` (default 1 week)
	- Max frequency for log compaction (more frequent)

How often do I need log compaction to happen? Tune this setting

## Log Cleanup Policies

Log cleanup: Make data expire

- `log.cleanup.policy=delete` default for user topics
	- Deletes based on age of data (default is a week, same as the `log.segment.ms`)
	- Delete based on max size of log (default is -1 which is infinite)
- `log.cleanup.policy=compact` (kafka default for topic `__consumer_offsets`)
	- Deletes based on keys of your messages
	- Will delete old duplicate keys after the active segment is committed

This allows you to control the size of data on disk and limits maintenance work on the cluter

- Log clean happens:
	- On you partition segments
	- Smaller/more segments means that log cleanup happens more often
	- Log cleanup shouldn't happen too often as it eats cpu and ram
	- Polls every 15 seconds (`log.cleaner.backoff.ms`)

## Log Cleanup Delete

- `log.retention.hours`
	- Number of hours to keep data for (default is 168 - one week)
	- Higher number means more disk space
	- Lower number means less data is retained
- `log.retention.bytes`
	- Max size in Bytes for each partition 
	- useful to keep the size of a log under a threshold

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330175918393.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330175918393.webp)

## Log Compaction Theory

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330180109019.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330180109019.webp)

- Any consumer that is reading from the tail of a log (current data) will still see all the messages sent to the topic
- Ordering of messages is kept, log compaction only removes some messages, but does not re-order them
- The offset of a message is immutable, offsets are just skipped if a message is missing
- Deleted records can still be seen by consumers for a period of `delete.retention.ms`

Mythbusting:

- Log compaction does not prevent you from pushing duplicate data to kafka
	- de-dupe is done after a segment is committed
	- Your consumers will still read from tail as soon as the data arrives
- It doesn't prevent you from reading duplicate data from Kafka
	- Same points as above
- Log Compaction can fail from time to time
	- It is an optimization and it the compaction thread might crash
	- Make sure you assign enough memory to it and that it gets triggered
	- Restart kafka if log compaction is broken

> [!NOTE]  
> You can't trigger log compaction using an api call currently

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330180532927.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330180532927.webp)

## Unclean Leader Election

`unclean.leader.election.enable`, only turn this on if data loss is OK, false by default

Basically what this says if if your In Sync Replicas go offline and have out of sync replicas up, instead of waiting for an insync replica to come back online, you can enable the election of a leader (out of sync replica)

>[!NOTE]  
>Generally don't use

## Large Messages in Kafka

>[!NOTE]  
>Generally don't. Large messages are considered inefficient and an anti-pattern

- Use an external store and send a reference of that message to kafka (preferred)
- Modify the kafka parameters to allow for larger messages, must set:
	- Broker: `message.max.bytes`
	- Topic `max.message.bytes`
	- Broker: `replica.fetch.max.bytes`
	- Consumer: `max.partition.fetch.bytes`
	- Producer: `max.request.size`

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330181341202.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330181341202.webp)

# References

# Flashcards
