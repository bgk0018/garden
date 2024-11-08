---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-reliability-testing-202407152130/","tags":["📖","♣️/kafka"],"created":"2024-11-08T08:07:57.650-06:00","updated":"2024-11-08T09:43:56.853-06:00"}
---

# Kafka Reliability Testing

Reliability testing in Kafka involves three key layers:
1. Configuration validation
2. Application validation
3. Production monitoring

## Configuration Testing Tools

- VerifiableProducer: Produces numbered sequence messages
- VerifiableConsumer: Validates message sequence and reports gaps
- Trogdor: Kafka's fault injection framework

## Key Test Scenarios

1. **Leader Elections**
   - Kill leader broker
   - Measure recovery time
   - Verify no message loss

2. **Broker Failures**
   - Rolling restarts
   - Disk failures
   - Network partitions

3. **Client Resilience**
   - Network latency
   - Broker unavailability
   - Rebalance handling

## References

## Flashcards

What are the three layers of Kafka reliability testing?:: Configuration validation, application validation, and production monitoring
<!--SR:!2024-07-18,3,250-->

What tools does Kafka provide for reliability testing?:: VerifiableProducer, VerifiableConsumer, and Trogdor fault injection framework
<!--SR:!2024-07-19,4,250-->

What happens when a broker loses its ZooKeeper connection?:: Its ephemeral node is automatically removed but broker ID remains in other data structures
<!--SR:!2024-07-20,5,250--> 