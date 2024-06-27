---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/exactly-once-semantics-theory-202406021527/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.171+01:00","updated":"2024-06-03T14:32:00.142+01:00"}
---

# Exactly Once Semantics Theory

## What's Exactly Once?

- Is the ability to guarantee that data processing on each message will happen only once, and that pushing the message back to kafka will also happen effectively only once
- Guaranteed when both input and output system is Kafka, not for Kafka to any external Systems
- When does the problem arise?

## Exactly Once in Kafka

- The producers are now idempotent (If the same message is sent twice or more due to retries, Kafka will make sure to only keep one copy of it)
- You can write multiple messages to different Kafka topics as part of one transaction (either all are written or none is written)

## What's the problem with At Least Once Semantics anyway?

- Cases when it's not acceptable to have at least once?
	- Getting the exact count by key for a stream
	- Summing up bank transactions
	- Any operation that is not idempotent
	- Any financial computation
- Cases when it's acceptable at have at least once:
	- Operations on time windows
	- Approximate operations
	- Idempotent operations

## How to do exactly once in Kafka streams?

- KafkaStreams properties

# References


# Flashcards