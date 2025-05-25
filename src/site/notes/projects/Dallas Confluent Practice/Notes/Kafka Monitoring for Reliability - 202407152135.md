---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-monitoring-for-reliability-202407152135/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:33.801-05:00","updated":"2025-01-24T22:18:30.311-06:00"}
---


# Kafka Monitoring for Reliability

## Key Metrics to Monitor

1. **Producer Metrics**
   - Error rate per record
   - Retry rate per record
   - Average request latency

2. **Consumer Metrics**
   - Consumer lag
   - Commit success rate
   - Rebalance events

3. **Broker Metrics**
   - Under-replicated partitions
   - Request handler utilization
   - Request timing

## Monitoring Tools

- JMX metrics from clients
- Burrow for consumer lag monitoring
- Confluent Control Center for end-to-end monitoring

## Best Practices

1. Monitor both client and broker metrics
2. Track message timestamps for end-to-end latency
3. Set up alerts for critical thresholds
4. Monitor failed request rates with error types

## References

## Flashcards

What are the most important producer metrics for reliability?:: Error rate and retry rate per record
<!--SR:!2025-01-25,1,210-->

<!--SR:!2024-07-18,3,250-->

What is the most important consumer metric to monitor?:: Consumer lag - indicates how far behind real-time the consumer is
<!--SR:!2025-01-26,3,250-->

<!--SR:!2024-07-19,4,250-->

What tool is recommended for monitoring consumer lag?:: Burrow - provides more sophisticated lag monitoring than simple threshold alerts
<!--SR:!2025-01-25,1,226-->

<!--SR:!2024-07-20,5,250--> 
