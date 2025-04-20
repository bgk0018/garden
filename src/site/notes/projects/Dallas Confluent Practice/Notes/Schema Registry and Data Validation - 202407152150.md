---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/schema-registry-and-data-validation-202407152150/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:22.186-06:00","updated":"2025-02-02T15:54:17.867-06:00"}
---


# Schema Registry and Data Validation

## Schema Registry Role

1. **Validation**
   - Rejects incompatible schema changes
   - Validates before data reaches Kafka
   - Maintains schema version history

2. **Schema Evolution**
   - Forward compatibility: New schema readable by old consumers
   - Backward compatibility: Old schema readable by new consumers
   - Full compatibility: Both forward and backward

3. **Client Integration**
   - KafkaAvroSerializer for producers
   - KafkaAvroDeserializer for consumers
   - Local schema caching for performance

## Best Practices

1. Plan schema evolution strategy upfront
2. Test schema changes before production
3. Monitor schema registry metrics
4. Consider compatibility settings per topic

## References

## Flashcards

What happens when KafkaAvroDeserializer can't find schema in local cache?:: Fetches schema from Schema Registry
<!--SR:!2025-01-28,4,270-->

<!--SR:!2024-07-18,3,250-->

Adding a field without default in Avro is what type of schema evolution?:: Forward compatibility - old consumers can still read new records
<!--SR:!2025-01-25,1,232-->

<!--SR:!2024-07-19,4,250-->

Which component rejects incompatible schema changes?:: The Schema Registry, before data reaches Kafka brokers
<!--SR:!2025-01-28,4,272-->

<!--SR:!2024-07-20,5,250--> 
