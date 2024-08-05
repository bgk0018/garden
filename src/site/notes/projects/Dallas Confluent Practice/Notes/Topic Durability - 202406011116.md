---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/topic-durability-202406011116/","tags":["📖","♣️/kafka"],"created":"2024-03-19T13:32:56.550-05:00","updated":"2024-07-15T21:22:08.370-05:00"}
---

# Topic Durability


For a [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]] of 3, Topic Durability can withstand 2 brokers loss.

As a rule, for a replication factor of N, you can permanently lose up to N-1 [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Brokers]] and still recover your data.


## References


## Flashcards

[[projects/Dallas Confluent Practice/Notes/Topic Durability - 202406011116\|Topic Durability]] is closely tied to
?
- [[projects/Dallas Confluent Practice/Notes/Topic Replication Factor - 202405302220\|Topic Replication Factor]]
- [[projects/Dallas Confluent Practice/Notes/Producer Acknowledgement - 202405302231\|Producer Acknowledgement]]
- [[Log Retention\|Log Retention]]
- [[Unclean Leader Election\|Unclean Leader Election]]
- [[Replication Throttling\|Replication Throttling]]
<!--SR:!2024-07-17,2,150-->