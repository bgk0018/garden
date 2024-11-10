---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/message-anatomy-202405302129/","tags":["♣️/kafka","📖"],"created":"2024-08-29T16:41:19.232-05:00","updated":"2024-11-10T13:44:34.925-06:00"}
---


# Message Anatomy

- Key, can be null
- Value, can be null
- Compression Type
- [[permanent/Headers - 202303012040\|Headers]]
- [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partition]] + [[projects/Dallas Confluent Practice/Notes/Offset - 202405282304\|Offset]]
- Timestamp (system or user set)

## References

## Flashcards

True/False a Message Key can be null:: true

<!--SR:!2024-09-02,67,310-->

True/False a Message Value can be null: true  

The anatomy of a Topic Message:: a key, a value, compression type, headers, partition plus offset and system or user set timestamp

<!--SR:!2024-07-17,8,210-->

Headers are often used for:: lineage to indicate the source of the data in the record and for routing or tracing messages without having to parse the message itself

<!--SR:!2024-07-19,4,272-->
