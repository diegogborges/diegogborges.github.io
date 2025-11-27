---
title: "System Design"
date: 2030-11-25T14:28:58-03:00
draft: true
---

System Design: A Complete Guide for Modern Software Architecture
Table of Contents

Introduction

1. Scalability

Horizontal vs. Vertical Scaling

Stateless vs. Stateful Services

2. Caching

Cache Strategies

Where to Apply Caching

3. Load Balancing

Load Balancing Algorithms

4. Message Queues & Event-Driven Architecture

When to Use Queues

Event-Driven Benefits

5. Databases & Storage Design

Normalization vs. Denormalization

Sharding, Replication and Partitioning

6. Consistency Models

Strong vs. Eventual Consistency

CAP Theorem

7. API Design

REST vs. gRPC vs. GraphQL

8. CDN, Edge Computing & Global Performance

9. Observability

Logs, Metrics, and Traces

Alerting & SLO/SLI/SLA

10. Reliability & Resilience

Circuit Breakers

Retries, Backoff & Idempotency

11. Security in System Design

12. Practical Guidelines

Final Thoughts

Introduction

System Design is the discipline of architecting software systems that are scalable, resilient, observable, and cost-efficient. It goes far beyond writing code — it’s about making decisions that determine whether your system will withstand real-world load, failures, and growth.

This guide compiles the essential concepts you must understand to design production-grade systems used by millions of users.

1. Scalability

Scalability is the system’s ability to handle increased load without performance degradation.

Horizontal vs. Vertical Scaling

Vertical scaling (Scale-Up):

Add more CPU/RAM to a single machine

Simpler to implement

Limited by hardware

Horizontal scaling (Scale-Out):

Add more machines

Enables high concurrency

Requires stateless architecture

In modern architectures, horizontal scaling is the default strategy.

Stateless vs. Stateful Services

Stateless services are easier to scale because any instance can handle any request.

Stateful services require session affinity, partitions, or distributed storage.

2. Caching

Caching reduces latency and offloads databases by keeping frequently accessed data in memory.

Cache Strategies

Write-Through

Write-Back

Cache-Aside (most common)

TTL & Eviction Policies (LRU, LFU, FIFO)

Where to Apply Caching

Application-level (Redis, Memcached)

CDN caching

Database caching

Client-side caching

3. Load Balancing

Load balancers distribute incoming requests across multiple servers.

Load Balancing Algorithms

Round Robin

Least Connections

IP Hash

Weighted strategies

Health checks ensure dead nodes stop receiving traffic.

4. Message Queues & Event-Driven Architecture

Queues decouple systems and allow asynchronous communication.

When to Use Queues

Email delivery

Payment processing

Notifications

Heavy tasks

Event-Driven Benefits

Loose coupling

Higher resilience

Easy horizontal scaling

Replay capability

Common tools: Kafka, RabbitMQ, SQS, Google Pub/Sub

5. Databases & Storage Design
Normalization vs. Denormalization

Normalization → integrity

Denormalization → performance

Sharding, Replication and Partitioning

Replication: HA and read scalability

Sharding: splits data across nodes

Partitioning: organizes large datasets

Choose based on:

Traffic

Query patterns

Data size

Consistency requirements

6. Consistency Models
Strong vs. Eventual Consistency

Strong: reads always return the latest value

Eventual: replicas synchronize over time

CAP Theorem

You can pick two, never all three:

Consistency

Availability

Partition tolerance

Modern systems favor AP for global scale and CP for critical finance-like systems.

7. API Design

Choose API style based on purpose:

REST vs. gRPC vs. GraphQL

REST: universal, flexible, slower

gRPC: super fast, binary, ideal for microservices

GraphQL: client-optimized queries, perfect for mobile

8. CDN, Edge Computing & Global Performance

Improve speed and reduce latency by serving data closer to users.

Tools: Cloudflare, Akamai, Fastly, Fly.io

Benefits:

Lower load on origin servers

Faster load times globally

9. Observability

Observability ensures you understand what’s happening inside your system.

Logs, Metrics, and Traces

Logs: what happened

Metrics: numerical indicators

Traces: request journey across services

Alerting & SLO/SLI/SLA

Define:

SLI: what you measure

SLO: target

SLA: contractual guarantee

10. Reliability & Resilience
Circuit Breakers

Prevents cascading failures by stopping calls to unhealthy services.

Retries, Backoff & Idempotency

Retry with exponential backoff

Ensure operations are idempotent to avoid duplicates

11. Security in System Design

Every design must consider:

Authentication & Authorization

Rate limiting

Audit logs

Encryption in transit & at rest

Secret management

Never treat security as optional.

12. Practical Guidelines

Prefer simplicity over premature optimization

“If you don’t measure it, you don’t know it”

Prioritize Critical User Journeys

Involve SRE early

Build observability from day one

Use proven references: Google SRE, DNS RFCs, TCP/IP

Final Thoughts

System design is a continuous learning journey.
The goal is not just to build systems that work — but to build systems that keep working, even under pressure, failures, or massive growth.

Master these principles, and you'll be prepared to design robust, scalable, and resilient architectures used in real-world production environments.