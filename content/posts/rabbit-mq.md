---
title: "Rabbit MQ"
date: 2025-12-02T16:53:48-03:00
draft: false
---

When you want to develop highly scalable distributed systems in several programming languages and one should communicate with others, it’s necessary an architecture with messaging queue systems and RabbitMq is one of the most used.

## Table of Contents
- [What is Messaging](#rabbitmq)
- [RabbitMQ](#rabbitmq)
- [How RabbitMQ Works](#how-rabbitmq-works)
- [AMQP Protocol](#amqp-protocol)
- [ACK](#ack)
- [Exchange and Routing Key](#exchange-and-routing-key)
  - [FANOUT](#fanout)
  - [DIRECT](#direct)
  - [TOPIC](#topic)
  - [HEADERS](#headers)
- [Channel](#channel)
- [Publishing](#publishing)
- [Listener](#listener)
- [Stream](#stream)

### What is Messaging
Messaging is a communication mechanism between systems where one publishes the message and any other as a client receives the same, thus simplifying a lot in the development of distributed systems.

### RabbitMQ
RabbitMQ is an open source messaging software developed in 2006 by Rabbit Technologies Ltd which was later acquired by SpringSource, more specifically, VMware.

Developed in Erlang, RabbitMQ is a Message-Oriented Middleware - MOM solution that works with the asynchronous exchange of messages between processes, applications or servers in a very reliable, fast and powerful way.

## How RabbitMq works

RabbitMQ is a Message Broker. Through an exchange and routing to queues, the Broker acts as an intermediary for who publishes and who will consume the message.
It ensures decoupling between services by disassociating the publisher and consumer of the message. In addition to storing messages, routing to queues, monitoring and managing messages.
Whatever messages the publishers send to RabbitMQ are stored in queues. Theoretically, the queue is a buffer of infinite size, publishers can send as many messages as they want.

## AMQP protocol
RabbitMQ implements several protocols such as AMQP, MQTT, STOMP and HTTP, but AMQP is the most used.
The AMQP or Advanced Message Queuing Protocol. It is a network communication protocol for MOM systems, which allows interoperability between many technologies and platforms.


## ACK
ACK is a mechanism in RabbitMQ that guarantees that the message has been consumed. The ACK is returned by the consumer to RabbitMQ confirming that the message has been received, processed and that RabbitMQ will be able to delete it. If there is a problem with the message consumption, connection error for example, the consumer will not send an ACK and RabbitMQ will understand that the message has not been fully processed and will requeue it.

## Exchange and routing key
RabbitMq uses exchanges, which are entities responsible for routing messages to different queues.
The relationships between exchanges and queues that define how messages should be routed are called bindings.
There are four types of exchanges:

## FANOUT
The FANOUT is one of the simplest, it simply ignores the route, the message is sent to all queues that are connected, that is, with the binding.


https://www.rabbitmq.com/tutorials/amqp-concepts.html

## DIRECT
The DIRECT exchange uses the routing key with the queue that has the binding. The message is only sent to the queue consisting of da key.

 
https://www.rabbitmq.com/tutorials/amqp-concepts.html

## TOPIC
TOPIC is almost similar to DIRECT, but in this one we can use * or # in the key, where the * replaces a word and the # replaces zero or more words in the key. With this exchange, rules for dynamic routing could be used.


https://springbootdev.com/2017/11/12/spring-amqp-rabbitmq-topic-exchange-example-part-1-producer-application/

## HEADERS
This exchange does not use keyed routing, routing is done based on criteria sent in the Header. It is similar to TOPIC, but without using a routing key.


## Channel
In RabbitMQ there is also the Channel, which is a virtual connection where the messages published and consumed from the queue are kept.

## Publishing
The publisher is any system that publishes messages to the queue.

## Listener
The listener, or consumer, is any other system that consumes messages from the queue.

## Stream
Stream was introduced in version 3.9 of RabbitMQ, and would be a different data structure than traditional RabbitMQ queues. In a traditional RabbitMQ queue, the consumer removes the messages read from the queue, while for RabbitMQ Stream the consumer does not remove the message, leaving the message intact to be read and reread.
