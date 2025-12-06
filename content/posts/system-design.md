---
title: "System Design"
date: 2025-12-04T14:28:58-03:00
draft: false
---

In this article, we explore how System Design goes far beyond diagrams, serving as a practical framework for reasoning, justifying decisions, and building scalable, well-structured systems.

## Table of Contents
- [System Design](#system-design)
    - [Introduction](#introduction)
    - [Understanding the Core Concepts](#understanding-the-core-concepts)
        - [Introduction to System Design](#introduction-to-system-design)
    - [What is System Design?](#what-is-system-design)
    - [Why is System Design Important?](#why-is-system-design-important)
    - [Working with Approximations](#working-with-approximations)
    - [Example of System Design Reasoning](#example-of-system-design-reasoning)
- [System Design in Big Techs](#system-design-in-big-techs)
    - [Why Big Techs Use System Design in Interviews](#why-big-techs-use-system-design-in-interviews)
    - [Why Many Candidates Fail](#why-many-candidates-fail)
    - [The Importance of Deduction and Approximation](#the-importance-of-deduction-and-approximation)
    - [System Design in the Real World](#system-design-in-the-real-world)
        - [Why System Design Is Essential in Practice](#why-system-design-is-essential-in-practice)
        - [Justifications and Trade-offs](#justifications-and-trade-offs)
- [The Six Elements of System Design](#the-six-elements-of-system-design)
    - [Introduction](#introduction)
    - [Six Fundamental Elements of System Design](#six-fundamental-elements-of-system-design)
        - [1. Requirements Gathering](#1-requirements-gathering)
        - [2. Capacity Planning](#2-capacity-planning)
        - [3. Data Modeling](#3-data-modeling)
        - [4. API Modeling](#4-api-modeling)
        - [5. Architecture Design](#5-architecture-design)
        - [6. Exploration & Justification (Trade-offs)](#6-exploration--justification-trade-offs)
    - [The Value of the Process](#the-value-of-the-process)
    - [Requirements — Deep Dive](#requirements-—-deep-dive)
        - [Core Features and Domain](#core-features-and-domain)
        - [Support Features](#support-features)
        - [Functional vs Non-Functional Requirements](#functional-vs-non-functional-requirements)
    - [Next Steps](#next-steps)


---

# System Design

## Introduction

In this new module, the focus is on **System Design**, an essential subject for anyone looking to advance in technology and system architecture.

Studying System Design helps you explore different possibilities when designing an application, allowing you to evaluate alternatives before finalizing the architecture. It's a practice widely used by Big Tech companies—both in daily work and hiring processes—because it evaluates how a professional thinks, structures ideas, makes technical decisions, and balances trade-offs.

Throughout this module, the goal is to provide the necessary foundation to understand what System Design is and how to apply it in practice. Over time, this knowledge can expand your technical repertoire and open doors to opportunities in large tech companies.

The central point is understanding how ideas and calculations connect, resulting in a solid and efficient architecture for your application.

---

## Understanding the Core Concepts

### Introduction to System Design

In this module, we approach System Design in a practical and applied manner. The idea is not only to understand fundamental concepts but also to exercise architectural reasoning through hands-on practice.

While some theoretical foundations will be reviewed with the help of slides, the focus remains on real-world scenarios involving architecture and technical decision-making.

---

## What is System Design?

**System Design** is the process of defining the architecture of a system, including:

- components,  
- modules,  
- interfaces,  
- data,  
- and the interactions between these parts.  

The objective is to ensure that the specified requirements are met efficiently.

Many assume System Design is simply “drawing architecture diagrams,” but it goes far beyond that. System Design is a structured process that forces intentional thinking about each decision, evaluating trade-offs and long-term impacts.

---

## Why is System Design Important?

- **Structured thinking:** avoids creating “automatic architectures” based only on reused patterns without reflection.  
- **Iterative process:** allows exploring multiple alternatives before selecting a final solution.  
- **Conscious decision-making:** helps identify immediate and long-term implications (costs, performance, maintenance, scalability).  
- **Exploration of multiple solutions:** the same problem can have several approaches, and System Design helps select the one that best fits the context.  

---

## Working with Approximations

System Design is not meant to be extremely detailed or definitive. Often, it relies on approximations to:

- gain speed,  
- focus on what truly matters,  
- objectively compare alternatives.  

This approximation-based process encourages practical thinking and helps evaluate solutions technically, financially, and in terms of long-term impact.

---

## Example of System Design Reasoning

Imagine your application needs to be extremely fast for specific operations.

One solution is to use **in-memory caching**, which provides high performance.

But in-memory cache is expensive. So the question becomes: *is it worth adopting this right now?*

Perhaps another strategy could be enough initially, delaying costs without significantly harming performance.

This type of analysis—considering alternatives, technical implications, and financial impacts—is exactly what makes System Design essential.

---

System Design is not just “architecture drawing,” but a deliberate process of defining a system. It helps plan solutions, explore alternatives, evaluate trade-offs, and prepare applications for both present and future needs.

Next, we will explore the relationship between System Design and Big Tech companies, understanding how the process is used in large-scale systems and technical interviews.

# System Design in Big Techs

## Table of Contents
- [Why Big Techs Use System Design in Interviews](#why-big-techs-use-system-design-in-interviews)
- [Why Many Candidates Fail](#why-many-candidates-fail)
- [The Importance of Deduction and Approximation](#the-importance-of-deduction-and-approximation)
- [System Design in the Real World](#system-design-in-the-real-world)
  - [Why System Design Is Essential in Practice](#why-system-design-is-essential-in-practice)
  - [Justifications and Trade-offs](#justifications-and-trade-offs)

---

## Why Big Techs Use System Design in Interviews

In the previous lesson, we covered the definition and importance of System Design. Now, let’s dive deeper into a crucial point: **why this practice is so valued by Big Techs during hiring processes.**

During a technical interview, it is very common to be asked to solve a System Design exercise. This happens because:

- The goal is not the exact final answer, but understanding **how you think**.  
- Interviewers want to see **how you reached a given solution or number**.  
- They analyze your **knowledge repertoire** and dive deeper into technologies based on your responses to measure your technical mastery.  

In summary, System Design is used as a tool to evaluate:

- Thought process  
- Deductive ability  
- Applied technical knowledge  

---

## Why Many Candidates Fail

If you had to take a System Design interview today, the chance of not doing well would be high. This happens because:

- System Design follows well-defined techniques and steps (step 1, 2, 3...).  
- Without this method, candidates tend to just “sketch ideas,” which rarely leads to good results.  
- Big Techs expect **well-structured thinking**, which requires practice and technique.  

In this module, you will learn these techniques, making the process easier and increasing your chances of success both in interviews and in your professional work.

---

## The Importance of Deduction and Approximation

Another highly valued skill in interviews is the ability to **deduce**.

Deduction means simplifying and approximating solutions instead of aiming for absolute precision.

- Often, a quick and approximate answer is more useful than spending too much time calculating a perfect one.  
- What matters is demonstrating **how you thought** and the **trade-offs** you considered.  

This reasoning can — and should — be learned. With practice, your ability to deduce will increase significantly.

---

## System Design in the Real World

So far, we’ve seen how System Design is used in Big Tech interviews. However, it’s essential to highlight that System Design is not only for hiring processes. In real-world work, especially for solution architects, it is an indispensable tool.

### Why System Design Is Essential in Practice

#### **1. Organizing Thought**

- Real systems can be extremely complex.  
- Explaining everything without structure leads to confusion.  
- System Design helps express ideas clearly so everyone involved can understand the proposed solution.

#### **2. Conviction in Decisions**

- By formalizing System Design, you gain time to reflect on your choices.  
- This gives you more confidence when presenting solutions.  
- Similar to TDD (Test-Driven Development), structuring before executing forces you to think better about the problem.

#### **3. Communication and Selling Tool**

- System Design is also a way to **sell your solution**.  
- Whether in meetings with technical teams, clients, or commercial departments, it becomes your main tool for clarity and credibility.  
- More than diagrams, it involves documented artifacts that justify every decision.

---

## Justifications and Trade-offs

A fundamental aspect of System Design is the ability to justify technical choices.

**Example:**  
If someone asks, *“Why use Apache Kafka?”*  
You shouldn’t answer with a generic explanation.

You need to present trade-offs, compare alternatives, and explain why Kafka is the most suitable option for the system’s context.

Without formalization, your decisions may seem arbitrary or based on guesswork.

---

In the real world, System Design is:

- A tool for clarity and expression for solution architects.  
- A process that strengthens technical conviction.  
- An efficient communication medium for clients and teams.  
- A set of documented artifacts that justify decisions and trade-offs, preventing poorly reasoned choices.  

# The Six Elements of System Design

## Table of Contents
- [Introduction](#introduction)
- [Six Fundamental Elements of System Design](#six-fundamental-elements-of-system-design)
  - [1. Requirements Gathering](#1-requirements-gathering)
  - [2. Capacity Planning](#2-capacity-planning)
  - [3. Data Modeling](#3-data-modeling)
  - [4. API Modeling](#4-api-modeling)
  - [5. Architecture Design](#5-architecture-design)
  - [6. Exploration & Justification (Trade-offs)](#6-exploration--justification-trade-offs)
- [The Value of the Process](#the-value-of-the-process)
- [Requirements — Deep Dive](#requirements-—-deep-dive)
  - [Core Features and Domain](#core-features-and-domain)
  - [Support Features](#support-features)
  - [Functional vs Non-Functional Requirements](#functional-vs-non-functional-requirements)
- [Next Steps](#next-steps)

---

## Introduction

Many people believe System Design is just about drawing architecture diagrams. That view is limited. Diagrams are only one element of the process — the real value of System Design lies in the set of techniques and methodologies that help structure and justify solutions.

---

## Six Fundamental Elements of System Design

To apply System Design consistently, highlight these six essential steps:

### 1. Requirements Gathering
The first step is understanding **why** the system exists.

- Developers often receive orders and start coding without questioning requirements.  
- The architect’s role is to ask the right questions to understand needs, goals, and constraints.

### 2. Capacity Planning
Estimate the demand the system must handle.

Typical questions:

- How many accesses per day?  
- What is the peak requests per second?  
- What is the data volume stored per month/year?  
- What throughput is expected?

These estimates guide choices for infrastructure, technology, and even programming languages.

### 3. Data Modeling
You don’t need to design the entire database in detail.

- Identify the main entities and their relationships.  
- Decide which type of database fits best:
  - Relational  
  - Key-value  
  - Document-oriented  
  - Graph-based

### 4. API Modeling
Define the system’s primary operations — you don’t need to implement every endpoint.

- Example: for ticket purchases, an API method might be `purchaseTickets(customer, event, quantity)`.  
- This modeling helps stakeholders clearly understand what the system does.

### 5. Architecture Design
This is when you create diagrams representing:

- Services  
- Cloud resources  
- Connections  
- Main components

Diagrams are important, but they must live within a broader process.

### 6. Exploration & Justification (Trade-offs)
After the design, evaluate and challenge your choices.

Typical questions:

- Why use Kafka instead of another messaging solution?  
- Why choose Redis over Memcached?

This exercise prevents automatic decisions based only on conventions or inherited practices. Justifying choices strengthens project clarity and solidity.

---

## The Value of the Process

System Design is not about “building like everyone else.” It exists to remove decisions from autopilot and force the architect to reflect, justify, and explore alternatives.

In daily work, this strengthens argumentation in meetings, improves communication with technical and business teams, and ensures proposed solutions are well-founded.

---

## Requirements — Deep Dive

The first essential element of System Design is requirement definition. Without requirements, you cannot build a consistent system. Requirements represent both the reason the application exists and the features it must provide.

This is not a return to old waterfall analysis models; requirements are a core part of any modern project.

### Core Features and Domain
Start by understanding:

- **What is the system domain?** → Why does this system exist and what problem does it solve?  
- **What are the core features?** → What does the system do within this domain?

This understanding ties directly to Domain-Driven Design (DDD), where features and models are structured around the business domain.

### Support Features
Beyond core features, every system needs complementary capabilities that support them.

- Example: in e-commerce, the core feature is selling products; payment is a **support feature** — an auxiliary capability that enables the primary feature.

### Functional vs Non-Functional Requirements
- **Functional requirements:** describe actions and behaviors the system must perform (what it should do).  
- **Non-functional requirements:** set constraints and qualities related to performance, security, scalability, usability, etc. (how it should behave).

---

## Next Steps

After mapping requirements, the System Design process advances to:

- Capacity planning (access counts, transactions, storage needs, etc.)  
- Data modeling  
- API modeling  
- Architecture design  
- Exploration and validation of the choices made

Understanding requirements is the first step that gives solidity to all subsequent architectural decisions.

---

Requirements are the foundation. Combined with capacity planning, data modeling, API design, architecture diagrams, and a disciplined trade-off analysis, these six elements form a repeatable, defensible System Design process that produces robust, communicable, and well-justified systems.
