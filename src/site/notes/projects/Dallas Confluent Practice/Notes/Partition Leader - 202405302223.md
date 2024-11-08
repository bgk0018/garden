---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/partition-leader-202405302223/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:41:19.200-05:00","updated":"2024-11-08T09:43:56.961-06:00"}
---

# Partition Leader

At any time, only one [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] can be a Partition Leader for a given [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partition]].

[[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] can only send data to the [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] that is a Partition Leader.

[[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] can only request data from the [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] that is Partition Leader.

>[!NOTE]  
>Since Kafka v2.4, it's possible to read from the closest replica.

> [!WARNING]  
> If you are setting up a modern-day Kafka implementation, do not use Zookeeper as a configuration in your Kafka clients, and other programs that connect to Kafka


![Pasted image 20230301214746.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301214746.webp)


## References


## Flashcards

How many [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Brokers]] can be a [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] for a given [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partition]]?:: 1
<!--SR:!2024-08-18,52,310-->
[[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] can only send data to:: The [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]]
<!--SR:!2024-07-21,6,210-->
[[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] can request data from:: The closest [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replica]] or the [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]]
<!--SR:!2024-07-19,4,170-->