---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/high-watermark-and-message-visibility-202407152200/","tags":["📖","♣️/kafka"],"created":"2024-11-08T08:12:26.104-06:00","updated":"2024-11-08T09:43:56.701-06:00"}
---

# High Watermark and Message Visibility

## High Watermark Concept

The high watermark (HW) is a crucial mechanism in Kafka that:
1. Controls message visibility to consumers
2. Ensures consistency across replicas
3. Prevents reading uncommitted messages

## Message Visibility Rules

1. **Producer Side**
   - Messages written to leader
   - Replicated based on acks setting
   - HW advances after ISR replication

2. **Consumer Side**
   - Can only read up to HW
   - May see delay with acks=1
   - Guarantees consistent view across consumers

## Impact on Reliability

1. **Data Consistency**
   - Prevents reading uncommitted data
   - Ensures all consumers see same data
   - Handles replica failures gracefully

2. **Failure Scenarios**
   - Leader failures don't lose committed data
   - Follower catch-up uses HW
   - Replication maintains consistency

## References

## Flashcards

When does the high watermark advance?:: When all in-sync replicas have replicated the latest offsets
<!--SR:!2024-07-18,3,250-->

Under what conditions will consumers see messages with acks=1?:: When the high watermark has advanced, even if followers haven't replicated yet
<!--SR:!2024-07-19,4,250-->

What's the relationship between high watermark and committed messages?:: Consumers can only read up to the high watermark, which represents committed messages
<!--SR:!2024-07-20,5,250--> 