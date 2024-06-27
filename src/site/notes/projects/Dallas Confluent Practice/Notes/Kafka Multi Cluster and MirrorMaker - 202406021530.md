---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-multi-cluster-and-mirror-maker-202406021530/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.255+01:00","updated":"2024-06-13T23:49:59.498+01:00"}
---

# Kafka Multi Cluster and MirrorMaker

Kafka can only operate well in a single region, so we need to leverage replication

Mirror Maker 2 - Open source Kafka connector that ships with Kafka

>[!WARNING]  
>Replicating doesn't preserve offsets, just data. Data at an offset in one cluster is not the same as the data at same offset in another cluster.

Replication: Active/Active, or Active/Passive (readonly)

# References


# Flashcards