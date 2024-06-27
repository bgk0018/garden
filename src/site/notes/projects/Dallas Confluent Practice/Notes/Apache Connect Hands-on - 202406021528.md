---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/apache-connect-hands-on-202406021528/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.622+01:00","updated":"2024-06-03T14:32:00.189+01:00"}
---

# Kafka Connect Hands-on

## What is Kafka Connect

Simplifies the process of getting data out of and into different sources and sinks

Kafka Connect are a series of connectors that someone else has written for very common source and sinks

## Kafka Connect Architecture

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240421093804909.webp](/img/user/assets/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240421093804909.webp)

## Kafka Connect Concepts

- Kafka Connect Cluster has multiple loaded Connectors
	- Each connector is a reusable piece of code
	- Many connectors exist in the open source world
- Connectors + User Configuration = Tasks
	- A task is linked to a connector configuration
	- A job configuration may spawn multiple tasks
- Tasks are executed by  Kafka Connect Workers
	- A worker is a single java process
	- A worker can be standalone or in a cluster

- Standalone
	- A single process runs your connectors and tasks
	- Configuration is bundled with your process
	- Very easy to get started
	- Not fault tolerant no scalability hard to monitor
- Distributed:
	- Multiple workers run your connectors and tasks
	- Configuration is submitted using a REST API
	- Easy to scale and fault tolerant
	- Useful for production deployment of connectors

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240421094600531.webp](/img/user/assets/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240421094600531.webp)

Connect Cluster will do automatic rebalancing for Connector Tasks if a worker (typically a server) goes down

# References


# Flashcards