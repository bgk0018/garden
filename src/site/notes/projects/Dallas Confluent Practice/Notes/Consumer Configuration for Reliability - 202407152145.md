---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/consumer-configuration-for-reliability-202407152145/","tags":["♣️/kafka","📖"],"created":"2025-02-22T11:19:55.616-06:00","updated":"2025-02-02T18:51:18.982-06:00"}
---


# Consumer Configuration for Reliability

## Critical Settings

1. **Processing Time Settings**
   - max.poll.interval.ms: Maximum time between polls
   - session.timeout.ms: Time before consumer considered dead
   - heartbeat.interval.ms: Frequency of heartbeats

2. **Offset Management**
   - enable.auto.commit: Whether to commit automatically
   - auto.commit.interval.ms: How often to auto-commit
   - isolation.level: read_committed or read_uncommitted

3. **Group Management**
   - group.id: Identifies consumer group
   - partition.assignment.strategy: How partitions are assigned

## Best Practices

1. Adjust max.poll.interval.ms for long-running processing
2. Manual offset commits for exactly-once processing
3. Proper error handling in poll loops
4. Consider isolation level based on requirements

## References

## Flashcards

What should you do if processing takes longer than max.poll.interval.ms?:: Increase max.poll.interval.ms to prevent unnecessary rebalances
<!--SR:!2025-01-25,2,230-->

<!--SR:!2024-07-18,3,250-->

How do consumers commit offsets in Kafka?:: Through interaction with the Group Coordinator broker
<!--SR:!2025-01-25,1,170-->

<!--SR:!2024-07-19,4,250-->

What happens if a consumer commits offset 2000, fails to get confirmation, then commits 3000 successfully?:: No action needed - offset 3000 implies all messages up to that point were processed
<!--SR:!2025-01-27,3,259-->

<!--SR:!2024-07-20,5,250--> 
