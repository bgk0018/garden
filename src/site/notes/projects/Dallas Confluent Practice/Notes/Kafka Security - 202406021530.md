---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/kafka-security-202406021530/","tags":["♣️/kafka","📖"],"created":"2024-06-01T21:18:16.380-05:00","updated":"2024-11-10T13:42:22.000-06:00"}
---


# Kafka Security

Need to setup

- Authentication
- Authorization
- Encryption

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173015032.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173015032.webp)

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240330173051955.webp](/img/user/projects/Dallas%20Confluent%20Practice/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240330173051955.webp)

# References

# Flashcards

If you enable an SSL endpoint in Kafka, what feature of Kafka will be lost?:: Zero copy. With SSL, messages will need to be encrypted and decrypted, by being first loaded into the JVM, so you lose the zero copy optimization.

<!--SR:!2024-07-25,16,290-->

What is not a valid authentication mechanism in Kafka?:: SAML

<!--SR:!2024-08-05,27,270-->

What is the protocol used by Kafka clients to securely connect to the Confluent REST Proxy?:: HTTPS (SSL/TLS) TLS - but it is still called SSL.

<!--SR:!2024-07-23,14,290-->
