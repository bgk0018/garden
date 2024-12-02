---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-controller-and-leadership-202407152155/","tags":["♣️/kafka","📖"],"created":"2024-11-08T08:11:13.129-06:00","updated":"2024-11-10T13:41:09.531-06:00"}
---


# Kafka Controller and Leadership

## Broker Roles

Brokers can serve three distinct roles:

1. Leader
2. Group Coordinator
3. Controller

## Controller Responsibilities

1. **Partition Management**
   - Leader election for partitions
   - Monitoring broker failures
   - Maintaining cluster metadata

2. **Split-Brain Prevention**
   - Uses controller epoch numbers
   - Higher numbers for new controllers
   - Ignores messages from old epochs

3. **ZooKeeper Integration**
   - Controller election via ZooKeeper
   - Only one active controller at a time
   - Automatic failover on controller failure

## Leadership Changes

1. **Planned Changes**
   - Rolling restarts
   - Broker maintenance
   - Configuration updates

2. **Unplanned Changes**
   - Broker failures
   - Network partitions
   - ZooKeeper connection loss

## References

## Flashcards

What are the three possible roles a broker can have?:: Leader, Group Coordinator, and Controller

<!--SR:!2024-07-18,3,250-->

How does Kafka prevent split-brain with controllers?:: Uses controller epoch numbers - higher numbers for new controllers and ignores old epoch messages

<!--SR:!2024-07-19,4,250-->

What happens when a broker loses ZooKeeper connection?:: Its ephemeral node is removed but broker ID remains in other data structures

<!--SR:!2024-07-20,5,250--> 
