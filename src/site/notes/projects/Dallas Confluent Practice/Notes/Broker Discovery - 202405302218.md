---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/broker-discovery-202405302218/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:41:19.066-05:00","updated":"2024-06-27T15:48:01.000-05:00"}
---

# Broker Discovery

Every [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] is also called a bootstrap server.

This means you only need to connect to one [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]], and the client will know to be connected to the entire [[projects/Dallas Confluent Practice/Notes/Cluster - 202303012114\|Cluster]].

Each [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] knows about all [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Brokers]], [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]], and [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]] 

![Pasted image 20230301214215.webp](/img/user/projects/Dallas%20Confluent%20Practice/Pasted%20image%2020230301214215.webp)


## References


## Flashcards

Each [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Broker]] in a [[projects/Dallas Confluent Practice/Notes/Cluster - 202303012114\|Cluster]] knows about:: all [[projects/Dallas Confluent Practice/Notes/Broker - 202405302214\|Brokers]], [[projects/Dallas Confluent Practice/Notes/Topics - 202405282249\|Topics]], and [[projects/Dallas Confluent Practice/Notes/Partitions - 202405282258\|Partitions]]
<!--SR:!2024-08-20,54,310-->