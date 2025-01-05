---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/consumer-incremental-cooperative-rebalance-202403301631/","tags":["📖"],"created":"2024-08-29T16:38:59.674-05:00","updated":"2024-11-10T13:35:39.693-06:00"}
---


# Consumer Incremental Cooperative Rebalance

## References

## Flashcards

Which events will initiate the consumer rebalancing? (Pick three)

- Consumers joins the consumer group
- A new producer starts writing messages to the topic in question
- A consumer leaves the group
- A new broker is added to the cluster
- Partitions are added to the topic  
?
- Consumers joins the consumer group
- A consumer leaves the group
- Partitions are added to the topic
