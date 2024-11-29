---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/topic-configuration-management-202407152205/","tags":["♣️/kafka","📖"],"created":"2024-11-08T08:58:31.199-06:00","updated":"2024-11-10T13:50:24.000-06:00"}
---


# Topic Configuration Management

## Core Settings

1. **Replication Settings**
   - replication.factor: Number of replicas
   - min.insync.replicas: Minimum replicas for writes
   - unclean.leader.election.enable: Out-of-sync leader election

2. **Partition Management**
   - num.partitions: Initial partition count
   - auto.create.topics.enable: Automatic topic creation
   - delete.topic.enable: Topic deletion allowed

3. **Storage Settings**
   - retention.ms: Message retention time
   - retention.bytes: Maximum partition size
   - segment.bytes: Size of segment files

## Dynamic Configuration

- Topic configurations stored in ZooKeeper
- Can be modified without broker restart
- Changes affect only specified topics
- Monitored via kafka-topics.sh tool

## Monitoring and Validation

1. **Health Checks**
   - Check under-replicated partitions
   - Monitor in-sync replica count
   - Track partition leadership changes

2. **Configuration Validation**
   - Verify replication factor adequacy
   - Check min.insync.replicas setting
   - Validate partition count

## References

## Flashcards

What are the three most critical topic configurations for reliability?:: replication.factor, min.insync.replicas, and unclean.leader.election.enable

<!--SR:!2024-07-18,3,250-->

Where are dynamic topic configurations stored?:: In ZooKeeper

<!--SR:!2024-07-19,4,250-->

When does auto.create.topics.enable trigger topic creation?:: When a producer writes messages, a consumer reads messages, or any client requests metadata

<!--SR:!2024-07-20,5,250--> 
