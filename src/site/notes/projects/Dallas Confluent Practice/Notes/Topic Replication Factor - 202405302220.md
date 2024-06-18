---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/topic-replication-factor-202405302220/","tags":["📖","♣️/kafka"],"created":"2024-03-19T13:32:56.546-05:00","updated":"2024-06-07T15:12:42.935-05:00"}
---

# Topic Replication Factor

[[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]] should have a replication factor > 1 (usually between 2 and 3)

This way if a [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] is down, another broker can serve the data.

![Pasted image 20230301214515.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301214515.webp)

## References


## Flashcards

Topic Replication Factor Formula:: Number of Replicas for each Partition
<!--SR:!2024-06-14,8,250-->
The minimum replication factor is:: 1
<!--SR:!2024-06-18,13,290-->
The maximum replication factor is:: The number of brokers in a cluster
<!--SR:!2024-06-22,17,290-->
The recommended replication factor is at least:: 3
<!--SR:!2024-06-21,16,290-->
Kafka's controller assigns replicas in what way:: distributed evenly to ensure load balancing
<!--SR:!2024-06-15,8,270-->