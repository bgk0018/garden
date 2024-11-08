---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/choosing-partition-count-and-replication-factor-202403301711/","tags":["📖"],"created":"2024-08-29T16:38:59.662-05:00","updated":"2024-11-08T09:43:56.590-06:00"}
---

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
	- 

## References


