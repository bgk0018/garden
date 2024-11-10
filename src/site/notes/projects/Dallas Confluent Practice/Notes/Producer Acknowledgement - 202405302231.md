---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/producer-acknowledgement-202405302231/","tags":["♣️/kafka","📖"],"created":"2024-08-29T16:41:19.107-05:00","updated":"2024-11-10T13:46:05.807-06:00"}
---


# Producer Acknowledgement

[[projects/Dallas Confluent Practice/Notes/Producer - 202405302120\|Producers]] can choose to receive acknowledgement of data writes:

1. **acks=0 (Fire and Forget)**
   - Producer won't wait for acknowledgement
   - Highest throughput but possible data loss
   - No durability guarantees

2. **acks=1 (Leader Only)**
   - Producer waits for [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] acknowledgement
   - Limited data loss possible if leader fails before replication
   - Balance of throughput and durability

3. **acks=all**
   - Requires [[projects/Dallas Confluent Practice/Notes/Partition Leader - 202405302223\|Partition Leader]] + all [[projects/Dallas Confluent Practice/Notes/In-sync Replica - 202405302227\|In-sync Replicas]] acknowledgement
   - Strongest durability guarantee
   - Lowest throughput
   - Works with min.insync.replicas for additional guarantees

## Impact on Durability

The acks setting directly impacts [[projects/Dallas Confluent Practice/Notes/Topic Durability - 202406011116\|Topic Durability]]. When used with min.insync.replicas, it provides the strongest durability guarantees.

## References

## Flashcards

What are the three possible values for producer acks?:: acks=0 (no ack), acks=1 (leader only), acks=all (all replicas)

<!--SR:!2024-07-18,3,250-->

Which acks setting provides the strongest durability guarantee?:: acks=all, especially when combined with min.insync.replicas

<!--SR:!2024-07-19,4,250-->

With acks=all and min.insync.replicas=2, how many brokers can fail before producers can't write?:: 1 broker - we need at least 2 brokers available to meet the min.insync.replicas requirement

<!--SR:!2024-07-20,5,250-->
