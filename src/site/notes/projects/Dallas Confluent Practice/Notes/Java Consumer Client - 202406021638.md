---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/java-consumer-client-202406021638/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:24.599+01:00","updated":"2024-06-27T22:33:31.548+01:00"}
---

# Java Consumer Client

Multiple topics can be passed as a list or regex pattern.

## References


## Flashcards

A consumer wants to read messages from a specific partition of a topic. How can this be achieved?::: Call `assign()` passing a Collection of `TopicPartitions` as the argument
<!--SR:!2024-07-19,22,250!2024-08-06,40,290-->

Select all the way for one consumer to subscribe simultaneously to the following topics - topic.history, topic.sports, topic.politics? (select two)
- `consumer.subscribePrefix("topic.");`
- `consumer.subscribe(Pattern.compile("topic\..*"));`
- `consumer.subscribe("topic.history"); consumer.subscribe("topic.sports"); consumer.subscribe("topic.politics");`
- `consumer.subscribe(Arrays.asList("topic.history", "topic.sports", "topic.politics"));`
?
- `consumer.subscribe(Pattern.compile("topic\..*"));`
- `consumer.subscribe(Arrays.asList("topic.history", "topic.sports", "topic.politics"));`
<!--SR:!2024-08-26,60,310-->

A consumer wants to read messages from partitions 0 and 1 of a topic topic1. Code snippet is shown below.
```java
consumer.subscribe(Arrays.asList("topic1"));
List<TopicPartition> pc = new ArrayList<>();
pc.add(new PartitionTopic("topic1", 0));
pc.add(new PartitionTopic("topic1", 1));
consumer.assign(pc);
```
?
Throws IllegalStateException subscribe() and assign() cannot be called by the same consumer, subscribe() is used to leverage the consumer group mechanism, while assign() is used to manually control partition assignment and reads assignment
<!--SR:!2024-07-07,10,248-->

How can you gracefully make a Kafka consumer to stop immediately polling data from Kafka and gracefully shut down a consumer application?:: Call consumer.wakeUp() and catch a WakeUpException
<!--SR:!2024-08-13,47,308-->