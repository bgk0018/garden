---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-connect-source-202406022136/","tags":["📖","♣️/kafka"],"created":"2024-06-03T08:22:24.950-05:00","updated":"2024-06-27T15:55:09.530-05:00"}
---

# Kafka Connect Source



## References


## Flashcards

You are using JDBC source connector to copy data from 2 tables to two Kafka topics. There is one connector created with max.tasks equal to 2 deployed on a cluster of 3 workers. How many tasks are launched?:: 2, we have two tables, so the max number of tasks is 2
<!--SR:!2024-07-23,26,270-->