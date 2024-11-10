---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/in-sync-replicas-management-202407152125/","tags":["♣️/kafka","📖"],"created":"2024-11-08T08:07:24.716-06:00","updated":"2024-11-10T13:38:06.010-06:00"}
---


# In-Sync Replicas Management

In-sync replicas (ISR) are crucial for Kafka's reliability guarantees. A replica is considered in-sync if it:

- Maintains an active ZooKeeper session
- Fetches messages from the leader regularly
- Catches up to most recent messages within configured time

## Key Configurations

1. **zookeeper.session.timeout.ms**
   - Time before broker considered dead if no heartbeat
   - Default: 18 seconds (since 2.5.0)
   - Higher values improve stability in cloud environments

2. **replica.lag.time.max.ms**
   - Maximum time a follower can lag behind leader
   - Default: 30 seconds (since 2.5.0)
   - Affects consumer latency

3. **min.insync.replicas**
   - Minimum replicas that must acknowledge writes
   - Works with acks=all for strongest durability
   - Partition becomes read-only if not met

## References

## Flashcards

What makes a replica considered "in-sync"?:: Active ZooKeeper session, regular fetches from leader, and caught up to recent messages

<!--SR:!2024-07-18,3,250-->

What happens when available replicas fall below min.insync.replicas?:: Partition becomes read-only for producers (but consumers can still read)

<!--SR:!2024-07-19,4,250-->

What is the purpose of replica.lag.time.max.ms?:: Defines maximum time a follower can lag behind leader before being removed from ISR

<!--SR:!2024-07-20,5,250--> 
