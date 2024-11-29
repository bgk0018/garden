---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-internals-202411021210/","tags":["♣️/kafka","📖"],"created":"2024-11-02T12:10:10.631-05:00","updated":"2024-11-10T13:41:36.000-06:00"}
---


# Kafka Internals

## Cluster Membership

- Kafka uses ZooKeeper to maintain broker membership in a cluster
- Each broker registers in ZooKeeper using an ephemeral node
- Broker registration includes:
  - Unique broker ID (integer)
  - ZooKeeper connection details
  - Broker metadata

## Controller

- One broker is elected as the controller
- Controller responsibilities:
  - Partition leader election
  - Monitoring broker failures
  - Updating cluster metadata
- Controller election process:
  - First broker to create `/controller` node in ZooKeeper becomes controller
  - Uses controller epoch numbers to prevent split-brain scenarios
  - Other brokers watch controller node for changes

## Physical Storage

- Messages stored in segments within partitions
- Each partition has two types of indexes:
  - Offset index: Maps message offsets to physical position
  - Timestamp index: Maps timestamps to message offsets
- Index characteristics:
  - Segmented like the log files
  - Can be regenerated if corrupted
  - No checksums maintained

## Log Compaction

- Alternative to time-based retention
- Partition structure:
  - Clean portion: Previously compacted messages
  - Dirty portion: New messages since last compaction
- Compaction process:
  - Triggered when dirty records reach threshold
  - Maintains latest value per key
  - Preserves tombstone messages for deletions
- Configuration controls:
  - `min.compaction.lag.ms`
  - `max.compaction.lag.ms`
  - `log.cleaner.enabled`

## Request Handling

- Zero-copy optimization for better performance
- No message transformation at broker level
- Supports both synchronous and asynchronous operations
- Quotas available for:
  - Produce requests
  - Consume requests
  - Request processing time

# References

- Kafka: The Definitive Guide
- Confluent Documentation

# Flashcards

What are the two types of indexes maintained by Kafka for each partition?:: Offset index (mapping offsets to physical positions) and Timestamp index (mapping timestamps to offsets)

<!--SR:!2024-07-16,3,250-->

How does Kafka prevent split-brain scenarios with controllers?:: Uses controller epoch numbers - each new controller gets a higher number and messages from controllers with old epoch numbers are ignored

<!--SR:!2024-07-17,4,270-->

What happens when a broker loses its ZooKeeper connection?:: Its ephemeral node is automatically removed, but its broker ID still exists in other data structures

<!--SR:!2024-07-18,5,290-->

What are the two portions of a compacted partition?:: Clean portion (previously compacted messages) and Dirty portion (messages written after last compaction)

<!--SR:!2024-07-19,6,310-->

What triggers log compaction in Kafka?:: When the ratio of dirty records reaches the configured threshold (default 50%) and a segment is closed

<!--SR:!2024-07-20,7,330-->

What is the role of the Kafka Controller?:: Responsible for partition leader election, monitoring broker failures, and maintaining cluster metadata

<!--SR:!2024-07-21,8,350-->

How does Kafka handle broker registration in a cluster?:: Each broker creates an ephemeral node in ZooKeeper with a unique broker ID

<!--SR:!2024-07-22,9,370-->

What happens if a Kafka index becomes corrupted?:: It can be safely regenerated from the matching log segment by rereading the messages

<!--SR:!2024-07-23,10,390-->
