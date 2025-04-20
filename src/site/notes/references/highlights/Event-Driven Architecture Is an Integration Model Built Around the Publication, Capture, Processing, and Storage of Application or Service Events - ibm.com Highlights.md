---
{"dg-publish":true,"permalink":"/references/highlights/event-driven-architecture-is-an-integration-model-built-around-the-publication-capture-processing-and-storage-of-application-or-service-events-ibm-com-highlights/","title":"Event-Driven Architecture Is an Integration Model Built Around the Publication, Capture, Processing, and Storage of Application or Service Events","tags":["✂️"],"created":"2025-02-24T16:08:57.734-06:00","updated":"2025-03-11T13:29:31.844-05:00"}
---


# Event-Driven Architecture Is an Integration Model Built Around the Publication, Capture, Processing, and Storage of Application or Service Events

![cover|150](https://www.ibm.com/content/dam/connectedassets-adobe-cms/worldwide-content/other/ul/g/70/65/7065b36b-da8d-43c3-be640c5b9d5ff204.jpg/_jcr_content/renditions/cq5dam.medium.1584.1584.jpeg)

## Metadata

- URL: https://www.ibm.com/topics/event-driven-architecture?utm_medium=OSocial&utm_source=Youtube&utm_content=000023UA&utm_term=10010608&utm_id=YTDescription-101-What-is-EDA-LH-Event-Driven-Architecture-Guide

## Highlights

>[!QUOTE]  
>**Event messaging or publish/subscribe**
>In the event messaging or publish/subscribe model, event consumers subscribe to a class or classes of messages published by event producers. When an event producer publishes an event, the message is sent directly to all subscribers who want to consume it.
>Typically a *[message broker](https://www.ibm.com/topics/message-brokers)* handles the transmission of event messages between publishers and subscribers. The broker receives each event message, translates it if necessary, maintains its order relative to other messages, makes them available to subscribers for consumption, and then deletes them once they are consumed (so that they cannot be consumed again). ([View Highlight](https://read.readwise.io/read/01hrtcsr7eq5ykd3v34cpdxznv)) #✂️
{ #ref-691986267}


---

>[!QUOTE]  
>**Event streaming**
>In the event streaming model, event producers publish *streams* of events to a broker. Event consumers subscribe to the streams, but instead of receiving and consuming every event as it is published, consumers can step into each stream at any point and consume only the events they want to consume. The key difference here is that the events are retained by the broker even after the consumers have received them. ([View Highlight](https://read.readwise.io/read/01hrtcttnce2wyp3bmkzh1q5kq)) #✂️
{ #ref-691986302}


---

>[!QUOTE]  
>A data streaming platform, such as [Apache Kafka](https://www.ibm.com/topics/apache-kafka), manages the logging and transmission of tremendous volumes of events at very high throughput (literally trillions of event records per day, in real-time, without performance lag). A streaming platform offers certain characteristics a message broker does not:
>• **Event persistence:** Because consumers may consume events at any time after they are published, event streaming records are *persistent*—they are maintained for a configurable amount of time, anywhere from fractions of a second to forever. This enables event stream applications to process historical data, as well as real-time data. 
>• **Complex event processing:** Like event messaging, event streaming can be used for simple event processing, in which each published event triggers transmission and processing by one or more specific consumers. But, it can also be used for complex event processing, in which event consumers process entire series of events and perform actions based on the result. ([View Highlight](https://read.readwise.io/read/01hrtcv4y6eam8p7kcwe8ndv6a)) #✂️
{ #ref-691986314}


---

>[!QUOTE]  
>Not surprisingly, event-driven architecture is widely considered best practice for microservices implementations. Microservices *can* communicate with each other using [REST APIs](https://www.ibm.com/topics/rest-apis). But REST, a request/response integration model, undermines many of the benefits of the loosely coupled microservices architecture by forcing a synchronous, tightly coupled integration between the microservices. ([View Highlight](https://read.readwise.io/read/01hrtcy29h09kw7vv98twp4znz)) #✂️
{ #ref-691986441}


---
