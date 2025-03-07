---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/delivery-semantics-202405302156/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:21.202-06:00","updated":"2025-01-26T11:50:20.698-06:00"}
---


# Delivery Semantics

There are different ways [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] will handle delivery.


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

<div class="markdown-embed-title">

# At Least Once Delivery

</div>




This is a [[projects/Dallas Confluent Practice/Notes/Delivery Semantics - 202405302156\|Delivery Semantics]] in which:

- [[projects/Dallas Confluent Practice/Notes/Offset - 202405282304\|Offsets]] are committed after the [[projects/Dallas Confluent Practice/Notes/Messages - 202406042227\|Message]] is processed
- If the processing goes wrong, the [[projects/Dallas Confluent Practice/Notes/Messages - 202406042227\|Message]] will be read again
- This can result in duplicate processing of messages and the [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]] needs to be able to reprocess those messages in an [[projects/Dallas Confluent Practice/Notes/Idempotent - 202303012108\|Idempotent]] manner


</div></div>



<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

<div class="markdown-embed-title">

# At Most Once Delivery

</div>




This is a [[projects/Dallas Confluent Practice/Notes/Delivery Semantics - 202405302156\|Delivery Semantics]] in which:

- [[projects/Dallas Confluent Practice/Notes/Offset - 202405282304\|Offsets]] are committed as soon as messages are received.
- If the processing goes wrong, some messages will be lost and not read again


</div></div>



<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

<div class="markdown-embed-title">

# Exactly One Delivery

</div>




This is a [[projects/Dallas Confluent Practice/Notes/Delivery Semantics - 202405302156\|Delivery Semantics]] in which:

- For Kafka to Kafka workflows: Use the Transactional API
- Kafka to External System us an [[projects/Dallas Confluent Practice/Notes/Idempotent - 202303012108\|Idempotent]] [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumer]]


</div></div>


## References

## Flashcards

What are the 3 different ways [[projects/Dallas Confluent Practice/Notes/Consumer - 202405302133\|Consumers]] handle message delivery?:: Atleast once, at most once, exactly once
<!--SR:!2025-02-07,12,270-->

<!--SR:!2024-09-04,69,310-->

```
while (true) {
        ConsumerRecords<String, String> records = consumer.poll(100);
         try {
          consumer.commitSync();
        } catch (CommitFailedException e) {
            log.error("commit failed", e)
        }
        for (ConsumerRecord<String, String> record : records)
        {
            System.out.printf("topic = %s, partition = %s, offset =
              %d, customer = %s, country = %s
",
                 record.topic(), record.partition(),
                 record.offset(), record.key(), record.value());
        }
}
```

What kind of delivery guarantee this consumer offers?

?

At-most-once. Here offset is committed before processing the message. If consumer crashes before processing the message, message will be lost when it comes back up.

<!--SR:!2024-08-26,60,314-->
