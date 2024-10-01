---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-in-the-enterprise-for-admins-202406021529/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:38:54.887-05:00","updated":"2024-06-03T08:32:00.000-05:00"}
---

# Kafka in the Enterprise for Admins

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330172205211.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330172205211.webp)

## Monitoring and Operations

- Kafka exposes metrics through JMX
- Common places to host
	- ELK
	- Datadog
	- New Relic etc

Important metrics:
- Under replication partitions (potentially high load on the cluster)
- Request handlers: use of threads for IO/network overall utizilation of an apache kafka broker
- Request timing: how long it takes to reply to request, lower is better as latency will be improved

Operations team must be able to:
- Rolling restart of brokers
- Update configuration
- Rebalance partitions
- Increase replication factor
- Add, replace, remove broker
- Upgrade cluster


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/kafka-security-202406021530/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




# Kafka Security

Need to setup
- Authentication
- Authorization
- Encryption

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173015032.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173015032.webp)


![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173051955.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173051955.webp)

# References


# Flashcards

If you enable an SSL endpoint in Kafka, what feature of Kafka will be lost?:: Zero copy. With SSL, messages will need to be encrypted and decrypted, by being first loaded into the JVM, so you lose the zero copy optimization.
<!--SR:!2024-07-25,16,290-->

What is not a valid authentication mechanism in Kafka?:: SAML
<!--SR:!2024-08-05,27,270-->

What is the protocol used by Kafka clients to securely connect to the Confluent REST Proxy?:: HTTPS (SSL/TLS) TLS - but it is still called SSL.
<!--SR:!2024-07-23,14,290-->

</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/kafka-multi-cluster-and-mirror-maker-202406021530/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




# Kafka Multi Cluster and MirrorMaker

Kafka can only operate well in a single region, so we need to leverage replication

Mirror Maker 2 - Open source Kafka connector that ships with Kafka

>[!WARNING]  
>Replicating doesn't preserve offsets, just data. Data at an offset in one cluster is not the same as the data at same offset in another cluster.

Replication: Active/Active, or Active/Passive (readonly)

# References


# Flashcards

</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/reference/event-driven-architecture-is-an-integration-model-built-around-the-publication-capture-processing-and-storage-of-application-or-service-events-ibm-com-highlights/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




# Event-Driven Architecture Is an Integration Model Built Around the Publication, Capture, Processing, and Storage of Application or Service Events

![cover|150](https://www.ibm.com/content/dam/connectedassets-adobe-cms/worldwide-content/other/ul/g/70/65/7065b36b-da8d-43c3-be640c5b9d5ff204.jpg/_jcr_content/renditions/cq5dam.medium.1584.1584.jpeg)
## Metadata
- URL: https://www.ibm.com/topics/event-driven-architecture?utm_medium=OSocial&utm_source=Youtube&utm_content=000023UA&utm_term=10010608&utm_id=YTDescription-101-What-is-EDA-LH-Event-Driven-Architecture-Guide

## Highlights
#📫
>[!QUOTE]  
>**Event messaging or publish/subscribe**
>In the event messaging or publish/subscribe model, event consumers subscribe to a class or classes of messages published by event producers. When an event producer publishes an event, the message is sent directly to all subscribers who want to consume it.
>Typically a *[message broker](https://www.ibm.com/topics/message-brokers)* handles the transmission of event messages between publishers and subscribers. The broker receives each event message, translates it if necessary, maintains its order relative to other messages, makes them available to subscribers for consumption, and then deletes them once they are consumed (so that they cannot be consumed again). ([View Highlight](https://read.readwise.io/read/01hrtcsr7eq5ykd3v34cpdxznv)) #✂️  ^ref-691986267

---
>[!QUOTE]  
>**Event streaming**
>In the event streaming model, event producers publish *streams* of events to a broker. Event consumers subscribe to the streams, but instead of receiving and consuming every event as it is published, consumers can step into each stream at any point and consume only the events they want to consume. The key difference here is that the events are retained by the broker even after the consumers have received them. ([View Highlight](https://read.readwise.io/read/01hrtcttnce2wyp3bmkzh1q5kq)) #✂️  ^ref-691986302

---
>[!QUOTE]  
>A data streaming platform, such as [Apache Kafka](https://www.ibm.com/topics/apache-kafka), manages the logging and transmission of tremendous volumes of events at very high throughput (literally trillions of event records per day, in real-time, without performance lag). A streaming platform offers certain characteristics a message broker does not:
>• **Event persistence:** Because consumers may consume events at any time after they are published, event streaming records are *persistent*—they are maintained for a configurable amount of time, anywhere from fractions of a second to forever. This enables event stream applications to process historical data, as well as real-time data. 
>• **Complex event processing:** Like event messaging, event streaming can be used for simple event processing, in which each published event triggers transmission and processing by one or more specific consumers. But, it can also be used for complex event processing, in which event consumers process entire series of events and perform actions based on the result. ([View Highlight](https://read.readwise.io/read/01hrtcv4y6eam8p7kcwe8ndv6a)) #✂️  ^ref-691986314

---
>[!QUOTE]  
>Not surprisingly, event-driven architecture is widely considered best practice for microservices implementations. Microservices *can* communicate with each other using [REST APIs](https://www.ibm.com/topics/rest-apis). But REST, a request/response integration model, undermines many of the benefits of the loosely coupled microservices architecture by forcing a synchronous, tightly coupled integration between the microservices. ([View Highlight](https://read.readwise.io/read/01hrtcy29h09kw7vv98twp4znz)) #✂️  ^ref-691986441

---


</div></div>


# References


# Flashcards