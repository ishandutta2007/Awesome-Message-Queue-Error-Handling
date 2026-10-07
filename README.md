# Awesome-Message-Queue-Error-Handling

## Top Message Queue Error Handling Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Dead Letter Queues, Retry Patterns & Self-Hosted Error Recovery*  

**Last updated: October 2026**



This repository tracks notable **commercial and open-source message queue platforms** that provide robust error handling — dead letter queues (DLQ), retry with backoff, poison message detection, and failure recovery — to prevent message loss and ensure reliable event-driven systems.



**Examples** include AWS SQS Dead Letter Queue, RabbitMQ, Apache Kafka, Azure Service Bus, Google Cloud Pub/Sub, IBM MQ, Celery, BullMQ, ActiveMQ, and Redpanda (the category leaders).



**Open-source emphasis**: Message queue error handling is a strong open-source domain. **RabbitMQ** provides dead letter exchanges with TTL and max retry policies. **Apache Kafka** supports DLQ patterns via Kafka Connect and consumer offset management. **BullMQ** delivers Redis-based retry with exponential backoff. **Celery** handles task retries with dead letter queues. **NATS JetStream** provides message redelivery and dead letter. **Apache Pulsar** offers negative acknowledgment and DLQ. **Redis Streams** supports consumer groups with pending message recovery. **MassTransit** and **NServiceBus** provide .NET error handling patterns. This section is heavily expanded.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[AWS SQS Dead Letter Queue](https://aws.amazon.com/sqs/faqs/)**

  **AWS's managed message queue with DLQ support** — configure maxReceiveCount and DLQ target . **Standard and FIFO queues with automatic redrive** . **Best for AWS-native message queuing** .



- **[AWS EventBridge](https://aws.amazon.com/eventbridge/)**

  **AWS's event bus with DLQ and retry policies** — configurable retry attempts and dead letter queues for failed deliveries . **Best for AWS-native event routing** .



- **[Azure Service Bus](https://azure.microsoft.com/en-us/products/service-bus/)**

  **Microsoft's message broker with DLQ** — automatic dead-lettering for expired, max-delivery, and filtering failures . **Best for Azure-native messaging** .



- **[Google Cloud Pub/Sub](https://cloud.google.com/pubsub)**

  **Google's messaging service with dead letter topics** — configure max delivery attempts and DLQ topic . **Best for GCP-native messaging** .



- **[IBM MQ](https://www.ibm.com/products/mq)**

  **Enterprise message queue with backout queues** — retry handling and poison message management . **Best for enterprise messaging** .



- **[Amazon MQ](https://aws.amazon.com/amazon-mq/)**

  **Managed ActiveMQ and RabbitMQ** — includes broker-level DLQ and retry configuration . **Best for managed message brokers** .



## Open-Source GitHub Projects



### Message Brokers with DLQ Support



- **[RabbitMQ](https://github.com/rabbitmq/rabbitmq-server)**

  **The most widely deployed open-source message broker**, MPL-2.0 licensed with **12,000+ GitHub stars** . **Dead letter exchanges (DLX)** — messages that are rejected, expire, or exceed queue length can be routed to a DLX . **TTL (Time-To-Live) per message and per queue** — expired messages can be dead-lettered . **Max retry via consumer nack or reject** — messages can be routed to DLQ after N attempts . **Best for reliable message queuing with DLQ** .



- **[Apache Kafka](https://github.com/apache/kafka)**

  **The de facto standard for event streaming**, Apache-2.0 licensed with **28,000+ GitHub stars** . **DLQ patterns via Kafka Connect** — sink connector handles failed records to DLQ . **Consumer offset management** — commit offsets after successful processing; failed messages remain for retry . **Kafka Streams** supports custom error handling with `ProductionExceptionHandler` and `DeserializationExceptionHandler` . **Best for high-throughput event streaming with DLQ patterns** .



- **[Redpanda](https://github.com/redpanda-data/redpanda)**

  **Kafka-compatible streaming platform in C++**, BSL licensed (free for most uses) . **No Zookeeper, no JVM** — simpler operations . **Kafka-compatible error handling** — supports all Kafka DLQ patterns . **Best for high-performance streaming with error handling** .



- **[Apache Pulsar](https://github.com/apache/pulsar)**

  **Distributed messaging and streaming platform**, Apache-2.0 licensed with **14,000+ GitHub stars** . **Negative acknowledgment (nack)** — consumers can nack messages for redelivery . **Dead letter topic (DLT)** — automatically routes failed messages after max redelivery attempts . **Retry letter topic** — configurable retry with backoff . **Best for multi-tenant messaging with built-in DLQ** .



- **[NATS JetStream](https://github.com/nats-io/nats-server)**

  **Cloud-native messaging system**, Apache-2.0 licensed . **Message redelivery and dead letter** — configurable max deliveries and DLQ subject . **Best for lightweight messaging with DLQ** .



- **[RabbitMQ Delayed Message Plugin](https://github.com/rabbitmq/rabbitmq-delayed-message-exchange)**

  **Delayed message exchange for RabbitMQ**, MPL-2.0 licensed . **Retry with delay and DLQ** — schedule failed messages for later retry . **Best for retry with backoff** .



### Task Queues with Retry & DLQ



- **[Celery](https://github.com/celery/celery)**

  **Distributed task queue for Python**, BSD-3-Clause licensed with **25,000+ GitHub stars** . **Task retries with exponential backoff** — `retry()` with `max_retries` and `countdown` . **Dead letter queue** via `task_reject_on_worker_lost` and custom error handlers . **Best for Python task queues** .



- **[BullMQ](https://github.com/taskforcesh/bullmq)**

  **Redis-based queue for Node.js**, MIT licensed with **5,000+ GitHub stars** . **Retry with exponential backoff** — configurable `attempts` and `backoff` . **Dead letter queue** — failed jobs move to DLQ after retries exhausted . **Best for Node.js background jobs** .



- **[Sidekiq](https://github.com/sidekiq/sidekiq)**

  **Ruby background job processing**, LGPL-3.0 licensed with **13,000+ GitHub stars** . **Retry with backoff** — automatic retries with exponential backoff . **Dead job queue** — failed jobs move to DeadSet after max retries . **Best for Ruby background jobs** .



- **[RQ (Redis Queue)](https://github.com/rq/rq)**

  **Simple Python task queue**, BSD-2-Clause licensed with **9,000+ GitHub Stars** . **Retry with backoff** — configurable retry intervals . **Failed queue** — failed jobs move to FailedQueue . **Best for simple Python task queues** .



### Error Handling Frameworks



- **[MassTransit](https://github.com/MassTransit/MassTransit)**

  **.NET distributed application framework**, Apache-2.0 licensed with **6,000+ GitHub stars** . **Built-in retry and DLQ** — configure retry policies and error queues per endpoint . **Best for .NET microservices** .



- **[NServiceBus](https://github.com/Particular/NServiceBus)**

  **.NET service bus**, commercial license with open-source core . **Automatic retry and DLQ** — first-level and second-level retries with error queue . **Best for .NET enterprise messaging** .



- **[Spring Cloud Stream](https://github.com/spring-cloud/spring-cloud-stream)**

  **Spring Boot messaging framework**, Apache-2.0 licensed . **Retry and DLQ via binder configuration** — supports RabbitMQ and Kafka DLQ . **Best for Java microservices** .



- **[Resilience4j](https://github.com/resilience4j/resilience4j)**

  **Fault tolerance library for Java**, Apache-2.0 licensed with **10,000+ GitHub stars** . **Retry, circuit breaker, and bulkhead** — combined with message queues for error handling . **Best for Java resilience** .



### Additional Strong Open-Source Options



- **Apache ActiveMQ** — Enterprise message broker with DLQ .

- **Apache Artemis** — High-performance messaging with DLQ .

- **ZeroMQ** — Messaging library (no built-in DLQ) .

- **NSQ** — Real-time distributed messaging .

- **Beanstalkd** — Simple work queue with delayed jobs .

- **Disque** — Distributed job queue .

- **Gearman** — Job server .

- **Kombu** — Messaging library for Python .



**Frameworks for building custom message queue error handling solutions**: Combine **RabbitMQ** for dead letter exchanges with TTL and max retry policies . Use **Apache Kafka** or **Redpanda** for high-throughput event streaming with DLQ patterns . Deploy **Apache Pulsar** for built-in dead letter topics and retry letter topics . Choose **Celery** for Python task queues with retry and DLQ . Integrate **BullMQ** for Node.js background jobs with exponential backoff . Use **MassTransit** or **NServiceBus** for .NET error handling patterns . Note that true managed message queuing with global infrastructure, automatic scaling, and vendor-supported SLAs (SQS, Azure Service Bus, Pub/Sub) remains primarily commercial territory; open-source stacks provide strong DLQ, retry, and error recovery foundations that require integration for complete message queue reliability.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Message queue error handling involves sensitive data and critical business processes. Self-hosted solutions require proper security hardening, access controls, and monitoring.

- **DLQ configuration is critical** — without DLQ, failed messages are lost or block queues. Configure max retry counts, TTL, and DLQ targets for every queue .

- **Poison messages can block queues** — implement message validation, dead lettering after N retries, and alerting on DLQ depth .

- **Retry with backoff prevents thundering herd** — use exponential backoff with jitter to avoid overwhelming downstream services .

- **License considerations**: RabbitMQ uses MPL-2.0, Kafka uses Apache-2.0, Pulsar uses Apache-2.0, Celery uses BSD-3-Clause, and BullMQ uses MIT. Verify licensing against your use case before committing.

- The open-source ecosystem provides strong DLQ, retry, and error recovery foundations, but **managed infrastructure, global scale, and vendor-supported SLAs** remain primarily commercial offerings.



---



**Made for backend engineers, platform teams, and organizations seeking message queue reliability sovereignty.**

Let's make message queue error handling more open, transparent, and reliable.
