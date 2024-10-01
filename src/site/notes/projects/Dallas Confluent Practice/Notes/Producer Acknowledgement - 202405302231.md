---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/producer-acknowledgement-202405302231/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:41:19.107-05:00","updated":"2024-07-09T17:22:05.000-05:00"}
---

# Producer Acknowledgement

[[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] can choose to receive Acknowledgement of data writes.

acks=0: [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]] won't wait for Acknowledgement (possible data loss)  
acks=1: [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]] will wait for [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] acknowledgement (limited data loss)  
acks=all: [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] and [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replicas]] acknowledgement (no data loss)

## References



## Flashcards

T/F [[projects/Dallas Confluent Practice/Notes/Producer Acknowledgement - 202405302231\|Producer Acknowledgement]] is required:: false, acks=0 requires no acknowledgement
<!--SR:!2024-08-19,53,310-->
acks=0::: [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]] won't wait for acknowledgement (possible data loss)
<!--SR:!2024-08-18,52,310!2024-09-10,63,310-->
acks=1::: [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]] will wait for [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] acknowledgement
<!--SR:!2024-09-05,58,310!2024-09-06,59,310-->
acks=all: [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producer]] will wait for [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] and [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replica]] acknowledgement (Out of sync replicas are not waited on)

