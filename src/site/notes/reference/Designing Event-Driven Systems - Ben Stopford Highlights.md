---
{"dg-publish":true,"permalink":"/reference/designing-event-driven-systems-ben-stopford-highlights/","title":"Designing Event-Driven Systems","tags":["✂️"],"created":"2024-08-29T16:39:00.925-05:00","updated":"2024-11-10T13:55:05.638-06:00"}
---


# Designing Event-Driven Systems

![cover|150](https://images-na.ssl-images-amazon.com/images/S/compressed.photo.goodreads.com/books/1523335721i/39793332.jpg)

## Metadata

- Document Note: The book "Designing Event-Driven Systems" discusses the use of Kafka, an event streaming platform, for building event-driven systems. The book covers topics such as managing data evolution with schemas, maintaining strong ordering guarantees, and implementing streaming services with Kafka Streams and KSQL. It also explains the use of event sourcing and CQRS patterns to help systems scale and be less prone to corruption. The book emphasizes the importance of a shared source of truth and loose coupling in designing event-driven systems.
- URL: https://readwise.io/reader/document_raw_content/18412683

## Highlights

#📫

>[!QUOTE]  
>But the services model made
>interaction a first-class entity. Suddenly your users weren’t just customers or businesspeople; they were other applications, and they really cared that your service was reliable. So applications became platforms, and building platforms is hard. ([View Highlight](https://read.readwise.io/read/01hs6m2ry10m4w5hb2fwg97sk8)) #✂️
{ #ref-694072536}


---

>[!QUOTE]  
>Complex dependencies led to instability, versioning issues caused painful lockstep releases, and early on, it wasn’t clear that the new architecture was actually an improvement. ([View Highlight](https://read.readwise.io/read/01hs6m3fgk6363nv41fzf112wj)) #✂️
{ #ref-694072827}


---

>[!QUOTE]  
>[Enterprise service buses (ESBs), for example, have](https://www.thoughtworks.com/radar/tools/esb) [vocal](https://www.thoughtworks.com/radar/tools/esb) detractors and traditional messaging systems have a number of issues of their own. They are often used to move data around an organization, but the absence of any notion of history limits their value. So, even though recent events typically have more value than old ones, business operations still need historical data—whether it’s users wanting to query their account history, some service needing a list of customers, or analytics that need to be run for a management report. ([View Highlight](https://read.readwise.io/read/01hs6m97s7310jkgdfjdbd4hdp)) #✂️
{ #ref-694073506}


---

>[!QUOTE]  
>Replayable logs decouple services from one another, much like a messaging system does, but they also provide a central point of storage that is fault-tolerant and scalable—a shared source of truth that any application can fall back to. ([View Highlight](https://read.readwise.io/read/01hs6mac5spgr8pr2p72qxs90f)) #✂️
{ #ref-694073552}


---

>[!QUOTE]  
>[A shared source of truth turns out to be a surprisingly useful thing. Microservi‐ ces, for example, don’t share their databases with one another (referred to as the](http://bit.ly/2um1Q6W) [IntegrationDatabase](http://bit.ly/2um1Q6W) antipattern[). There is a good reason for this: databases have very rich APIs that are wonderfully useful on their own, but when widely shared they make it hard to work out if and how one application is going to affect oth‐ ers, be it data couplings, contention, or load. But the business facts that services do choose to share are the most important facts of all.](http://bit.ly/2DWuVFm) ([View Highlight](https://read.readwise.io/read/01hs6mbngz7d475byz5tv86qyr)) #✂️
{ #ref-694074338}


---

>[!QUOTE]  
>a replayable log provides a far more suitable place to hold this kind of data because (somewhat counterintuitively) you can’t query it! It is purely about storing data and pushing it to somewhere new. This idea of pure data movement is important, because data on the outside—the data services share—is the most tightly coupled of all, and the more services an ecosystem has, the more tightly coupled this data gets ([View Highlight](https://read.readwise.io/read/01hs6me5ayg0arvhnj9vjqxyve)) #✂️
{ #ref-694074533}


---

>[!QUOTE]  
>eplayable log–based approach has two primary benefits. First, it makes it easy to react to events that are happening now, with a toolset specifically designed for manipulating them. Second, it provides a central repository that can push whole datasets to wherever they may be needed. ([View Highlight](https://read.readwise.io/read/01hs6mg34zhyk4jdpsjx0zvgt6)) #✂️
{ #ref-694074635}


---

>[!QUOTE]  
>Making message-at-a-time network calls isn’t a particularly good idea when you’re handling a high-throughput event stream. For this reason stream processors write data locally (so writes and reads are fast) and back those writes
>[up to Kafka](https://readwise.io/reader/document_raw_content/18412683/#bookmark332) ([View Highlight](https://read.readwise.io/read/01hs6n2bjn4a1yphz6v1y2asnz)) #✂️
{ #ref-694076694}


---

>[!QUOTE]  
>A broker is a separate piece of infrastructure that broadcasts messages to any programs that are interested in them, as well as storing them for as long as is needed. So it’s perfect for streaming or fire-and-forget messaging. ([View Highlight](https://read.readwise.io/read/01hs6n4g4jd30f1mf6m3wf6r64)) #✂️
{ #ref-694076817}


---

>[!QUOTE]  
>[ESBs are criticized](https://www.thoughtworks.com/radar/tools/esb) [in some](https://www.thoughtworks.com/radar/tools/esb) circles. This criticism arises from the way the technology has been built up over the last 15 years, particularly where ESBs are controlled by central teams that dictate schemas, message flows, validation, and even transformation. In practice centralized approaches like this can constrain an organization, making it hard for individual applications and services to evolve at their own pace. ([View Highlight](https://read.readwise.io/read/01hs6n9195n2nqqjs2q5zcndz1)) #✂️
{ #ref-694077397}


---

>[!QUOTE]  
>So Kafka may look a little like an ESB, but as we’ll see throughout this book, it is very different. It provides a far higher level of throughput, availability, and storage, and there are hundreds of companies routing their core facts through a single Kafka cluster. Beyond that, streaming encourages services to retain control, particularly of their data, rather than providing orchestration from a single, central team or platform. ([View Highlight](https://read.readwise.io/read/01hs6namxj27kp3eyrs6gxjnxg)) #✂️
{ #ref-694078082}


---

>[!QUOTE]  
>A Kafka cluster is essentially a collection of files, filled with messages, spanning many different machines. Most of Kafka’s code involves tying these various individual logs together, routing messages from producers to consumers reliably, replicating for fault tolerance, and handling failure gracefully. ([View Highlight](https://read.readwise.io/read/01hs6nfa8hjs4ejzz598qf1z4h)) #✂️
{ #ref-694082023}


---

>[!QUOTE]  
>A Kafka cluster is a distributed system, spreading data over many machines both for fault tolerance and for linear scale-out. The system is designed to handle a range of use cases, from high-throughput streaming, where only the latest mes‐
>sages matter, to mission-critical use cases where messages and their relative ordering must be preserved with the same guarantees as you’d expect from a DBMS (database management system) or storage system. ([View Highlight](https://read.readwise.io/read/01hs6njszf9h24gqwkajxc2d35)) #✂️
{ #ref-694083990}


---

>[!QUOTE]  
>[At the heart of the Kafka messaging system sits a partitioned, replayable log. The](https://en.wikipedia.org/wiki/Transaction_log) [log-structured](https://en.wikipedia.org/wiki/Transaction_log) approach [is itself a simple idea: a collection of messages, appended sequentially to a file. When a service wants to read messages from Kafka, it “seeks” to the position of the last message it read, then scans sequentially, reading messages in order while periodically recording its new position in the log](https://readwise.io/reader/document_raw_content/18412683/#bookmark43) ([View Highlight](https://read.readwise.io/read/01hs6nmmkx7sgktg4fppr5s3da)) #✂️
{ #ref-694084321}


---

>[!QUOTE]  
>In fact, when you read messages from Kafka, the server doesn’t even import them into the JVM (Java virtual machine). Data is copied directly from the disk buffer to the network
>buffer (zero copy)—an opportunity afforded by the simplicity of both the contract and the underlying data structure ([View Highlight](https://read.readwise.io/read/01hs6nnp9x1ve8cew9bnyqh59w)) #✂️
{ #ref-694084513}


---

>[!QUOTE]  
>[There are a few implications to this log-structured approach. If a service has some form of outage and doesn’t read messages for a long time, the backlog won’t cause the infrastructure to slow significantly (a common problem with tra‐ ditional brokers, which have a tendency to slow down as they get full). Being log- structured also makes Kafka well suited to performing the role of an event store, for those who like to apply](https://martinfowler.com/eaaDev/EventSourcing.html) [Event](https://martinfowler.com/eaaDev/EventSourcing.html) Sourcing [within their services.](https://readwise.io/reader/document_raw_content/18412683/#bookmark132) ([View Highlight](https://read.readwise.io/read/01hs6nqf1924j58ckqgfwd9t89)) #✂️
{ #ref-694084721}


---

>[!QUOTE]  
>Partitions are a fundamental concept for most distributed data systems. A partition is just a bucket that data is put into, much like buckets used to group data in a hash table. In Kafka’s terminology each log is a replica of a partition held on a different machine. ([View Highlight](https://read.readwise.io/read/01hs6nr16x6dfp210pks4c1qq6)) #✂️
{ #ref-694084761}


---

>[!QUOTE]  
>There are a couple of things that need to be considered to ensure strong ordering guarantees. The first is that messages that require relative ordering need to be sent to the same partition. (Kafka provides ordering guarantees only within a partition.) This is managed for you: you supply the same key for all messages that require a relative order. So a stream of customer information updates would use the CustomerId [as their partitioning key. All messages for the same customer would then be routed to the same partition, and hence be strongly ordered](https://readwise.io/reader/document_raw_content/18412683/#bookmark48) ([View Highlight](https://read.readwise.io/read/01hs6p150d36tby3d9qdraphwf)) #✂️
{ #ref-694085416}


---

>[!QUOTE]  
>Sometimes key-based ordering isn’t enough, and global ordering is required. This often comes up when you’re migrating from legacy messaging systems where global ordering was an assumption of the original system’s design. To maintain global ordering, use a single partition topic. Throughput will be limited to that of a single machine, but this is typically sufficient for use cases of this type. ([View Highlight](https://read.readwise.io/read/01hs6p2y3sq8hmjn506erw34hy)) #✂️
{ #ref-694085583}


---

>[!QUOTE]  
>[Compacted topics work a bit like simple](http://www.benstopford.com/2015/02/14/log-structured-merge-trees/) [log-structure merge-trees (LSM](http://www.benstopford.com/2015/02/14/log-structured-merge-trees/) trees)[. The topic is scanned periodically, and old messages are removed if they have been superseded (based on their key); see](https://readwise.io/reader/document_raw_content/18412683/#bookmark53) [Figure](https://readwise.io/reader/document_raw_content/18412683/#bookmark53) 4-5. It’s worth noting that this is an asynchronous process, so a compacted topic may contain some superseded messages, which are waiting to be compacted away. ([View Highlight](https://read.readwise.io/read/01hs6pacqkrzvw833ksf9h0j4a)) #✂️
{ #ref-694086637}


---
