---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/confluent-rest-proxy-202406021526/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:20.140-06:00","updated":"2025-01-24T21:28:39.248-06:00"}
---


# Confluent REST Proxy

[Documentation here](https://docs.confluent.io/platform/current/kafka-rest/api.html)

## V1 Vs V2 APIs

- Just use V2 API
- `Content-Type` header should be specified as `application/vnd.kafka.[embedded_format].[api_version]+[serialization_format]` 
	- embeddedformat: json, binary or avro
	- api_version is always v2
	- serialization_format is always json

Example: `Content-Type: application/vnd.kafka.avro.v2+json`

Port number is 8082 typically

## Topic Operations

- Get a list of topics
- Get a specific topic

Can't create/configure topics with the REST Proxy

## Producing in Binary with the Kafka REST Proxy

- Binary data has to be base64 encoded before sending it to Kafka

# References

# Flashcards

If I want to send binary data through the REST proxy to topic "test_binary", it needs to be base64 encoded. A consumer connecting directly into the Kafka topic "test_binary" will receive:: binary data
<!--SR:!2025-01-27,3,250-->

<!--SR:!2024-09-02,67,310-->

What data format isn't natively available with the Confluent REST Proxy?:: Protobuf
<!--SR:!2025-01-26,2,230-->

<!--SR:!2024-08-30,64,312-->

If I want to send binary data through the REST proxy, it needs to be base64 encoded. Which component needs to encode the binary data into base 64?:: The Producer. The REST Proxy requires to receive data over REST that is already base64 encoded, hence it is the responsibility of the producer
<!--SR:!2025-01-26,3,250-->

<!--SR:!2024-09-22,69,319-->
