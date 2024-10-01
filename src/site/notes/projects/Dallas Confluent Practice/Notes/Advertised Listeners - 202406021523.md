---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/advertised-listeners-202406021523/","tags":["📖","♣️/kafka"],"created":"2024-08-29T16:38:54.677-05:00","updated":"2024-06-02T15:28:37.000-05:00"}
---

# Advertised Listeners

- The most important setting of kafka
- Advertised listener is basically the preferred connection point of a Kafka Broker, if you request the public IP address from a Kafka Client to a Broker, and the Advertised Listener IP is set to a private network IP address, if the client is on the private network then everything will work but if it's not it will fail to connect
- If you're using IPs, you have the potential of having the IP change so you probably want to use a DNS hostname


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/consumer-incremental-cooperative-rebalance-202403301631/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Consumer Incremental Cooperative Rebalance

</div>



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

</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/consumer-group-auto-offset-commit-behavior-202403301632/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Consumer Group Auto Offset Commit Behavior

</div>



# Consumer Group Auto Offset Commit Behavior



## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/producer-retries-202403301634/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Producer Retries

</div>



# Producer Retries



## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/idempotent-producer-202403301634/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Idempotent Producer

</div>



# Idempotent Producer



## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/safe-producers-202403301634/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




# Safe Producers



## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/producer-batch-settings-202403301636/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Producer Batch Settings

</div>



# Producer Batch Settings

linger.ms and batch.size

## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/producer-partitioners-202403301636/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Producer Partitioners

</div>



# Producer Partitioners

Default Partition and Sticky Partitioner


## References




</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/kafka-extended-ap-is-for-developers-202406021528/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




# Kafka Extended APIs for Developers

[[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] and [[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] are considered low level, and since their introduction other higher level APIs have been created, specifically:
- [[projects/Dallas Confluent Practice/Notes/Kafka Connect - 202403301639\|Kafka Connect]]
- [[projects/Dallas Confluent Practice/Notes/Kafka Streams - 202403301640\|Kafka Streams]]
- [[projects/Dallas Confluent Practice/Notes/Schema Registry - 202403301641\|Schema Registry]]

- Kafka Brokers do NOT verify the messages they receive
- Kafka takes bytes as input with out loading them into memory (zero copy)
- Schema Registry then is a separate component
	- Producers and Consumers need to be able to talk to it
	- The Schema Registry must be able to reject bad data before sent to Kafka
	- Supports Avro, Protobuf and JSON

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170029132.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170029132.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170119062.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170119062.webp)

Gotchas:
- Needs to be highly available
- Schema formats have a learning curve (Avro, etc.)

You can also evolve schemas over time. The same problems you experience in changing any contract apply. Additions are backwards compatible, modifications or deletions are not.

Schema changes are versioned (v1, v2, etc.)

You can also assign default values for new properties as the schemas evolve.


![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330170923135.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330170923135.webp)

- Known data source use kafka connect source or sink depending on data flow
- Use Producer to collect directly from the source
- Consumer for producing ephemeral messages
- Kafka Streams for ETL back into Kafka
- KSQL for queries on Kafka data

# References


# Flashcards

</div></div>


# References


# Flashcards