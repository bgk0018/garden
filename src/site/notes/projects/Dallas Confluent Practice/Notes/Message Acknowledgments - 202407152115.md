---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/message-acknowledgments-202407152115/","tags":["♣️/kafka","📖"],"created":"2024-11-08T08:58:30.539-06:00","updated":"2024-11-10T13:44:28.000-06:00"}
---


# Message Acknowledgments

Message acknowledgments (acks) determine how producers receive confirmation that their messages were received by Kafka brokers.

## Acknowledgment Levels

1. **acks=0 (Fire and Forget)**
   - No acknowledgment required
   - Lowest latency but no durability guarantees
   - Message loss possible if broker fails

2. **acks=1 (Leader Only)**
   - Leader acknowledges without waiting for followers
   - Better durability than acks=0
   - Possible message loss if leader fails before replication

3. **acks=all (All In-Sync Replicas)**
   - Requires acknowledgment from all in-sync replicas
   - Highest durability guarantee
   - Highest latency
   - Works with min.insync.replicas for stronger guarantees

## Impact on Durability

The acks setting directly impacts [[projects/Dallas Confluent Practice/Notes/Topic Durability - 202406011116\|Topic Durability]]. When used with min.insync.replicas, it provides the strongest durability guarantees.

## References

## Flashcards

What are the three possible values for producer acks?:: acks=0 (no ack), acks=1 (leader only), acks=all (all replicas)

<!--SR:!2024-07-18,3,250-->

Which acks setting provides the strongest durability guarantee?:: acks=all, especially when combined with min.insync.replicas

<!--SR:!2024-07-19,4,250-->

What is the trade-off when using acks=all?:: Highest durability but also highest latency since we wait for all replicas to acknowledge

<!--SR:!2024-07-20,5,250--> 
