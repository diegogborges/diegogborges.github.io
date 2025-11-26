---
title: "REST API - Design Guidelines"
date: 2025-11-17
tags: ["rest", "api", "backend", "web development"]
categories: ["backend"]
---

Everything you need to know to get started with REST in just a few minutes.

REST API is the technology that transformed the way systems communicate with each other.
It enables applications, websites, servers, and devices to exchange data quickly, securely, and universally — forming the foundation of modern apps, powerful integrations, and digital experiences that work anywhere.

## **Index**
* [What Is an API?](#-what-is-an-api)
* [What Is a REST API?](#-what-is-a-rest-api)
* [Key REST Concepts](#-key-rest-concepts)
  * [Resources](#resources)
  * [Main HTTP Methods](#main-http-methods)
  * [Data Formats](#data-formats)
* [🔧 RESTful API Characteristics](#-restful-api-characteristics)
  * [Stateless](#1-stateless)
  * [Client–Server Architecture](#2-clientserver-architecture)
  * [Cacheability](#3-cacheability)
  * [Uniform Interface](#4-uniform-interface)
  * [Layered System](#5-layered-system)
* [General Recommendations](#general-recommendations)
* [Use Plural Nouns in URLs](#use-plural-nouns-in-urls)
* [Keep the Base URL Simple and Intuitive](#keep-the-base-url-simple-and-intuitive)
* [Avoid Verb-Based URLs](#avoid-verb-based-urls)
* [Use HTTP Verbs to Operate on Resources](#use-http-verbs-to-operate-on-resources)
* [Resource Listing and Detail Retrieval](#resource-listing-and-detail-retrieval)
* [Associations](#associations)
* [Use Query Parameters to Reduce URL Complexity](#use-query-parameters-to-reduce-url-complexity)
* [Error Handling](#error-handling)
* [Versioning](#versioning)
* [Partial Response](#partial-response)
* [Pagination](#pagination)
* [Actions Not Involving Resources](#actions-not-involving-resources)
* [Multi-Format Support](#multi-format-support)
* [Attribute Naming](#attribute-naming)
  * [Attributes in Request/Response Bodies](#attributes-in-requestresponse-bodies)
  * [Attributes in URLs (Query Parameters)](#attributes-in-urls-query-parameters)
  * [Attributes in Headers](#attributes-in-headers)
* [References](#references)

---

# What Is an API?

An **API (Application Programming Interface)** is a set of standards and protocols that allow different systems or users to interact with an application.  
It enables clients to access the software’s features and services without needing direct access to its internal implementation.

---

# What Is a REST API?

A **REST API (Representational State Transfer API)** is an interface that enables communication between systems over the web following REST architectural principles.  
REST APIs use the **HTTP protocol** and rely on standardized resource-oriented operations.

---

# Key REST Concepts

### **Resources**
Resources are the entities exposed by the API—for example, users, products, or orders.  
Each resource is accessed through a unique **URL** (Uniform Resource Identifier).

---

### **Main HTTP Methods**

| Method | Purpose |
|--------|---------|
| **GET** | Retrieve information about a resource |
| **POST** | Create a new resource |
| **PUT** | Update an existing resource or create it if it does not exist |
| **DELETE** | Remove a resource |
| **PATCH** | Partially modify an existing resource |

---

### **Data Formats**
REST APIs typically exchange data using:

- **JSON (JavaScript Object Notation)** – lightweight, simple, widely adopted  
- **XML (eXtensible Markup Language)** – less common today but still supported

---

# 🔧 RESTful API Characteristics

### **1. Stateless**
Each request must contain all the information necessary for the server to process it.  
The server does **not store client state** between requests.

---

### **2. Client–Server Architecture**
REST separates:

- **Client** – responsible for the user interface  
- **Server** – responsible for data and logic  
- **Resources** – the objects exchanged between them  

Communication happens entirely through **HTTP**.

---

### **3. Cacheability**
REST APIs should allow responses to be **cached** whenever possible.  
This improves performance and reduces unnecessary network calls.

---

### **4. Uniform Interface**
A uniform interface makes client and server evolve independently.  
A REST API must provide:

- Consistent URLs  
- Standardized HTTP methods  
- Predictable input/output formats  

This standardization enables seamless integration between systems.

---

### **5. Layered System**
A REST architecture may include multiple layers with specific roles:

- Security  
- Load balancing  
- Routing  
- Caches  
- Gateways  

Each layer handles part of the request/response lifecycle, improving scalability and maintainability.

# **General Recommendations**

APIs should be grouped by business entities (e.g., products, branches, orders), and within each entity, you should expose CRUD operations (create, read, update, delete).

Follow these principles:

* Follow REST specification standards.
* Translate all path names, fields, parameters, and attribute identifiers into English.
* Document your API in the development documentation portal, then request publication to production documentation.
* Create test scenarios (success and failure) for each endpoint.

---

# **Use Plural Nouns in URLs**

Always favor plural nouns. Examples:

```
/customers
```

A specific resource:

```
/customers/1234
```

> **Avoid URLs with more than two levels!**

---

# **Keep the Base URL Simple and Intuitive**

### **Correct Structure:**

**Level 1:** A collection representing a business entity
**Level 2:** A specific element inside the collection

Example:

```
/customers
/customers/1234
```

---

# **Avoid Verb-Based URLs**

❌ **Avoid these patterns:**

```
/getCustomers
/saveCustomer
/deleteCustomer
```

---

# **Use HTTP Verbs to Operate on Resources**

| Resource          | POST    | GET                | PUT                         | DELETE               |
| ----------------- | ------- | ------------------ | --------------------------- | -------------------- |
| `/customers`      | Create  | List all customers | Batch update                | Delete all customers |
| `/customers/1234` | ❌ Error | Get customer 1234  | Update customer (if exists) | Delete customer      |

---

# **Resource Listing and Detail Retrieval**

When querying collections, return **minimal fields** (usually identifiers + summary).

**Example — Collection Query**

```
GET /employees
```

**Response:**

```json
{
  "records": [
    { "cpf": "123456", "name": "HENRIQUE DA SILVA" },
    { "cpf": "8795531", "name": "PAULO LEITE JUNIOR" },
    { "cpf": "458314", "name": "ROBERTO PEREIRA DOS SANTOS" }
  ]
}
```

---

**Example — Detail Query**

```
GET /employees/123456
```

**Response:**

```json
{
  "records": [{
    "cpf": "123456",
    "name": "HENRIQUE DA SILVA",
    "branch": 500,
    "jobTitle": "SOLUTION ARCHITECT SENIOR",
    "startDate": "2014-09-15T00:00:00-0300",
    "status": "Active"
  }]
}
```

---

# **Associations**

Retrieve all orders for a customer:

```
GET /customers/{id}/orders
```

Create an order for a customer:

```
POST /customers/{id}/orders
```

> URLs should rarely exceed 3 levels.

---

# **Use Query Parameters to Reduce URL Complexity**

Use query params for optional filters:

**Example**

```
GET /orders?salesbranch=1&status=6&zip=14403597
```

---

# **Error Handling**

Use a small set of HTTP status codes:

| Code | Message               | Use Case                           |
| ---- | --------------------- | ---------------------------------- |
| 200  | OK                    | Successful operation               |
| 204  | No Content            | Success, no payload (e.g., DELETE) |
| 207  | Multi-Status          | Batch operations                   |
| 400  | Bad Request           | Invalid client request             |
| 401  | Unauthorized          | Invalid credentials                |
| 404  | Not Found             | Resource not found                 |
| 500  | Internal Server Error | Server failure                     |

---

### **Recommended Error Payload Format**

```json
{
  "developerMessage": "Technical details and suggestions for resolving the error.",
  "userMessage": "User-friendly explanation.",
  "errorCode": 99999,
  "moreInfo": "https://example.com/errors/99999"
}
```

---

### **Example — 401 Unauthorized**

```json
{
  "developerMessage": "OAuth2 access token not provided",
  "userMessage": "Authentication Required",
  "errorCode": 20003,
  "moreInfo": "http://developer.example.com/errors/20003"
}
```

---

# **Versioning**

* Never publish an API without versioning.
* Prepend the version with `v`.
* The version should appear at the **leftmost position**:

```
/v1/orders
```

* Use simple ordinal numbers (no dots).
* Keep at least one previous version available.

---

# **Partial Response**

Use a `fields` parameter to return only selected attributes:

```
/orders/247571913?fields=total,status,branch
```

---

# **Pagination**

Use `limit` (number of items) and `offset` (starting point):

```
/orders?limit=25&offset=50
```

Return 25 records from #51 to #75.

Include total record count in metadata.

---

# **Actions Not Involving Resources**

Examples:

* Calculations
* Translations
* Conversions

These **do not** involve database resources and should use **verbs**, not nouns.

Example — currency conversion:

```
/convert?from=EUR&to=USD&amount=100
```

Document clearly that such endpoints behave differently.

---

# **Multi-Format Support**

To get XML:

```
/orders.xml
```

To get a specific order in XML:

```
/orders/1234.xml
```

> JSON should remain the default format.

---

# **Attribute Naming**

## **Attributes in Request/Response Bodies**

* Use **camelCase**
* Avoid snake_case and PascalCase

**Correct:**

```json
"startDate": "2014-08-06T00:00:00-0300",
"zipCode": 14403597
```

**Incorrect:**

```json
"created_at": "...",
"DateTime": "..."
```

### **Composite types must be nested objects**

**Correct:**

```json
"type": {
  "id": 1,
  "description": "store"
}
```

**Incorrect:**

```json
"typeId": 1,
"typeDescription": "store"
```

---

## **Attributes in URLs (Query Parameters)**

* Always lowercase
* Use dot notation for nested fields

**Correct:**

```
/v1/prices?branch.id=10&item.product.id=41702
```

**Incorrect:**

```
/v1/prices?branchId=10&itemProductId=41702
```

### **Substring filtering**

```
/v1/customers?name_contains=John
```

### **Value ranges**

```
/v1/orders?period_greater=2024-01-01&period_lesser=2024-01-02
```

---

## **Attributes in Headers**

* Do not use special characters
* Remain concise

**Correct:**

```
uuidProtocol
```

**Incorrect:**

```
UUID_Protocol
```

---

# **References**

* Mulloy, B. *Web API Design - Crafting Interfaces that Developers Love.* Apigee.
  [https://pages.apigee.com/web-api-design-ebook-sr-register.html](https://pages.apigee.com/web-api-design-ebook-sr-register.html)

