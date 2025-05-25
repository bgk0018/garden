---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/producer-acknowledgement-202405302231/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:29.274-05:00","updated":"2025-02-02T18:55:31.445-06:00"}
---


# Producer Acknowledgement

[[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] can choose to receive acknowledgement of data writes through three different levels:

1. **acks=0 (Fire and Forget)**
   - Producer won't wait for acknowledgement
   - No acknowledgment required from broker
   - Highest throughput but possible data loss
   - Lowest latency but no durability guarantees
   - Message loss possible if broker fails

2. **acks=1 (Leader Only)**
   - Producer waits for [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] acknowledgement
   - Leader acknowledges without waiting for followers
   - Limited data loss possible if leader fails before replication
   - Balance of throughput and durability
   - Better durability than acks=0

3. **acks=all (All In-Sync Replicas)**
   - Requires [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] + all [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replicas]] acknowledgement
   - Strongest durability guarantee
   - Highest latency
   - Works with min.insync.replicas for additional guarantees

## Impact on Durability

The acks setting directly impacts [[projects/Dallas Confluent Practice/Notes/Topic Durability - 202406011116\|Topic Durability]]. When used with min.insync.replicas, it provides the strongest durability guarantees. For example, with acks=all and min.insync.replicas=2, we need at least 2 brokers available to accept writes.

## References

## Flashcards

What are the three possible values for producer acks?:: acks=0 (no ack), acks=1 (leader only), acks=all (all replicas)
<!--SR:!2025-02-05,12,288-->

<!--SR:!2024-07-18,3,250-->

Which acks setting provides the strongest durability guarantee?:: acks=all, especially when combined with min.insync.replicas
<!--SR:!2025-01-28,4,272-->

<!--SR:!2024-07-19,4,250-->

What is the trade-off when using acks=all?:: Highest durability but also highest latency since we wait for all replicas to acknowledge
<!--SR:!2025-01-25,2,230-->

<!--SR:!2024-07-20,5,250-->

With acks=all and min.insync.replicas=2, how many brokers can fail before producers can't write?:: 1 broker - we need at least 2 brokers available to meet the min.insync.replicas requirement
<!--SR:!2025-02-02,9,250-->

<!--SR:!2024-07-20,5,250--> 
