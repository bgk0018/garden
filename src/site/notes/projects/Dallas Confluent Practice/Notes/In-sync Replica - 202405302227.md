---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/in-sync-replica-202405302227/","tags":["📖","♣️/kafka"],"created":"2024-03-19T13:32:56.765-05:00","updated":"2024-06-05T22:53:32.567-05:00"}
---

# In-sync Replica


An ISR is a [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] who is not a [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] put contains a replicate of a given [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topic]].

The number of ISR is dictated by the [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]] being 2+.

## References


## Flashcards

A [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] who is not a [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] but contains a replicate of a given [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]]::: [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replica]]
<!--SR:!2024-06-20,15,290!2024-06-22,17,290-->
Full ISR::: ISR Count = [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]]
<!--SR:!2024-06-21,16,290!2024-06-20,15,290-->
Partial ISR::: ISR Count < [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]]
<!--SR:!2024-06-15,10,270!2024-06-17,12,270-->
[[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replica]] is involved in leader election by::: being in the candidate pool for partition leader election
<!--SR:!2024-06-19,14,290!2024-06-19,14,290-->
