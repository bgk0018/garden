---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/reliable-data-delivery-202407152100/","tags":["📖","♣️/kafka"],"created":"2024-11-08T08:05:59.660-06:00","updated":"2024-11-08T09:43:57.019-06:00"}
---

# Reliable Data Delivery

Reliability is a system-wide concern that requires coordination between Kafka administrators, Linux administrators, network/storage administrators, and application developers.

## Core Reliability Guarantees

Kafka provides these key guarantees:

- Message order is preserved within a partition
- Messages are considered "committed" when written to all in-sync replicas
- Committed messages won't be lost as long as one replica remains alive
- Consumers can only read committed messages

## Broker Configuration for Reliability

Three key broker configurations affect reliability:

1. **Replication Factor**
   - Higher replication = better availability but more storage/network cost
   - Consider:
     - Availability needs
     - Durability requirements  
     - Throughput impact
     - End-to-end latency
     - Hardware costs

2. **Unclean Leader Election** 
   - Controls if out-of-sync replicas can become leader
   - Default: false (safer)
   - True allows higher availability but risks data loss

3. **Minimum In-Sync Replicas**
   - Sets minimum replicas needed for writes
   - Prevents single point of failure
   - Example: min.insync.replicas=2 with 3 replicas means producers need 2 in-sync replicas to write

## Producer Reliability

Key producer configurations:

1. **acks Setting**
   - acks=0: Fire and forget
   - acks=1: Leader acknowledgment
   - acks=all: All in-sync replicas acknowledge

2. **Retries**
   - Use delivery.timeout.ms to control retry window
   - enable.idempotence=true prevents duplicates
   - Handle non-retriable errors in application code

## Consumer Reliability

Key consumer considerations:

1. **Offset Management**
   - Commit offsets only after processing
   - Balance commit frequency vs duplicate processing
   - Handle rebalances properly

2. **Configuration**
   - group.id controls consumer grouping
   - auto.offset.reset controls start position
   - enable.auto.commit controls commit behavior
   - auto.commit.interval.ms sets commit frequency

## Validation Approaches

1. **Configuration Testing**
   - Use VerifiableProducer and VerifiableConsumer
   - Test leader elections and restarts
   - Validate behavior matches expectations

2. **Application Testing**
   - Test under various failure conditions
   - Validate offset management
   - Test rebalance handling

3. **Production Monitoring**
   - Monitor producer error/retry rates
   - Track consumer lag
   - Validate end-to-end data flow
   - Watch broker error metrics

## References

## Flashcards

What are Kafka's core reliability guarantees?:: 1) Message order in partition 2) Committed when written to all in-sync replicas 3) No loss if one replica alive 4) Consumers only read committed messages
<!--SR:!2024-07-18,3,250-->

What are the three key broker configurations affecting reliability?:: 1) Replication Factor 2) Unclean Leader Election 3) Minimum In-Sync Replicas
<!--SR:!2024-07-19,4,270-->

What does setting acks=all mean for producers?:: The leader will wait for all in-sync replicas to acknowledge before responding. This provides the strongest durability guarantee but highest latency.
<!--SR:!2024-07-20,5,270-->

What is the main way consumers can lose messages?:: By committing offsets for messages they've read but haven't completely processed yet
<!--SR:!2024-07-21,6,270-->

What does unclean.leader.election.enable=false prevent?:: Prevents out-of-sync replicas from becoming leaders, which could cause data loss but may reduce availability
<!--SR:!2024-07-22,7,270--> 