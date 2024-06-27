---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/message-anatomy-202405302129/","tags":["📖","♣️/kafka"],"created":"2024-03-19T18:32:56.710+00:00","updated":"2024-06-12T03:22:32.000+01:00"}
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
<!--SR:!2024-06-21,16,290-->
True/False a Message Value can be null: true  
The anatomy of a Topic Message:: a key, a value, compression type, headers, partition plus offset and system or user set timestamp
<!--SR:!2024-06-17,6,210-->