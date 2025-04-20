---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/log-compaction-and-retention-202407152210/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:19.187-06:00","updated":"2025-02-02T15:54:17.846-06:00"}
---


# Log Compaction and Retention

## Log Cleanup Policies

1. **Delete Policy** (default for user topics)
   - Based on message age (default 1 week)
   - Based on log size (default infinite)
   - Controlled by log.cleanup.policy=delete

2. **Compact Policy** (default for __consumer_offsets)
   - Deletes based on message keys
   - Maintains latest value per key
   - Controlled by log.cleanup.policy=compact

## Retention Configuration

1. **Time-based Retention**
   - log.retention.hours (default 168)
   - log.retention.minutes
   - log.retention.ms
   - Smallest unit takes precedence

2. **Size-based Retention**
   - log.retention.bytes
   - Controls max size per partition
   - Default is -1 (unlimited)

## Log Compaction Behavior

1. **Timing**
   - Evaluated when segments close
   - Polls every 15 seconds (log.cleaner.backoff.ms)
   - Triggered by dirty ratio threshold

2. **Important Notes**
   - Preserves message order
   - Doesn't prevent duplicates in real-time
   - Offsets remain immutable
   - Deleted records visible for delete.retention.ms

## References

## Flashcards

How often is log compaction evaluated?:: Every time a segment is closed and if enough data is "dirty"
<!--SR:!2025-01-26,3,250-->

<!--SR:!2024-07-18,3,250-->

What are the two log cleanup policies in Kafka?:: delete (age/size based) and compact (key based)
<!--SR:!2025-01-27,2,232-->

<!--SR:!2024-07-19,4,250-->

Which retention setting takes precedence when multiple are configured?:: The smallest unit (ms over minutes over hours)
<!--SR:!2025-01-28,4,270-->

<!--SR:!2024-07-20,5,250--> 
