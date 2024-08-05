---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/java-producer-client-202406021637/","tags":["📖","♣️/kafka"],"created":"2024-06-03T08:22:24.909-05:00","updated":"2024-07-15T22:42:50.909-05:00"}
---

# Java Producer Client

Both of these are retriable errors, others non-retriable errors. See the full list of errors and their "retriable" status here: [https://kafka.apache.org/protocol#protocol_error_codes](https://kafka.apache.org/protocol#protocol_error_codes)

## References


## Flashcards

Which of the following errors are retriable from a producer perspective? (select two)
- INVALID_REQUIRED_ACKS
- TOPIC_AUTHORIZATION_FAILED
- MESSAGE_TOO_LARGE
- NOT_LEADER_FOR_PARTITION
- NOT_ENOUGH_REPLICAS
?
- NOT_LEADER_FOR_PARTITION
- NOT_ENOUGH_REPLICAS
<!--SR:!2024-08-31,65,310-->

What is returned by a producer.send() call in the Java API?:: `Future<RecordMetadata>` object
<!--SR:!2024-07-20,23,252-->

When is the onCompletion() method called?
```java
private class ProducerCallback implements Callback {
         @Override
        public void onCompletion(RecordMetadata recordMetadata, Exception e) {
         if (e != null) {
             e.printStackTrace();
            }
        } 
}

    ProducerRecord<String, String> record =
            new ProducerRecord<>("topic1", "key1", "value1");
    producer.send(record, new ProducerCallback()); 
```
?
When the broker response is received, Callback is invoked when a broker response is received.
<!--SR:!2024-09-03,68,312-->

Which of the following is true regarding thread safety in the Java Kafka Clients?
- One Consumer needs to run in one thread
- One Producer needs to be run in one thread
- One Producer can be safely used in multiple threads
- One Consumer can be safely used in multiple threads
?
- One Consumer needs to run in one thread
- One Producer can be safely used in multiple threads
KafkaConsumer is not thread-safe, KafkaProducer is thread safe.
<!--SR:!2024-07-26,17,294-->

What's is true about Kafka brokers and clients from version 0.10.2 onwards?:: A newer client can talk to a newer broker, and an older client can talk to a newer broker. Kafka's new bidirectional client compatibility introduced in 0.10.2 allows this.
<!--SR:!2024-07-20,8,254-->


What exceptions may be caught by the following producer? (select two)
```
ProducerRecord<String, String> record =
            new ProducerRecord<>("topic1", "key1", "value1");
    try {
      producer.send(record);
    } catch (Exception e) {
            e.printStackTrace();
}
```
?
- SerializationException
- BufferExhaustedException
These are the client side exceptions that may be encountered before message is sent to the broker, and before a future is returned by the .send() method.
<!--SR:!2024-08-30,49,294-->

The BufferedExhaustedException in the context of the Java Producer Client library for Apache Kafka is an exception that can be thrown when the producer is unable to send messages due to the internal buffer being full. This typically happens when the producer is producing messages faster than Kafka brokers can handle them, or when there are network or broker issues causing a delay in the acknowledgement of messages.
<!--SR:!2024-06-13,1,234-->

If you want to modify the behavior of your producer without modifying the code, you should use:: `ProducerInterceptor`
<!--SR:!2024-07-19,4,286-->

`ProducerInterceptor` has what 2 methods?
?
- `ProducerRecord<K,V> onSend(ProducerRecord<K, V> record)` Called before the produced record is sent to kafka, can modify the Records being produced
- `void onAcknowledgement(RecordMetadata metadata, Exception exception)` This methold will be called if and when Kafka responds with an acknowledge for a send. You cannot modify the response