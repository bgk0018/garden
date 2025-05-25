---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/topic-replication-factor-202405302220/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:29.637-05:00","updated":"2025-02-02T15:54:17.870-06:00"}
---


# Topic Replication Factor

[[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]] should have a replication factor > 1 (usually between 2 and 3)

This way if a [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] is down, another broker can serve the data.

![Pasted image 20230301214515.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301214515.webp)

## References

## Flashcards

Topic Replication Factor Formula:: Number of Replicas for each Partition
<!--SR:!2025-01-31,7,268-->

<!--SR:!2024-07-16,19,250-->

The minimum replication factor is:: 1
<!--SR:!2025-02-04,11,270-->

<!--SR:!2024-08-26,48,310-->

The maximum replication factor is:: The number of brokers in a cluster
<!--SR:!2025-02-01,7,250-->

<!--SR:!2024-09-05,70,310-->

The recommended replication factor is at least:: 3
<!--SR:!2025-01-26,3,250-->

<!--SR:!2024-09-01,66,310-->

Kafka's controller assigns replicas in what way:: distributed evenly to ensure load balancing
<!--SR:!2025-01-25,1,232-->

<!--SR:!2024-08-07,29,290-->
