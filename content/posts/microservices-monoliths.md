---
title: "Microservices Monoliths"
date: 2025-11-26T16:02:19-03:00
draft: false
---

Microservices or Monolith? Discover the strengths, the trade-offs, and the real-world lessons every developer must know before deciding how to start a project.

- [Microservices and Event-Driven Architecture](#microservices-and-event-driven-architecture)
  - [Introduction to the Module: Microservices-Based Architecture](#introduction-to-the-module-microservices-based-architecture)
  - [Why Study Microservices?](#why-study-microservices)
  - [What You Will Learn in This Module](#what-you-will-learn-in-this-module)
  - [Why This Module Matters](#why-this-module-matters)
  - [Our Goal](#our-goal)

- [Monolithic Systems](#monolithic-systems)
  - [What Is a Monolithic System?](#what-is-a-monolithic-system)
    - [Characteristics](#characteristics)
  - [Teamwork Inside a Monolith](#teamwork-inside-a-monolith)
  - [Practical Benefits](#practical-benefits)
  - [Technological Constraints](#technological-constraints)
  - [Deployment Risks](#deployment-risks)
  - [Conclusion About Monoliths](#conclusion-about-monoliths)

- [What Are Microservices](#what-are-microservices)
  - [Core Principle: SRP](#core-principle-srp)
  - [Relationship With Domain-Driven Design (DDD)](#relationship-with-domain-driven-design-ddd)
  - [Independence and Autonomy](#independence-and-autonomy)
    - [Example: Graceful Degradation](#example-graceful-degradation)
  - [Part of a Bigger Machine](#part-of-a-bigger-machine)
  - [Summary](#summary)

- [Microservices-Based Architecture](#microservices-based-architecture)
  - [Microservice ≠ Architecture](#microservice--architecture)
  - [Main Characteristics](#main-characteristics)
    - [Use of Multiple Technologies](#use-of-multiple-technologies)
  - [Governance vs Total Freedom](#governance-vs-total-freedom)
    - [Platform Teams](#platform-teams-usually-provide)
  - [The Myth of Total Freedom](#the-myth-of-total-freedom)
  - [Summary](#summary-1)

- [Microservices Setup](#microservices-setup)
  - [1. Less Risky Deployment](#1-less-risky-deployment)
  - [2. Specialized Teams](#2-specialized-teams)

- [Scaling Microservices: Reality vs Myth](#scaling-microservices-reality-vs-myth)
  - [1. The Promise](#1-the-promise)
  - [2. The Hidden Side](#2-the-hidden-side)
  - [3. The Myth: “Monoliths Don’t Scale”](#3-the-myth-monoliths-dont-scale)
  - [4. Communication Between Services](#4-communication-between-services)
  - [Conclusion](#conclusion)

- [Distributed Architectures Are Necessary](#distributed-architectures-are-necessary)
  - [Why Do Large Companies Need Them?](#why-do-large-companies-need-them)
  - [Microservices: The “Bitter Medicine”](#microservices-the-bitter-medicine)
  - [Reflection](#reflection)

- [When to Choose Monolithic Systems](#when-to-choose-monolithic-systems)

- [When to Choose Microservices](#when-to-choose-microservices)

- [Provocation: Are You Ready for Microservices?](#provocation-are-you-ready-for-microservices)

- [Final Analogy](#final-analogy)


# Microservices and Event-Driven Architecture
## Introduction to the Module: Microservices-Based Architecture

In this module, we explore the essential foundations of microservices architecture and set expectations so you know exactly what you will learn.

---

## Why Study Microservices?

Although widely used in large companies, microservices often **fail in practice** — not because of technical issues, but due to a **lack of conceptual understanding** among developers, tech leads, and architects.

They are frequently adopted for the **wrong reasons**, without clear goals or mastery of the fundamentals.

---

## What You Will Learn in This Module

- Fundamentals of microservices-based architecture  
- When to use and when to avoid microservices  
- How microservices work in practice and their challenges  
- Strategies to reduce failure risks  
- How to avoid the **“death star”** (excessive dependencies)  
- Difference between **choreography vs. orchestration**  

---

## Why This Module Matters

Most of the content is **theoretical**, because the biggest challenge is not creating an isolated microservice — that part is simple — but understanding **how to compose and organize the entire architecture**.

---

## Our Goal

To share solid principles that accelerate your journey and help you avoid common pitfalls.

---

# Monolithic Systems

## What Is a Monolithic System?

A monolith concentrates all scopes and areas inside a **single application**.

### Characteristics
- All components and features grouped together  
- Simple and direct internal communication  
- Still predominant in the market  

---

## Teamwork Inside a Monolith

- Squads work on different parts of the same system  
- Requires organization to avoid Git conflicts  
- Automated tests reduce risks  

---

## Practical Benefits

- Lower infrastructure cost  
- Great for small and medium businesses  
- Higher productivity with unified standards  

---

## Technological Constraints

- Single programming language  
- No queues, circuit breaker, or multiple databases  
- Simple deployment  

---

## Deployment Risks

- If deployment fails, the **entire system goes down**  
- Microservices reduce this risk  
- Blue-green or canary deployments minimize impact  

---

## Conclusion About Monoliths

Monoliths are simple, efficient, and perfectly suitable for many scenarios — especially early in a project.

---

# What Are Microservices?

Microservices are **small, independent applications** with a well-defined scope.

---

## Core Principle: SRP

A microservice should have **a single reason to change** (SRP — Single Responsibility Principle).

---

## Relationship With Domain-Driven Design (DDD)

- Bounded Contexts help identify services  
- But not every context becomes a microservice  

---

## Independence and Autonomy

Each microservice must:

- Continue working even if others fail  
- Have fallback and resilience mechanisms  

### Example: Graceful Degradation
If the account calculation service is down:  
→ Display the **last known balance** to the user.

---

## Part of a Bigger Machine

A microservice in total isolation is **not** a microservice — it's just a small system.

---

## Summary

- Clear scope  
- Independent and autonomous  
- Part of an ecosystem  
- More complex communication  

---

# Microservices-Based Architecture

## Microservice ≠ Architecture

- **Microservice:** a software unit  
- **Architecture:** how multiple units are organized  

---

## Main Characteristics

### Use of Multiple Technologies

Each service may use different languages or databases — but this requires **governance**.

---

## Governance vs Total Freedom

- Standards increase productivity  
- Micromanagement harms development  

### Platform teams usually provide:
- Templates  
- SDKs  
- Internal development standards  
- Infrastructure tools  

---

## The Myth of Total Freedom

Too many technologies create **expensive and hard-to-maintain systems**.

---

## Summary

Microservices require:

- Governance  
- Standardization  
- Balance between freedom and consistency  

---

# Microservices Setup

## 1. Less Risky Deployment

- If one service fails, the others keep running  
- Reduces user impact  

But increases complexity:

- CI/CD per service  
- Dedicated monitoring  
- Infrastructure per service  

---

## 2. Specialized Teams

Microservices allow:

- Domain-focused teams  
- More technical depth  
- Faster business delivery  

---

# Scaling Microservices: Reality vs Myth

## 1. The Promise

- Scale only the critical parts  
- Reduce resource waste  

---

## 2. The Hidden Side

- Many pipelines  
- Higher infrastructure cost  
- More complex monitoring  

---

## 3. The Myth: “Monoliths Don’t Scale”

Monoliths **do** scale — vertically and horizontally.

---

## 4. Communication Between Services

Tools like Kafka, RabbitMQ, or SQS:

- Increase complexity  
- Require cultural changes  
- Increase operational costs  

---

## Conclusion

Microservices only make sense in **large and complex environments**.

---

# Distributed Architectures Are Necessary

## Why Do Large Companies Need Them?

- Large teams  
- Large domains  
- Complex business rules  

---

## Microservices: The “Bitter Medicine”

They are:

- Hard  
- Expensive  
- Necessary at scale  

---

## Reflection

The choice must depend on **context**, not trends.

---

# When to Choose Monolithic Systems

Ideal for:

- MVPs and POCs  
- Product discovery  
- High uncertainty  
- Low governance maturity  
- Small teams  
- Limited budget  

**Monolith = simple, cheap, and fast.**

---

# When to Choose Microservices

Best choice when:

- Many teams work simultaneously  
- Domains are well defined  
- Need to scale isolated components  
- Use of multiple technologies  

Microservices are about **scaling organizations**, not only systems.

---

# Provocation: Are You Ready for Microservices?

You must master:

- Containers  
- CI/CD  
- Distributed architecture  
- Asynchronous communication  
- Independent databases  
- Observability (logs, metrics, tracing)  
- DDD  

---

## Final Analogy

A distributed environment is like an airplane cockpit:

You don’t need to press every button today —  
but you must know what each one does,  
because eventually, you'll need them.
