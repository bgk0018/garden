---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/producer-configuration-for-reliability-202407152140/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:32.448-05:00","updated":"2025-02-02T18:53:12.612-06:00"}
---


# Producer Configuration for Reliability

## Key Configuration Parameters

1. **Idempotence**
   - enable.idempotence=true prevents network-induced duplicates
   - Automatically sets retries and acks for safety
   - Small performance impact but stronger guarantees

2. **In-Flight Requests**
   - max.in.flight.requests.per.connection affects ordering
   - Higher values improve throughput but risk reordering with retries
   - Set to 1 for strict ordering with retries

3. **Delivery Timeouts**
   - delivery.timeout.ms controls total time for retry attempts
   - Should be greater than linger.ms + request.timeout.ms
   - Affects how long before giving up on failed sends

## Best Practices

1. Enable idempotence for exactly-once delivery
2. Use acks=all with min.insync.replicas for durability
3. Consider throughput vs ordering trade-offs
4. Implement proper error handling in callbacks

## References

## Flashcards

What configuration prevents network-induced duplicates in producers?:: enable.idempotence=true
<!--SR:!2025-01-28,4,270-->

<!--SR:!2024-07-18,3,250-->

What is the risk of increasing max.in.flight.requests while enabling retries?:: Message order may not be preserved if retries occur
<!--SR:!2025-01-25,4,270-->

<!--SR:!2024-07-19,4,250-->

What happens if you use producer.send().get()?:: Throughput decreases because it waits synchronously for broker response
<!--SR:!2025-01-25,2,232-->

<!--SR:!2024-07-20,5,250--> 
