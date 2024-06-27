---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-security-202406021530/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.477+01:00","updated":"2024-06-27T22:16:56.601+01:00"}
---

# Kafka Security

Need to setup
- Authentication
- Authorization
- Encryption

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173015032.webp](/img/user/assets/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173015032.webp)


![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173051955.webp](/img/user/assets/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173051955.webp)

# References


# Flashcards

If you enable an SSL endpoint in Kafka, what feature of Kafka will be lost?:: Zero copy. With SSL, messages will need to be encrypted and decrypted, by being first loaded into the JVM, so you lose the zero copy optimization.
<!--SR:!2024-06-16,4,270-->

What is not a valid authentication mechanism in Kafka?:: SAML
<!--SR:!2024-07-05,8,250-->

What is the protocol used by Kafka clients to securely connect to the Confluent REST Proxy?:: HTTPS (SSL/TLS) TLS - but it is still called SSL.
<!--SR:!2024-06-16,4,270-->