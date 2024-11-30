---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/real-world-insights-and-case-studies-202406021533/","tags":["♣️/kafka","📖"],"created":"2024-06-01T21:19:41.212-05:00","updated":"2024-11-10T13:47:03.000-06:00"}
---


# Real World Insights and Case Studies


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/projects/dallas-confluent-practice/notes/choosing-partition-count-and-replication-factor-202403301711/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Choosing Partition Count and Replication Factor

</div>




# Choosing Partition Count and Replication Factor

- These are the two most important parameters when creating a topic
- They impact performance and durability of the system
- It's best to get these right the first time

>[!WARNING]
>- If the partition count increases, you will break your keys ordering guarantee
>- If the replication factor increases, you put more pressure on your cluster, which can have a performance decrease

How to choose?

- Partitions per topic
	- Small Cluster (<6 Brokers): 3 x # Brokers
	- Big Cluster (>12 Brokers): 2 x # Brokers
	- Adjust for number of consumers you need to run in parallel at peak throughput
	- Adjust for producer throughput (increase if super-high throughput or projected increase in the next 2 years)
- TEST IT!
- Replication Factor
	- Should be at least 2, usually 3, maximum 4
	- Set it to 3, if performance is an issue, get a better broker instead of lowering RF
- Cluster Guidelines
	- Total number of partitions in the cluster: 200k as of November 2018 which is Zookeeper Scaling limit
		- Recommend a maximum of 4000 partitions per broker (soft limit)

## References


</div></div>


Topic naming conventions

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330172118192.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330172118192.webp)

# References

# Flashcards
