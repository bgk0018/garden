---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/consumer-groups-202405302143/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:41:19.216-05:00","updated":"2024-11-08T09:43:56.644-06:00"}
---

# Consumer Groups


All the [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] in an application read data as a [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Group]].

Each [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]] within a group reads from exclusive partitions.

If the number of [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] exceeds the number of available [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]] in a [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topic]], then all [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] over the max number of [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]] will be inactive.

It is acceptable for multiple Consumer Groups to read from the same [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topic]] [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]].

To create distinct consumer groups in [[projects/Dallas Confluent Practice/Notes/Apache Kafka - 202302211117\|Apache Kafka]], you use the consumer property `group.id`

![Pasted image 20230301205448.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301205448.webp)

![Pasted image 20230301205532.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301205532.webp)

![Pasted image 20230301205821.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301205821.webp)

## References


## Flashcards

[[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Groups]]::: A collection of consumers that work together to read and process messages from [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]].
<!--SR:!2024-09-13,66,310!2024-08-29,51,310-->
Each [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]] within a [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Groups]] reads:: a subset of partitions ensuring that every message is read by only one consumer within the group.
<!--SR:!2024-08-28,50,310-->
[[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partition]] count limits what in a [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Groups]]:: the number of active [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]]
<!--SR:!2024-08-28,50,310-->
True/false it is acceptable for multiple [[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Groups]] to read from the same [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topic]] [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]]:: true
<!--SR:!2024-09-07,72,310-->
[[projects/Dallas Confluent Practice/Notes/Consumer Groups - 202405302143\|Consumer Groups]] are uniquely identified by::: `group.id`
<!--SR:!2024-09-07,72,310!2024-08-23,57,310-->
A topic receives all the orders for the products that are available on a commerce site. Two applications want to process all the messages independently - order fulfilment and monitoring. The topic has 4 partitions, how would you organise the consumers for optimal performance and resource usage?:: Create two consumer groups for two applications with 4 consumers in each
<!--SR:!2024-08-19,53,300-->

There are two consumers C1 and C2 belonging to the same group G subscribed to topics T1 and T2. Each of the topics has 3 partitions. How will the partitions be assigned to consumers with PartitionAssignor being RoundRobinAssignor?:: C1 will be assigned partitions 0 and 2 from T1 and partition 1 from T2. C2 will have partition 1 from T1 and partitions 0 and 2 from T2.
<!--SR:!2024-09-09,74,320-->

Which actions will trigger partition rebalance for a consumer group? (select three)
- A consumer in a consumer group shuts down
- Add a new consumer to consumer group
- Remove a broker from the cluster
- Add a broker to the cluster
- Increase partitions of a topic
?
- A consumer in a consumer group shuts down
- Add a new consumer to consumer group
- Increase partitions of a topic
Rebalance occurs when a new consumer is added, removed or consumer dies or paritions increased.
<!--SR:!2024-09-11,64,329-->

Two consumers share the same group.id (consumer group id). Each consumer will:: Read all the data on mutual exclusive partitions
<!--SR:!2024-09-26,73,334-->

You have a consumer group of 12 consumers and when a consumer gets killed by the process management system, rather abruptly, it does not trigger a graceful shutdown of your consumer. Therefore, it takes up to 10 seconds for a rebalance to happen. The business would like to have a 3 seconds rebalance time. What should you do? (select two)
- Decrease session.timeout.ms
- decrease max.poll.interval.ms
- Increase heartbeat.interval.ms
- Decrease heartbeat.interval.ms
- increase max.poll.interval.ms
- Increase session.timeout.ms
?
- Decrease session.timeout.ms
- Decrease heartbeat.interval.ms
session.timeout.ms must be decreased to 3 seconds to allow for a faster rebalance, and the heartbeat thread must be quicker, so we also need to decrease heartbeat.interval.ms
<!--SR:!2024-07-28,13,274-->