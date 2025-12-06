---
title: "Messaging Systems Compared: RabbitMQ vs. Apache Kafka"
date: 2025-12-02T17:03:47-03:00
draft: false
---

This article provides a clear and concise comparison between RabbitMQ and Apache Kafka to help you choose the most suitable messaging solution for your system architecture.

## Table of Contents
- [Objective](#objective)
- [History](#history)
  - [RabbitMQ](#rabbitmq)
  - [Apache Kafka](#apache-kafka)
- [Solution Features and Comparisons](#solution-features-and-comparisons)
  - [RabbitMQ Features](#rabbitmq-features)
  - [Kafka Features](#kafka-features)
- [Consumption Strategy (Pull vs Push)](#consumption-strategy-pull-vs-push)
- [Comparative Use Cases](#comparative-use-cases)
- [Deployment](#deployment)

## Objective
The objective of this article is to clarify doubts regarding which messaging system is most appropriate when implementing your applications. It analyzes RabbitMQ and Apache Kafka.

## History

### RabbitMQ
RabbitMQ is an open-source generic messaging system developed in Erlang by telecom companies such as T-Mobile. It was created in 2007 and initially implemented AMQP, later supporting MQTT and STOMP through plugins.

Use cases:
- SumUp
- Vocalink
- Goldman Sachs
- Nintendo Online
- T-Mobile

### Apache Kafka
Kafka was developed by LinkedIn in 2010, released as open‑source in 2011, and later adopted by the Apache Foundation. It is a high‑volume messaging and streaming platform.

Use cases:
- LinkedIn
- Netflix
- PayPal
- Spotify
- Uber

## Solution Features and Comparisons
Below is a full overview of how both systems operate.

## RabbitMQ Features
RabbitMQ is a mature and flexible broker supporting multiple messaging models.

### Simple Queues
A single producer and a single consumer.

### Work Queues
A producer pushes tasks to multiple consumers for scalability and throughput.

### Publish/Subscribe (Fanout Exchange)
Messages are broadcast to multiple queues. Common in Event Sourcing.

### Direct Exchange (Routing Key)
Routes messages according to a routing key.

### Topic Exchange
Routing keys consist of dot‑separated words:
- `*` matches one word
- `#` matches zero or more words

### RPC (Remote Procedure Call)
Implements pseudo‑synchronous behavior with:
- RPC queue
- Callback queue
- Correlation ID

### Additional Notes
- Runs on ports 5671/5672
- Libraries available for many programming languages
- Built in Erlang for real‑time, mission‑critical applications

## Kafka Features
Kafka consists of four core components:
- Producers
- Consumers
- Connectors
- Stream processors

### Producer API
Publishers send data to one or more topics.

### Consumer API
Consumers read data from Kafka, usually via port 9092.

### Connectors
Reusable producers and consumers that integrate Kafka with external systems.

### Stream API
Used for applying transformations to event streams.

### Topic & Partition Model
Each topic contains one or more partitions. Partitions behave like ordered logs with incremental offsets.

### Offsets
Each consumer maintains its own position in the log.

### Replication and Availability
Kafka replicates partitions across servers. With replication factor N, data remains available even if N‑1 servers fail.

### Consumer Groups
Consumers are grouped for scalability and fault tolerance. Messages are distributed among consumers in a group.

### Ordering
Kafka guarantees order only within a partition. For global ordering, use a single partition topic.

## Consumption Strategy (Pull vs Push)

### Kafka – Pull
Consumers pull batches of messages from partitions using offsets. Suitable for:
- High‑throughput processing
- Stream replay
- Backpressure control

### RabbitMQ – Push
The broker pushes messages to consumers. Pre‑fetching is used to avoid overload and maintain low latency.

## Comparative Use Cases

### Volume & Hardware
- **RabbitMQ:** Scales well but requires more nodes at very high throughput.
- **Kafka:** Handles millions of messages per second efficiently.

### Sequential/Temporal Processing
- **RabbitMQ:** No built‑in order guarantee.
- **Kafka:** Ordered within partitions.

### Message Lifetime
- **RabbitMQ:** Messages disappear after consumption.
- **Kafka:** Log‑based retention with TTL and replay.

### Delivery Guarantees
- **RabbitMQ:** Supports acknowledgments, durability; may deliver duplicates.
- **Kafka:** Strong ordering and batch‑level guarantees; supports offset‑controlled replay.

### Message Priority
- **RabbitMQ:** Supports priority queues.
- **Kafka:** Does not support priority; achieved through topic architecture.

### Protocol Support
- **RabbitMQ:** AMQP, MQTT, STOMP.
- **Kafka:** Proprietary TCP protocol.

### Broker Intelligence
- **RabbitMQ:** Routing and balancing done by the broker.
- **Kafka:** Consumers manage offsets and strategy.

### Footprint
- **RabbitMQ:** Suitable for IoT and embedded systems.
- **Kafka:** Requires heavier infrastructure.

## Deployment

### RabbitMQ
- Simple to configure
- Works on‑premise, Docker, Kubernetes, or cloud
- Available via providers like CloudAMQP

### Kafka
- Historically required ZooKeeper (now optional with KRaft mode)
- Works on‑premise, containers, cloud
- Available via providers like Confluent
- Supports storage systems like HDFS, S3, and traditional filesystems
