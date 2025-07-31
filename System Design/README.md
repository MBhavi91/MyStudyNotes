# Ultimate System Design Detailed Outline

## Table of Contents

1. [Foundations of System Design & Fundamentals](#1-foundations-of-system-design--fundamentals)

   - [What is System Design?](#what-is-system-design)
   - [Types of Design](#types-of-design)
   - [Requirements](#requirements)
   - [CAP Theorem](#cap-theorem)
   - [PACELC Theorem](#pacelc-theorem)
   - [ACID vs BASE](#acid-vs-base)
   - [Consistency Models](#consistency-models)
   - [Scalability](#scalability)
   - [Latency vs Throughput](#latency-vs-throughput)
   - [Load Estimation](#load-estimation)
   - [Availability, Reliability, Durability](#availability-reliability-durability)
   - [Performance Bottlenecks](#performance-bottlenecks)
   - [Monolith vs Microservices vs Serverless](#monolith-vs-microservices-vs-serverless)

2. [Networking Basics & OS Concepts](#2-networking-basics--os-concepts)
3. [Design Patterns and Architectures](#3-design-patterns-and-architectures)
4. [Data Modeling and Storage Systems](#4-data-modeling-and-storage-systems)
5. [Caching Systems](#5-caching-systems)
6. [Load Balancing](#6-load-balancing)
7. [Message Queues & Stream Processing](#7-message-queues--stream-processing)
8. [Distributed Systems Principles](#8-distributed-systems-principles)
9. [Search Systems](#9-search-systems)
10. [Rate Limiting & Throttling](#10-rate-limiting--throttling)
11. [Security & Authorization](#11-security--authorization)
12. [Monitoring, Logging & Observability](#12-monitoring-logging--observability)
13. [Designing for Scale](#13-designing-for-scale)
14. [Failure Recovery & Resilience](#14-failure-recovery--resilience)
15. [Real-World Design Scenarios](#15-real-world-design-scenarios)
16. [Other Advanced Topics & Best Practices](#16-other-advanced-topics--best-practices)
17. [System Design Interview Process](#17-system-design-interview-process)

---

## 1. Foundations of System Design & Fundamentals

### What is System Design?

**System Design** is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements. It is a high-level approach used in both software and hardware domains, but it's especially critical in software engineering when building large, scalable, and complex systems like web applications, cloud services, or distributed systems.

System design bridges the gap between a conceptual idea and a practical, functioning system. It is both a creative and analytical discipline, combining problem-solving, engineering principles, and architectural patterns.

It involves making decisions about:

- **What** components the system will have
- **How** those components will interact.
- **Where** data will be stored and processed.
- **How** users or other systems will interact with it.

This process ensures the system fulfills **both functional requirements** (what the system should do) and **non-functional requirements** (performance, scalability, security, etc.).

#### Goals of System Design

The primary goals of system design are to:

- **Define architecture:** Determine how different parts of the system will interact.
- **Ensure scalability:** The system should handle increasing loads efficiently.
- **Achieve reliability:** The system should function correctly under expected and unexpected conditions.
- **Maintainability:** Systems should be easy to modify, update, or debug.
- **Efficiency:** Optimal use of resources such as memory, CPU, and bandwidth.
- **Security:** Safeguarding data and preventing unauthorized access.
- **User-centric design:** Ensuring good user experience and usability.

#### Importance of System Design

System design is crucial for several reasons:

- **Foundation of Software Development:** A well-thought-out design reduces errors and improves the quality of the final product.
- **Scalability and Flexibility:** Good design anticipates future growth and changes.
- **Team Collaboration:** Provides a shared understanding and blueprint for all stakeholders.
- **Cost Efficiency:** Early detection of flaws through design saves time and development costs.
- **Performance Optimization:** It helps identify potential bottlenecks and address them during the design phase.

#### Types of System Design

1. **High-Level Design (HLD):**

   - Focuses on system architecture
   - Identifies modules, data flow, and technologies
   - Defines how components interact

2. **Low-Level Design (LLD):**

   - Detailed internal logic of components
   - Class diagrams, method signatures, database schemas
   - Often used by developers for implementation

#### Key Components of System Design

1. **Scalability**
   - Can the system handle increased load?
   - Horizontal scaling (more machines) vs. vertical scaling (more power to a machine)
2. **Performance**
   - Latency: Time taken to respond.
   - Throughput: Requests handled per second.
3. **Availability**
   - How often is the system up and running?
   - 99.9% (three 9s) = 8.76 hours downtime/year
4. **Reliability**
   - Can the system work correctly even with failures?
   - Redundancy, failover mechanisms, backups
5. **Maintainability**
   - How easy is it to modify, update, or fix the system?
6. **Security**
   - Protecting data and services from unauthorized access
7. **Consistency**
   - Ensuring data remains accurate across distributed systems (CAP theorem comes into play here)

System design is not just about drawing boxes and arrows—it's about creating systems that are **robust, scalable, secure, and efficient.** Whether you’re building a small feature or architecting an entire platform, system design is a **critical skill** that shapes how software functions in the real world.

### Types of Design

#### High-Level Design (HLD)

High-Level Design (HLD) outlines the **system architecture** — how the components interact, what technologies are used, and how the system is structured.

It's like the **blueprint of a house** before it's built: rooms, floors, plumbing lines — but not down to the color of the walls.

**Goals of HLD**

- Define **scope** of the system
- Visualize **system architecture**
- Identify **modules, services, and interactions**
- Choose **technology stack**
- Show **data flow and control flow**
- Support **non-functional requirements:** scalability, performance, availability, etc.

**Key Components of HLD**

| Component                | Explanation                                         | Example                                      |
| ------------------------ | --------------------------------------------------- | -------------------------------------------- |
| System Architecture      | Overall layout: monolith, microservices, serverless | Microservices with API Gateway               |
| Modules/Components       | Subsystems of the application                       | Auth Service, Product Catalog, Cart Service  |
| Data Flow Diagrams (DFD) | How data moves across modules                       | User → API → DB                              |
| Technology Stack         | Frameworks, databases, message queues               | React, Node.js, PostgreSQL, Kafka            |
| API Contracts            | What APIs are exposed, input/output                 | `/login`, `/createOrder`                     |
| Third-party Integrations | External systems like Stripe, Firebase, Twilio      | SMS with Twilio                              |
| Security Design          | Authentication, authorization, encryption           | JWT, OAuth 2.0, HTTPS                        |
| Deployment Architecture  | Servers, load balancers, CDNs                       | AWS EC2 + NGINX + CloudFront                 |
| Caching Strategy         | Improves performance and latency                    | Redis for session & frequently accessed data |
| Scalability              | Strategy Horizontal scaling, stateless services     | Kubernetes-based auto-scaling                |
| Monitoring & Logging     | Tools for observability                             | Prometheus, Grafana, ELK stack               |

**Tools for HLD**

- **Diagramming:** Draw.io, Lucidchart, Excalidraw, Miro
- **Documentation:** Notion, Confluence, Google Docs
- **Architecture Modeling:** C4 Model, ArchiMate, UML

**When to Use HLD**

- At the start of system design
- During architectural discussions or reviews
- For project proposals and planning
- In system design interviews

**HLD Example: Ride-Sharing App (like Uber)**

- **Users:** Riders & Drivers
- **Components:**
  - Rider App
  - Driver App
  - Matching Engine
  - Payment Gateway
  - Notification Service
- **Data Flow:**
  - Rider → Request Ride → Matching Engine → Driver Assigned
- **Architecture:**
  - Microservices + REST APIs
  - Real-time location tracking using WebSockets or MQTT
- **Database:**
  - PostgreSQL (Transactional Data)
  - Redis (Session & Cache)
  - MongoDB (Geospatial Data)

#### Low-Level Design (LLD)

Low-Level Design (LLD) zooms in on the **implementation details** of each component. It defines **classes, methods, data structures, algorithms, database schema**, and how everything is built internally.

It’s like the **interior design of your house:** wall colors, furniture layout, plumbing details.

**Goals of LLD**

- Break HLD components into **concrete class structures**
- Design **business logic**, workflows, and algorithms
- Define **method signatures** and data flow between functions
- Ensure **code-level consistency** and reusability
- Identify **bottlenecks** and optimize for efficiency

**Key Components of LLD**

| Component            | Description                          | Example                                 |
| -------------------- | ------------------------------------ | --------------------------------------- |
| Class Diagrams       | Object-oriented layout of entities   | `User`, `Ride`, `Driver` classes        |
| Interfaces/Contracts | Interaction points between modules   | `UserRepository`, `RideService`         |
| Database Schema      | Detailed table design with relations | Tables: `users`, `rides`, `payments`    |
| Algorithms           | Logic for core features              | Dijkstra’s for shortest route           |
| Data Structures      | To support performance and use-case  | Min-Heap, HashMap, Trie                 |
| Sequence Diagrams    | Object interactions over time        | Request Ride → Assign Driver → Notify   |
| Error Handling       | Logic Fault tolerance                | Retry, circuit breakers, fallback logic |
| Concurrency Handling | Thread safety, locks, queues         | Mutex, semaphores in ride-matching      |
| Design Patterns      | Reusable design techniques           | Singleton, Factory, Observer, Strategy  |

**Tools for LLD**

- **UML Tools:** Visual Paradigm, StarUML, PlantUML
- **ERD Tools:** dbdiagram.io, SQLDBM, QuickDBD
- **Code Modeling:** Source code IDEs, Lucidchart, IntelliJ UML Plugin

**When to Use LLD**

- During actual coding phase
- While reviewing system behavior and dependencies
- In code reviews or design discussions
- In LLD coding interviews

**LLD Example: URL Shortener**

- **Class Design (Python-style):**

```python
class URLShortener:
def **init**(self):
self.short_to_long = {}
self.long_to_short = {}

    def shorten(self, long_url: str) -> str:
        # Logic to shorten and store
        ...

    def expand(self, short_url: str) -> str:
        # Logic to retrieve original
        ...
```

- **Database Table:**

```sql
CREATE TABLE url_map (
id SERIAL PRIMARY KEY,
short_url VARCHAR(10) UNIQUE,
long_url TEXT,
created_at TIMESTAMP
);
```

- **Algorithm:**
  - Base62 encoding
  - Hashing + collision check
  - Expiry cleanup logic

**HLD vs LLD – Complete Comparison Table**
|Feature| HLD| LLD|
|---- | ---- | --- |
|Focus| Architecture and design overview| Internal logic and code structure|
|Scope| Modules, systems, data flow, APIs| Classes, methods, algorithms, DB schema|
|Abstraction| High-level (black box view)| Low-level (white box view)|
|Tools Used| Diagrams, flowcharts, architecture docs| UML, class diagrams, pseudo-code|
|Team| Architects, senior devs| Developers, engineers|
|Deliverables| Architecture doc, system diagram, tech stack| Class diagram, DB design, detailed logic|
|Time of Use| Before implementation | During implementation|
|Example| Output Architecture diagram of an e-commerce system| Class structure of CartService|

#### Best Practices

**HLD Best Practices**

- Modularize the system: define clear service boundaries
- Ensure scalability and fault-tolerance are covered
- Use layered architecture (client, service, database, cache)
- Include data flow diagrams for clarity
- Document assumptions, decisions, and trade-offs

**LLD Best Practices**

- Follow SOLID principles (OOP)
- Use design patterns where appropriate
- Keep class responsibilities single and focused
- Choose efficient data structures
- Write testable and modular code

#### Common Interview Problems Using HLD & LLD

**HLD-Oriented:**

- Design YouTube
- Design WhatsApp
- Design Instagram Stories
- Design Uber

**LLD-Oriented:**

- Design a Parking Lot
- Design Elevator System
- Design Tic-Tac-Toe
- Design File System
- Design Rate Limiter

#### Summary

| Category   | HLD                                            | LLD                               |
| ---------- | ---------------------------------------------- | --------------------------------- |
| Defines    | What system will do and how it will look       | How it will be implemented        |
| Involves   | Architecture, components, APIs                 | Classes, methods, logic           |
| Helps With | Planning, budgeting, stakeholder communication | Development, testing, refactoring |

### Requirements

#### What Are Functional Requirements?

**Functional requirements** define what a system is supposed to do. These are the specific **features, behaviors, and capabilities** of the system. They describe the **functions** that a system must perform to satisfy user and business needs.

Think of functional requirements as the **"actions"** of the system — the tasks the system must be able to handle.

**Characteristics of Functional Requirements:**

- Directly tied to **user expectations** and business logic
- Described as **use cases, user stories, or features**
- Usually start with "The system shall..." or "The user should be able to..."
- Can be clearly tested — either it works or it doesn’t

**Categories of Functional Requirements**

These are typically grouped based on what the system must do to serve its purpose. Here are the common categories:

1. **User Interactions**
   - What actions the user can perform in the system.
   - Includes login, registration, profile management, etc.
   - **Example:** Users should be able to sign in using Google or email.
2. **Business Rules**
   - Logical rules that dictate system behavior in specific conditions.
   - These reflect company policies or domain-specific rules.
   - **Example:** A user cannot withdraw more than their current balance.
3. **Data Management**
   - How data is created, read, updated, and deleted (CRUD).
   - Involves database operations, input/output handling, validations.
   - **Example:** The system must allow an admin to update user roles.
4. **System Workflows**
   - Series of steps or processes the system must perform.
   - Often part of complex multi-step features.
   - **Example:** A user places an order → payment is confirmed → order is processed → delivery is scheduled.
5. **Authorization and Roles**
   - Who can do what — defining different user roles and access controls.
     **Example:** Only admin users can delete posts.

**Examples:**

Imagine you are building an online banking app:

- The user should be able to log in with a username and password.
- The system should allow the user to check their account balance.
- The system must support money transfers between accounts.
- Users should receive a confirmation email after every transaction.
- The system should support multiple user roles, such as admin and customer.

These are all **functional** because they describe **specific things the system must do.**

#### What Are Non-Functional Requirements?

**Non-functional requirements** describe **how** the system performs its functions. They are not about specific tasks but about the **quality attributes** of the system. These requirements define **standards, performance benchmarks, and constraints** for how the system should behave.

In simple terms, they answer questions like:

- How fast should it work?
- How many users should it handle?
- How secure should it be?
- How easy should it be to use or maintain?

**Characteristics of Non-Functional Requirements:**

- They are often **measurable** but not always black-and-white (e.g., “fast” can be subjective unless quantified).
- They ensure the system is **usable, scalable, reliable, and secure.**
- They are usually **cross-cutting concerns** that apply to the whole system, not just a single feature.

**Examples:**

Let’s use the same online banking app:

- The system should respond to user requests within **2 seconds.**
- The app should handle **up to 100,000 concurrent users.**
- The system should have **99.99% uptime** (availability).
- User data must be **encrypted in transit and at rest.**
- The system should be **compatible with both mobile and desktop browsers.**
- The backend should be **designed for easy future maintenance and upgrades.**
- There should be **automatic failover** in case a server goes down.

These are non-functional because they describe the quality, behavior, and constraints of the system, not specific actions.

**Categories of Non-Functional Requirements**
These define the **quality, efficiency,** and **usability** of the system. Here's a breakdown:

1. **Performance**

- How fast the system responds to requests.
- Includes latency, throughput, response time.
- **Example:** All API calls should respond in under 300ms.

2. **Scalability**

- System's ability to handle increased load (users, data, traffic).
- Can be vertical (bigger servers) or horizontal (more servers).
- **Example:** The system should support up to 1 million users during peak hours.

3. **Availability**

- How much time the system is operational and accessible.
- Measured in uptime (e.g., 99.99%).
- **Example:** The service must be available 24/7 with a maximum downtime of 5 minutes per month.

4. **Security**

- Protection of data, preventing unauthorized access, and secure communication.
- Includes encryption, authentication, authorization.
- **Example:** All sensitive data should be encrypted using AES-256.

5. **Maintainability**

- How easy it is to update, debug, and upgrade the system.
- Related to modularity and clean code practices.
- **Example:** The system architecture must support hotfix deployment without downtime.

6. **Usability**

- How easy and intuitive the system is to use.
- Includes user interface design and user experience.
- **Example:** First-time users should be able to navigate the app without external help.

7. **Portability**

- The ability of the system to operate on various platforms and environments.
- **Example:** The web application should work on all major browsers and devices.

8. **Reliability and Fault Tolerance**

- The system’s ability to recover from crashes or errors and continue working.
- **Example:** In case of server failure, traffic should be rerouted to a backup server within 10 seconds.

9. **Capacity**

- Resource limits
- **Example:** Support 100K active sessions

10. **Compliance**

- Legal and standards
- **Example:** GDPR, HIPAA, PCI-DSS adherence

#### In System Design Interviews

**You Should Ask:**

**Functional**

- What are the core features the system must support?
- What workflows or user interactions are expected?

**Non-Functional**

- What’s the expected traffic (QPS)?
- Is high availability required?
- What latency is acceptable?
- Are there security/compliance constraints?

#### How They Influence Architecture

| Requirement  | Impact on Design                           |
| ------------ | ------------------------------------------ |
| Performance  | Caching, CDNs, async processing            |
| Scalability  | Load balancing, partitioning, auto-scaling |
| Security     | Auth, encryption, role-based access        |
| Availability | Redundancy, failover, retries              |
| Usability    | UI/UX simplicity, A/B testing              |
| Functional   | Microservices for modular features         |

#### Why These Requirements Are Important in System Design

1. **Clear Understanding of Scope**

- Separating functional and non-functional requirements helps define the **scope and boundaries** of the system. You know what it must do and how well it must do it.

2. **Design Decisions**

- Functional requirements help define **core architecture and modules.**
- Non-functional requirements influence **technology stack, database choices, caching, load balancing,** etc.

3. **Prioritization & Planning**

- You can prioritize core features (functional) and gradually improve quality (non-functional) — but you know both are coming.

4. **Testing & Quality Assurance**

- Functional requirements are tested with **unit, integration, and system tests.**
- Non-functional requirements need **performance testing, load testing, security audits,** etc.

5. **Improved User Experience**

- Users won’t just judge your product by what it can do, but by how reliably, quickly, and securely it does it.

6. **Failure Prevention**

- Ignoring non-functional requirements is a common reason for system failures during real-world usage (e.g., slow performance under load).

**Example:**

Let’s say you’re building a food delivery app.

**Functional requirements:**

- Users can browse restaurants, place orders, track delivery, and pay online.
- Delivery partners can see incoming orders and accept or reject them.

**Non-functional requirements:**

- The app must support **real-time tracking** with less than **3 seconds of delay.**
- The system must be **available 24/7 with minimal downtime.**
- The app should work on **Android, iOS, and web browsers.**
- Payments must be processed using **secure encryption protocols.**
- The backend should be **scalable** to handle traffic surges during lunch/dinner hours.

### CAP Theorem

#### What is the CAP Theorem?

The **CAP Theorem**, proposed by Eric Brewer in 2000 (and later formally proven by Gilbert and Lynch), stands for:

- C: Consistency
- A: Availability
- P: Partition Tolerance

It states that **in a distributed system, you can only achieve two out of the three guarantees at any given time**, but not all three simultaneously. This doesn't mean you can’t strive for all three, but in the presence of a network partition (which is inevitable in distributed systems), you must sacrifice either **Consistency or Availability.**

1. **C — Consistency**

**Definition:** Every read receives the most recent write or an error.

**Explanation:** Consistency means that all nodes in a distributed system see the same data at the same time. If a system is consistent, once a write is made to a data item, any subsequent read (from any node) will return that written value or nothing until it’s available. This is similar to the consistency model of traditional relational databases (like SQL databases), where ACID properties ensure that all clients see the same view of the data.

**Example:** If you update your profile picture on Facebook, and your friend sees the old picture when they view your profile from another region, that system is not consistent.

**Tradeoff:** To maintain consistency across nodes, the system might delay responses or reject requests (to make sure all replicas are updated before serving the data).

2. **A — Availability**

**Definition:** Every request (read or write) receives a (non-error) response, without guarantee that it contains the most recent write.

**Explanation:** Availability ensures that every request to the system gets a response—even if it’s not the most up-to-date. The system always remains operational. This is important for user-facing applications where downtime is unacceptable.

**Example:** Imagine a shopping cart system where you add an item. Even if one data center goes down, another still responds and allows you to keep shopping, even if your cart isn’t fully synced.

**Tradeoff:** To maintain high availability, the system may serve stale data (i.e., not the latest value). It sacrifices accuracy for uptime.

3. **P — Partition Tolerance**

**Definition:** The system continues to operate despite arbitrary message loss or failure of part of the system (i.e., a network partition).

**Explanation:** Partition tolerance means that even when communication between parts of the system fails (e.g., one data center can’t talk to another), the system continues to function. In distributed systems, network partitions are not just possible—they’re inevitable, so Partition Tolerance is a must. That means CAP really becomes a trade-off between C and A.

**Example:** If a network split happens between two data centers, and clients are connected to both, the system must decide: should it remain available (sacrifice consistency) or stay consistent (sacrifice availability)?

#### Combination Scenarios in CAP

Since you can't have all three in the event of a partition, systems generally choose one of these:

1. **CP (Consistency + Partition Tolerance)**

   - System stays consistent and can tolerate partitioning, but might become unavailable during failure.

   - Prioritizes correctness over availability.

   - **Examples:** MongoDB (in strict mode), HBase, Redis (when used as a CP store)

2. **AP (Availability + Partition Tolerance)**

   - System stays available and tolerates partitions, but may return stale or inconsistent data.
   - Prioritizes responsiveness over accuracy.
   - **Examples:** Cassandra, Couchbase, DynamoDB

3. **CA (Consistency + Availability)**
   - System is consistent and available only if no partitions exist (not tolerating network failures).
   - This is mostly theoretical in distributed systems since partitions will eventually occur.
   - More common in single-node or tightly-coupled systems, like SQL databases running on a single server.

#### Importance of CAP Theorem

CAP Theorem is vital because it **forces engineers to make conscious decisions** about tradeoffs in their system design. It helps you:

- Decide how to handle failures (availability vs correctness)
- Design for global scale (distributed across regions)
- Set realistic expectations for system behavior under stress or failure
- Prioritize user experience or data accuracy, depending on the domain

Without understanding CAP, you may build systems that behave unpredictably or fail silently under real-world conditions.

#### Why Do We Use CAP Theorem?

- To **design robust distributed systems** that are fault-tolerant.
- To **understand trade-offs** when choosing databases, communication protocols, or replication strategies.
- To guide **architectural decisions** when building systems that span across multiple servers, data centers, or geographies.
- To **define SLAs and user experience expectations** for consistency and availability.

#### Advantages of CAP-aware Design

- Builds **resilient, fault-tolerant systems**
- Improves **scalability and flexibility**
- Enables **fine-tuned user experience** (based on priority: data accuracy vs uptime)
- Helps you pick the right **tool or database** for the job

#### Disadvantages

- Forces you to **sacrifice** at least one desirable property
- May introduce **complexity** in understanding and handling data staleness or availability
- Increases **engineering effort** (to manually handle scenarios like eventual consistency)
- Can create **user confusion** if the system doesn’t behave predictably (especially in AP systems)

#### When to Use Which Part?

**Choose CP:**

- When **data correctness is critical**
- Domains: **Banking, inventory systems, financial ledgers**
- You’re okay with some downtime, but not incorrect data

**Choose AP:**

- When **high availability is critical**
- Domains: **Social media, messaging systems, caching layers**
- You’re okay with stale or eventually consistent data

**Choose CA:**

- In **centralized systems** where network partitioning isn’t a concern
- Domains: **Internal enterprise apps, single-node apps**
- You don't need partition tolerance (not common in distributed web-scale apps)

#### How CAP Solves System Design Problems

| Problem                           | CAP Component             | How it helps                                                   |
| --------------------------------- | ------------------------- | -------------------------------------------------------------- |
| Data loss during network failure  | P                         | System keeps working even if nodes can’t communicate           |
| System hangs under load           | A                         | Prioritizes responsiveness even under stress                   |
| Stale reads                       | C (or lack thereof in AP) | Shows need for stronger consistency if stale reads are harmful |
| Multiple conflicting writes       | C                         | Ensures only one correct version of data                       |
| Global replication across regions | P                         | Handles partitions due to geographic latency/failure           |

#### Where to Use CAP in System Design?

- **Database choice:** NoSQL vs SQL? Choose based on CAP priorities
- **Replication strategy:** Synchronous vs asynchronous
- **Consistency model:** Strong vs eventual consistency
- **Service architecture:** Microservices vs monoliths
- **Designing APIs:** Idempotent operations, retry strategies
- **Load balancers / failover strategies:** Which nodes to prefer when some are inconsistent?

#### How to Choose in System Design

Let’s go step by step:

- **Step 1: Accept Partition Tolerance**

Unless you're building **a single-machine system, Partition Tolerance (P)** is a must.
So the real choice becomes:
**CA**, **CP**, or **AP** — but **you must give up one** during a partition.

- **Step 2: Understand Your System’s Requirements**
  Ask these questions:
  |Question|If YES|If NO|
  |----|----|----|
  |Do users expect strict correctness (like banking)?|Prioritize Consistency|Consider Availability|
  |Can the system tolerate stale data temporarily?|Favor Availability|Choose Consistency|
  |Is global uptime more important than perfect accuracy?|Choose Availability|Lean toward Consistency|
  |Is the system user-facing with real-time requirements?|Lean toward Availability|Prefer Consistency|
  |Do you expect frequent or unpredictable network partitions?|You must design for Partition Tolerance||

- **Step 3: Match Use Case to a CAP Combination**

Here’s how common combinations apply:

1. **CP (Consistency + Partition Tolerance)**

   - Sacrifices: Availability
   - Guarantee: Always returns the correct data, even if some nodes are unreachable
   - Might reject requests or time out during partitions

   **When to Use:**

   - Banking systems
   - E-commerce checkouts
   - Inventory systems
   - Payment gateways

   **Examples:**

   - HBase
   - MongoDB (with majority write concern)
   - Google BigTable

2. **AP (Availability + Partition Tolerance)**

   - Sacrifices: Consistency
   - Guarantee: System remains responsive, even during partition
   - Data may be stale, but system stays up

   **When to Use:**

   - Social networks
   - Shopping catalogs
   - Messaging platforms
   - Content delivery (e.g., YouTube comments)

   **Examples:**

   - Couchbase
   - Cassandra
   - DynamoDB

3. **CA (Consistency + Availability)**

   - Sacrifices: Partition Tolerance
   - Only works in systems with no partition risk (e.g., single-node systems or tightly coupled clusters)

   **When to Use:**

   - Internal tools in a reliable LAN environment
   - Systems without horizontal scaling

   **Examples:**

   - Traditional relational databases (PostgreSQL, MySQL) on a single node

#### Real-World Use Case Mapping

| Use Case               | CAP Choice | Why?                                               |
| ---------------------- | ---------- | -------------------------------------------------- |
| Online banking         | CP         | Data must be consistent                            |
| Shopping cart          | CP or AP   | Depends on how critical the cart state is          |
| Social media feeds     | AP         | Freshness is less important than availability      |
| Real-time chat         | AP         | Stale messages okay temporarily                    |
| Airline ticket booking | CP         | Must avoid overbooking                             |
| DNS resolution         | AP         | Always available, even if not perfectly up-to-date |

#### Rule of Thumb

When in doubt: **Design for AP, and use domain-level strategies to approximate consistency.**
This is how Amazon, Facebook, and Netflix scale reliably at the cost of temporarily inconsistent data—**then resolve it later.**

#### Tips for Choosing CAP in Design

- For critical workflows: Use **CP systems **(or CP-mode of an AP system)
- For high read throughput: Use **AP systems** with **eventual consistency**
- For UX-heavy systems: Use **AP** but ensure **read-your-writes** for better perception
- For write-heavy systems: Watch for **conflict resolution needs in AP** systems
- For hybrid apps: Use **microservices with different CAP** profiles per service

### PACELC Theorem

#### What is PACELC Theorem?

While the CAP theorem helps us understand trade-offs in distributed systems during network partitions, it doesn't tell us what happens when the system is functioning normally (no partitions).

To solve this, Daniel Abadi introduced the PACELC Theorem in 2010 as an extension of CAP, making it more comprehensive and practical for real-world distributed systems.

**PACELC stands for:**

If there is a Partition (P), then a system must choose between Availability (A) and Consistency (C); Else (E), when the system is running normally, it must choose between Latency (L) and Consistency (C).

#### Breaking Down Each Letter

**1.** **Partition (P)**

- **Definition:** A network failure that prevents some nodes in the system from communicating with others.
- **Importance:** Partitions are inevitable in distributed systems due to network unreliability, data center outages, or geographic latency. PACELC starts with the same assumption as CAP: during a partition, you must trade off between Availability and Consistency.

**2.** **Availability (A)**

- **Definition:** The system continues to serve requests and respond to clients during a partition—even if it means returning outdated or incomplete data.
- **Explanation:** Highly available systems prioritize uptime and responsiveness, even if that means compromising on accuracy. During a partition, choosing Availability may mean some users see stale or inconsistent data.

**3.** **Consistency (C)**

- **Definition:** All users and nodes see the same, most recent version of data—whether during a partition or in normal operations.
- **Explanation:** Prioritizing consistency means ensuring that all replicas are up-to-date before serving reads or writes. It avoids anomalies like conflicting writes or stale reads.

**4.** **Else (E)**

This part introduces a new dimension: what does the system prioritize when there is no network partition?  
CAP doesn't consider this case at all, and that's PACELC's major upgrade.

**5.** **Latency (L)**

- **Definition:** The time it takes for the system to respond to a request.
- **Explanation:** Even without a partition, synchronizing all nodes can increase response time. Systems that prioritize latency will respond quickly, even if they sacrifice immediate consistency.

**6.** **Consistency (again)**

Here, it refers to the trade-off made in normal conditions. Some systems still choose to delay responses to guarantee consistency—even when the network is healthy.

#### Common PACELC Trade-off Patterns

Here's how systems are categorized based on PACELC:

| System                   | PACELC Model                    | Meaning                                                                            |
| ------------------------ | ------------------------------- | ---------------------------------------------------------------------------------- |
| Cassandra                | PA/EL                           | During partition: favors Availability. Else: favors Latency (eventual consistency) |
| Amazon DynamoDB          | PA/EL                           | Same as Cassandra                                                                  |
| MongoDB                  | PC/EC                           | During partition: favors Consistency. Else: favors Consistency                     |
| HBase                    | PC/EC                           | Strong consistency at all times                                                    |
| Cosmos DB (configurable) | Can be tuned to different modes | -                                                                                  |

#### Why Is PACELC Important?

The CAP theorem only applies when there's a network partition, but most of the time, distributed systems are not under partition. PACELC provides a more complete model by considering both failure and non-failure conditions:

- Helps understand trade-offs beyond just fault scenarios
- Useful for tuning distributed systems for performance or correctness
- Helps choose a database or architecture that aligns with business priorities
- Encourages designing systems that adapt to both normal and abnormal states

In other words, **CAP is a subset of PACELC**.

#### Why Do We Use PACELC?

PACELC is used in:

- Distributed database design: Helps pick replication strategies and consistency models
- Cloud systems: Guides decisions around geo-replication, latency targets, and failover behavior
- Microservice design: Determines how services communicate, synchronize state, and maintain data correctness
- Service Level Agreements (SLAs): Helps define uptime vs correctness guarantees
- Choosing between NoSQL vs NewSQL databases

PACELC helps teams engineer for reality, where failures may happen—but also where performance and latency still matter during normal operation.

#### Advantages of Using PACELC

- More realistic model than CAP
- Addresses latency vs consistency trade-offs even in healthy systems
- Encourages fine-tuned design for distributed applications
- Allows informed decision-making when choosing systems like Cassandra, MongoDB, or CosmosDB
- Gives architects a way to balance user experience vs system accuracy

#### Disadvantages of PACELC

- Complexity: More nuanced than CAP, harder for beginners to grasp
- Requires deep understanding of system internals to apply effectively
- May lead to over-optimization or premature tuning
- Difficult to implement dynamic switching between modes (e.g., EL to EC based on load)

#### When to Use Each Trade-Off?

#### PA/EL (Availability during Partition, Low Latency otherwise)

- **Use when:** User experience (speed and uptime) is more critical than strict consistency
- **Domains:** Social networks, real-time messaging apps, product search, recommendation engines
- **Examples:** Cassandra, DynamoDB

#### PC/EC (Consistency during Partition, Strong Consistency always)

- **Use when:** Data correctness is critical at all times, even if slower
- **Domains:** Banking, inventory management, e-commerce order processing, medical systems
- **Examples:** MongoDB (with write concern), HBase, Spanner

#### PA/EC or PC/EL

These are hybrid or configurable modes, where the trade-off depends on the use case  
Systems like Cosmos DB allow configurable levels of consistency (from eventual to strong)

#### What System Design Problems Does PACELC Help Solve?

| Problem                           | PACELC Factor | How It Helps                                                           |
| --------------------------------- | ------------- | ---------------------------------------------------------------------- |
| Slow response in normal operation | L             | Optimize for Latency over Consistency                                  |
| Inconsistent data under failure   | P & C         | Choose Consistency over Availability during partitions                 |
| Stale reads during normal state   | E & C         | Tune for stronger consistency (EC)                                     |
| High availability requirements    | A             | Choose Availability during partitions (PA)                             |
| Eventual consistency side effects | C             | Shift toward strong consistency model                                  |
| Global data replication           | E/L           | Pick replication strategies based on latency or correctness priorities |

#### Where to Apply PACELC in System Design?

PACELC helps you in the following system design areas:

- Database choice: SQL vs NoSQL vs NewSQL
- Replication model: Quorum-based vs Master-slave vs Leaderless
- Write/read strategies: Synchronous vs asynchronous replication
- Data sharding and geo-replication: Balancing latency with correctness
- API design: Whether to fail fast (for consistency) or retry (for availability)
- Consistency models: Eventual, strong, causal, session consistency, etc.

#### Use Case Examples

| Use Case / Need                            | Choose PACELC Trade-off      | Explanation                                                                                            |
| ------------------------------------------ | ---------------------------- | ------------------------------------------------------------------------------------------------------ |
| Financial transactions, banking            | CP + EC                      | Strong consistency always required, even if latency increases or availability drops during partitions. |
| Social media feeds, user-generated content | AP + EL                      | High availability and low latency prioritized, stale data acceptable temporarily.                      |
| E-commerce carts                           | AP + EL or CP + EC (tunable) | Availability to prevent cart loss, consistency needed at checkout, may tune per phase.                 |
| Real-time messaging (chat)                 | AP + EL                      | Fast delivery important, slight eventual consistency tolerable.                                        |
| IoT sensor data collection                 | AP + EL                      | Data ingestion prioritizes availability, consistency less strict.                                      |
| Inventory management / booking system      | CP + EC                      | Prevent double booking, must be consistent even if slower or less available during partition.          |
| Content Delivery Networks (CDNs)           | AP + EL                      | Prioritize latency and availability for user experience, stale content temporarily allowed.            |

#### Best Practices for PACELC in Modern Systems

1. **Identify Your Critical Consistency Points**

   - Understand exactly which operations must be consistent (e.g., payments) vs where eventual consistency is acceptable (e.g., user profiles).
   - Design different components or microservices with different PACELC trade-offs.

2. **Use Tunable Consistency Where Possible**

   - Modern databases (Cassandra, Cosmos DB) allow choosing consistency level per query.
   - Use strong consistency for critical writes; eventual consistency for reads or non-critical operations.

3. **Design for Graceful Degradation During Partitions**

   - In AP systems, design clients to handle stale data and resolve conflicts asynchronously.
   - In CP systems, provide clear user feedback if the system is temporarily unavailable.

4. **Optimize for Latency Without Sacrificing Critical Consistency**

   - Use caching, CDNs, and asynchronous replication to reduce latency in consistent systems.
   - Consider read-repair or conflict-free replicated data types (CRDTs) for smooth eventual consistency.

5. **Implement Monitoring and Alerting on Trade-offs**

   - Track latency, availability, consistency errors, and partitions in real-time.
   - Use metrics and SLAs to adjust system configuration dynamically.

6. **Prepare for Network Partitions**

   - Design retry strategies, circuit breakers, and fallback mechanisms.
   - Use distributed consensus protocols (e.g., Paxos, Raft) for CP systems.

7. **Communicate Trade-offs to Stakeholders**
   - Clearly explain the impact of CAP and PACELC choices on user experience and business goals.
   - Align consistency and availability choices with business risk tolerance.

#### How to Choose PACELC in System Design

**Step 1: Accept Partition Tolerance**

As in CAP, P is non-negotiable in distributed systems. That part remains fixed.

**Step 2: Choose A vs C — What to Sacrifice During Partition?**

| Prioritize Consistency (C) | Prioritize Availability (A) |
| -------------------------- | --------------------------- |
| Financial transactions     | Messaging apps              |
| Inventory systems          | Feed viewers (social apps)  |
| Booking/ticketing          | Real-time dashboards        |
| Strong business rules      | Media streaming             |

**Step 3: Choose L vs C — What to Sacrifice When Network is Healthy?**

| Prioritize Latency (L) | Prioritize Consistency (C)           |
| ---------------------- | ------------------------------------ |
| Low-latency UX needed  | Strong accuracy needed               |
| Read-heavy systems     | Write-heavy with coordination        |
| User-facing apps       | Complex workflows (banking, ledgers) |
| Shopping catalogs      | Order processing                     |

#### Tips to Apply PACELC in Design

1. **Start from business requirements**  
   Identify if latency, correctness, or availability is your highest priority.

2. **Design for failure first (PA vs PC)**  
   Assume partitions will happen — plan for them explicitly.

3. **Then focus on user experience under normal ops (EL vs EC)**  
   What will affect the end-user if consistency is delayed?

4. **Use database support for fine-tuned controls**  
   Choose databases like Cosmos DB, Cassandra, or MongoDB where consistency levels are configurable.

5. **Evaluate per service in microservices**  
   Not all services need the same PACELC strategy! Break it down per component.

### ACID vs BASE

#### What is ACID?

ACID is a set of properties that guarantee reliable processing of database transactions in relational databases. These properties ensure the database remains in a valid state, even in cases of power failure, crashes, or errors.

#### Breakdown of ACID Properties

**1. Atomicity**

- **Definition:** A transaction is all or nothing.
- **Explanation:** If one part of a transaction fails, the entire transaction fails and the database state is left unchanged.
- **Example:** In a money transfer, either both the debit and credit succeed, or neither does.

**2. Consistency**

- **Definition:** A transaction brings the database from one valid state to another.
- **Explanation:** Data must always follow all rules, constraints, triggers, and relationships.
- **Example:** You cannot end up with a negative bank balance if your system doesn't allow it.

**3. Isolation**

- **Definition:** Concurrent transactions don't interfere with each other.
- **Explanation:** The final outcome must be as if the transactions were executed sequentially.
- **Example:** Two users editing the same profile won't overwrite each other.

**4. Durability**

- **Definition:** Once a transaction is committed, it will persist, even if there's a crash.
- **Explanation:** Data is saved in non-volatile memory and survives system failure.
- **Example:** After hitting "submit," your order stays placed—even after a power outage.

#### What is BASE?

BASE is an alternative consistency model designed for distributed systems and NoSQL databases where scalability, availability, and fault tolerance are prioritized over strict consistency.

#### Breakdown of BASE Properties

**1. Basically Available**

- **Definition:** The system guarantees availability, meaning it will always respond—even if the response is a failure or stale.
- **Explanation:** During failures or high load, the system may degrade gracefully rather than become unavailable.

**2. Soft State**

- **Definition:** The system state may change even without new input.
- **Explanation:** Due to eventual consistency, intermediate states may exist temporarily as data propagates across nodes.

**3. Eventually Consistent**

- **Definition:** The system guarantees that, given enough time, all replicas will converge to the same state.
- **Explanation:** Immediate consistency is sacrificed for performance and availability.

#### ACID vs BASE (Comparison)

| Feature           | ACID (Relational DBs)                | BASE (Distributed Systems / NoSQL)      |
| ----------------- | ------------------------------------ | --------------------------------------- |
| Model Type        | Strict                               | Loosely consistent                      |
| Consistency       | Strong                               | Eventual                                |
| Availability      | Lower                                | Higher                                  |
| Performance       | Slower                               | Faster                                  |
| Use Case          | Banking, E-commerce, Enterprise apps | Social media, IoT, Streaming, Analytics |
| Failure Tolerance | Low (fails safely)                   | High (degrades gracefully)              |
| Example Systems   | MySQL, PostgreSQL, Oracle            | Cassandra, DynamoDB, Couchbase          |

#### ACID in Relational Databases

Relational databases like PostgreSQL, Oracle, and SQL Server implement ACID properties through:

- Transaction logs: To ensure atomicity and durability.
- Locks and latches: To ensure isolation.
- Constraints and triggers: To ensure consistency.

They are ideal when you need accuracy, integrity, and structured schemas—like in banking, inventory systems, ERP, or finance.

#### BASE in NoSQL & Distributed Systems

NoSQL databases like Cassandra, DynamoDB, and MongoDB follow BASE principles. They:

- Allow eventual consistency across replicas
- Use asynchronous replication
- Prefer availability and partition-tolerance (based on PACELC or CAP models)

They are used in big data, streaming services, real-time analytics, IoT, and social media platforms where scale and responsiveness matter more than perfect consistency.

#### Why Do We Use ACID or BASE?

**Use ACID when:**

- Data correctness is critical (e.g., finance, healthcare)
- Transactions must not lose or corrupt data
- You can afford a slight performance cost for accuracy

**Use BASE when:**

- Scalability, speed, and fault tolerance are more important
- Some degree of stale or inconsistent data is tolerable
- You operate in a distributed, high-throughput environment

#### Advantages and Disadvantages

#### ACID

**Advantages:**

- Guarantees data integrity
- Excellent for systems needing reliability
- Easier to reason about program logic

**Disadvantages:**

- Harder to scale horizontally
- Higher latency due to locking and isolation
- May become a bottleneck in high-concurrency systems

#### BASE

**Advantages:**

- High availability and scalability
- Resilient to failure
- Ideal for real-time, distributed workloads

**Disadvantages:**

- Inconsistent reads possible
- Conflict resolution is complex
- Harder to guarantee correctness

#### When to Use Which?

| Scenario             | ACID                      | BASE                                       |
| -------------------- | ------------------------- | ------------------------------------------ |
| Banking, payments    | ✅                        | ❌                                         |
| Social network feed  | ❌                        | ✅                                         |
| Inventory management | ✅                        | ❌ / partial BASE with conflict resolution |
| Messaging systems    | ❌ (if speed is priority) | ✅                                         |
| Order processing     | ✅ (must be accurate)     | ❌ (can cause issues)                      |
| Analytics and logs   | ❌                        | ✅                                         |

#### What Problem Does Each Solve?

- **ACID solves:** correctness, integrity, and transactional reliability
- **BASE solves:** availability, performance, and distributed data scaling

Each solves a different system design problem based on context.

#### Where to Use in System Design?

In system design interviews, ACID vs BASE informs your data layer decisions.

- Choose ACID for systems with strong correctness needs.
- Choose BASE for systems where high throughput, fault tolerance, and horizontal scaling are critical.

#### System Design Applications

**1. Data Modeling**

**ACID (Relational):**

- Schema-driven and normalized
- Strong data integrity using foreign keys, constraints
- Example: Banking system with tightly coupled tables

**BASE (NoSQL/Distributed):**

- Schema-less or denormalized
- Duplicate data acceptable for performance
- Example: Social media platform with duplicated post data

**2. Replication Strategies**

**ACID:**

- Synchronous replication
- Writes confirmed after all replicas updated
- Example: PostgreSQL synchronous replicas

**BASE:**

- Asynchronous replication
- Eventual consistency
- Example: Cassandra replication across regions

**3. Caching Layers**

**ACID:**

- Tight coordination with source of truth
- Requires cache invalidation logic

**BASE:**

- Loosely consistent with database
- Accepts stale cache data
- Example: Redis with eventual freshness

**4. Consistency Models**

**ACID:**

- Strong consistency
- Linearizability or serializability
- Example: Financial applications

**BASE:**

- Eventual consistency
- Tunable consistency levels
- Example: Recommendation engines

**5. Microservices Communication**

**ACID:**

- Distributed transactions (2PC)
- Tight coupling
- Example: Shared relational DB

**BASE:**

- Eventual consistency
- Asynchronous messaging
- Example: Event-driven architecture

#### How to Choose Between ACID and BASE

**1. Nature of the Application**

| Application Type          | Model to Choose | Why                               |
| ------------------------- | --------------- | --------------------------------- |
| Banking / Payments        | ACID            | Must guarantee correctness        |
| Social Media / News Feeds | BASE            | Prioritize speed and availability |
| E-commerce Checkout       | ACID            | Prevent revenue loss              |
| Product Search            | BASE            | High volume reads acceptable      |
| Healthcare Systems        | ACID            | Regulations demand integrity      |
| IoT Data Ingestion        | BASE            | Massive write throughput          |

**2. Consistency Requirements**

- **Strong, immediate consistency** → ACID
- **Eventual consistency is fine** → BASE

**3. Availability and Partition Tolerance (CAP Trade-Off)**

- **Availability over Consistency** → BASE
- **Consistency over Availability** → ACID

**4. Scalability Needs**

- **Vertical scaling** → ACID
- **Horizontal scaling** → BASE

**5. Latency Sensitivity**

- **Can tolerate delay** → ACID
- **Needs fast response** → BASE

#### Mixing ACID and BASE: Hybrid Approaches

Modern architectures often combine both:

- Use ACID for critical workflows (checkout, billing)
- Use BASE for scalable, user-facing parts (search, recommendations)

| Component             | ACID or BASE | Reason                         |
| --------------------- | ------------ | ------------------------------ |
| User account data     | ACID         | Identity and security critical |
| Product catalog       | BASE         | Tolerates eventual consistency |
| Shopping cart         | ACID         | Must reflect true state        |
| Recommendation engine | BASE         | Approximate and fast           |
| Order processing      | ACID         | No partial/inconsistent orders |

#### Final Rule of Thumb

- **If correctness > performance** → ACID
- **If speed, scale, and tolerance > strict consistency** → BASE

### Consistency Models

#### What Are Consistency Models?

A consistency model is a formal contract between the storage system and the application that specifies what values a read operation can return after a series of write operations. These models determine how consistent data appears to users across replicas in distributed environments.

The need arises from replication - when data is copied across multiple machines to improve:

- Fault tolerance
- Latency reduction
- Throughput improvement

#### Core Consistency Models

**1. Strong Consistency**
**Definition:**  
Ensures every read receives the most recent write for a given piece of data. Once a write is acknowledged, any subsequent read (from any node) will see that write.

**Example:**  
Bank account balance - a deposit is immediately visible to all subsequent requests.

**Use Cases:**

- Banking and payment systems
- Inventory management
- Authentication systems

| Pros                   | Cons                                |
| ---------------------- | ----------------------------------- |
| Simple mental model    | High latency                        |
| Guarantees correctness | Poor availability during partitions |
| Easy debugging         |                                     |

**2. Eventual Consistency**
**Definition:**  
Guarantees that if no new writes are made, eventually all accesses will return the last updated value, with no time guarantee.

**Example:**  
Social media posts may take time to propagate to all feeds.

**Use Cases:**

- Social media platforms
- DNS systems
- Content delivery networks (CDNs)

| Pros              | Cons                         |
| ----------------- | ---------------------------- |
| High availability | Stale reads possible         |
| Low latency       | Requires conflict resolution |
| Easy to scale     |                              |

**3. Causal Consistency**
**Definition:**  
Preserves causal relationships between operations while allowing concurrent, unrelated operations to be reordered.

**Example:**  
Comment and edit operations must appear in correct order.

**Use Cases:**

- Collaborative apps (Google Docs)
- Messaging systems
- Real-time multi-user editing

| Pros                                  | Cons                         |
| ------------------------------------- | ---------------------------- |
| Intuitive UX                          | Complex implementation       |
| Avoids eventual consistency anomalies | Requires dependency tracking |

**4. Read-Your-Writes Consistency**
**Definition:**  
Guarantees users always see their own writes, even if the system is eventually consistent for others.

**Example:**  
Profile picture updates are immediately visible to the user who changed them.

**Use Cases:**

- User dashboards
- Profile management
- Personal notifications

| Pros                            | Cons                   |
| ------------------------------- | ---------------------- |
| Improved UX                     | Limited to single user |
| Performance/correctness balance |                        |

#### Hybrid Approaches

Real-world systems often combine multiple models:

| System          | Approach                                      |
| --------------- | --------------------------------------------- |
| Amazon DynamoDB | Eventual by default, strong when needed       |
| Cassandra       | Configurable per-operation (QUORUM, ALL, ONE) |
| Firebase        | Eventual for sync + Read-your-writes for UI   |

#### Why Use Consistency Models?

- Define correctness expectations
- Design fault-tolerant replication
- Optimize performance vs correctness
- Ensure predictable user experience

#### Model Comparison

| Model            | Advantages                 | Disadvantages                         |
| ---------------- | -------------------------- | ------------------------------------- |
| Strong           | Predictable, safe          | High latency, poor availability       |
| Eventual         | Highly available, scalable | Stale data, needs conflict resolution |
| Causal           | Preserves logical order    | Complex implementation                |
| Read-Your-Writes | User-friendly              | Limited scope                         |

#### Use Case Recommendations

| Use Case           | Recommended Model          | Reason                 |
| ------------------ | -------------------------- | ---------------------- |
| Bank transactions  | Strong                     | Correctness critical   |
| Profile updates    | Read-your-writes           | User trust important   |
| Messaging apps     | Causal                     | Preserve message order |
| Social feeds       | Eventual                   | Throughput prioritized |
| E-commerce catalog | Eventual                   | Tolerable lag          |
| Cart/checkout      | Strong or Read-your-writes | Accuracy required      |

#### System Design Applications

Consistency models influence:

- Database selection (SQL vs NoSQL)
- Replication strategies
- Caching policies
- API response guarantees
- User session handling

#### Selection Guide

Ask these questions:

1. **Is correctness > availability?**  
   → Strong or Causal

2. **Can users tolerate stale data?**  
   → Eventual

3. **Need immediate feedback for user actions?**  
   → Read-your-writes

4. **Operations have causal relationships?**  
   → Causal

5. **Globally distributed system?**  
   → Eventual or Hybrid

6. **Concurrent writers?**  
   → Use CRDTs or quorum models

#### Implementation Considerations

- **Strong consistency:** Requires synchronous replication
- **Eventual consistency:** Needs conflict resolution (last-write-wins, vector clocks)
- **Causal consistency:** Requires dependency tracking
- **Read-your-writes:** Needs session affinity

#### Performance Tradeoffs

- Stronger consistency → Higher latency
- Weaker consistency → Better availability
- Hybrid approaches → More complex code paths

#### Popular Implementations

- **Strong:** PostgreSQL, MySQL (with proper configuration)
- **Eventual:** Cassandra, DynamoDB (default)
- **Causal:** MongoDB, Riak
- **Read-your-writes:** Firebase, session-based systems

### Scalability

#### What Is Scalability?

Scalability refers to a system's ability to handle increased workload gracefully by increasing resources. It's about efficiently, predictably, and cost-effectively managing growth while maintaining performance.

#### Two Major Types of Scalability

**1. Vertical Scaling (Scale-Up)**

**Definition:**  
Increases system capacity by upgrading hardware (CPU, RAM, storage) on a single machine.

**Pros:**

- Simpler implementation
- Fewer architectural changes needed
- Easier to maintain strong consistency
- Good for legacy systems

**Cons:**

- Hardware limitations
- Expensive high-end hardware
- Single point of failure
- Often requires downtime

**Best Use Cases:**

- Small to medium applications
- Databases requiring strong consistency
- Prototypes/MVPs with tight timelines

**2. Horizontal Scaling (Scale-Out)**

**Definition:**  
Increases capacity by adding more machines to a distributed system.

**Pros:**

- Virtually unlimited scalability
- Built-in fault tolerance
- Cost-effective with commodity hardware
- Enables distributed processing

**Cons:**

- Complex architecture
- Consistency challenges
- Higher operational overhead
- Network latency concerns

**Best Use Cases:**

- Large-scale systems (social media, e-commerce)
- Fault-tolerant architectures
- Stateless microservices

#### Comparison: Vertical vs Horizontal Scaling

| Aspect            | Vertical Scaling     | Horizontal Scaling         |
| ----------------- | -------------------- | -------------------------- |
| Scale Limit       | Hardware-constrained | Theoretically unlimited    |
| Cost              | Expensive upgrades   | Commodity hardware         |
| Downtime          | Often required       | Minimal if designed well   |
| Complexity        | Low                  | High (coordination needed) |
| Consistency       | Strong               | Requires compromise        |
| Typical Use Cases | Monoliths, SQL DBs   | Microservices, NoSQL       |

#### Importance of Scalability

Critical for:

- Maintaining user experience under load
- Ensuring system availability
- Optimizing costs
- Supporting business growth

#### Why We Need Scalability

- Handle growth without system rewrites
- Improve performance through load distribution
- Maintain reliability and uptime
- Optimize cloud costs
- Ensure fault tolerance

#### Advantages & Disadvantages

**Advantages:**

- Future-proofs your system
- Maintains performance under load
- Improves fault tolerance (horizontal)
- Provides operational flexibility

**Disadvantages:**

- Increases complexity (especially horizontal)
- Higher initial costs (vertical)
- Harder debugging in distributed systems
- Data consistency challenges

#### When to Use Each Scaling Type

| Scenario                          | Recommended Approach     |
| --------------------------------- | ------------------------ |
| Growing database with low traffic | Vertical                 |
| Global user base, real-time feeds | Horizontal               |
| Startup MVP                       | Vertical (simple/cheap)  |
| Multi-tenant SaaS platform        | Horizontal               |
| Read-heavy applications           | Horizontal + replication |

#### Where to Apply Scalability

Consider scaling at every architectural layer:

- **Application servers:** Horizontal replication
- **Database:** Read replicas, sharding
- **Cache:** Distributed clusters
- **File storage:** Object stores (S3)
- **Queue systems:** Kafka/RabbitMQ
- **Load balancing:** Across nodes

#### Hybrid Scaling Approach

Most production systems combine both strategies:

**When to Use Hybrid:**

- Start vertical, evolve to horizontal
- Vertical for DBs, horizontal for stateless services
- Cloud-native implementations

**Pros:**

- Flexibility per layer
- Cost optimization
- Staged growth

**Cons:**

- Complex management
- Monitoring challenges
- Requires broader infrastructure knowledge

#### Choosing the Right Model

Key questions to ask:

1. Will the system need massive scale?
2. Is latency or availability more critical?
3. Can your team handle distributed complexity?
4. Prioritizing launch speed or future-proofing?

**Rule of thumb:** Start simple with vertical scaling, then evolve to horizontal as needed.

#### Scalability Decision Tree

1. **Is your system experiencing performance issues under load?**

   - No → Monitor & optimize
   - Yes → Continue

2. **Can workload be split across machines?**

   - Yes → Go to 4
   - No → Go to 3

3. **Can hardware be upgraded?**

   - Yes → ✅ Vertical Scaling
   - No → ⚠️ Refactor needed

4. **Need high availability/failover?**

   - Yes → ✅ Horizontal Scaling
   - No → Continue

5. **Latency-sensitive with global users?**

   - Yes → ✅ Horizontal + CDNs
   - No → Continue

6. **Immediate scaling needs but centralized?**

   - Yes → ✅ Vertical (short-term), plan Hybrid
   - No → ✅ Horizontal if possible

7. **Both app and DB under pressure?**

   - Yes → ✅ Hybrid Scaling
   - No → Scale pressured layer

8. **Have resources for distributed complexity?**
   - Yes → ✅ Horizontal/Hybrid
   - No → ⚠️ Start Vertical, plan Horizontal

#### Summary of Outcomes

| Scenario                    | Approach                        |
| --------------------------- | ------------------------------- |
| Simple bottleneck           | Vertical Scaling                |
| Partitionable, high traffic | Horizontal Scaling              |
| Mixed app & DB pressure     | Hybrid Scaling                  |
| Limited resources           | Vertical first, plan Horizontal |

### Latency vs Throughput

#### What is Latency?

Latency refers to the time it takes for a request to travel from the client to the system, get processed, and for the response to come back. It’s measured in units of time (like milliseconds).

In simpler terms, latency measures the delay in response—how long the user waits after clicking a button or hitting an endpoint.

**Example:**  
If a user clicks "Buy Now" and the confirmation takes 2 seconds to appear, that’s a **2-second latency**. High latency leads to sluggish experiences, critical in real-time applications like online gaming, video calls, or trading platforms.

#### What is Throughput?

Throughput refers to how many requests a system can handle per unit of time, typically measured as **requests per second (RPS)**. It reflects capacity—how much work your system can do in a given timeframe.

**Example:**  
An API server that handles **10,000 requests per second** has high throughput. It’s key in systems like batch processors, video streaming services, or large-scale web apps where request volume is massive.

#### Latency vs Throughput: The Trade-off

- **Latency** is about **speed per operation**.
- **Throughput** is about **volume over time**.

Optimizing one often affects the other. Lowering latency (making things faster per user) can reduce the total number of requests you can handle (throughput), and vice versa. This trade-off becomes a critical design decision based on use case.

#### Why Are They Important in System Design?

Understanding latency and throughput is fundamental to building **scalable, responsive systems**.

A system with:  
✔ **Low latency but low throughput** → Feels snappy but fails under high load.  
✔ **High throughput but high latency** → Handles heavy traffic but delivers poor UX.

**Choosing the right balance ensures:**

- Better user experience
- High availability
- Efficient resource usage
- Proper load distribution

---

#### Advantages & Disadvantages

| **Metric**     | **Advantages**                              | **Disadvantages**                          |
| -------------- | ------------------------------------------- | ------------------------------------------ |
| **Latency**    | Better UX, responsive apps                  | Hard to maintain under load, needs caching |
| **Throughput** | Handles more load, efficient resource usage | May increase latency if not optimized      |

#### When to Focus on Latency vs Throughput?

| **Use Case**                         | **Focus On** |
| ------------------------------------ | ------------ |
| Real-time communication (VoIP, Chat) | Latency      |
| E-commerce checkout                  | Latency      |
| Bulk data import                     | Throughput   |
| Video streaming (CDN delivery)       | Both         |
| High-frequency trading               | Latency      |
| Big data processing                  | Throughput   |

#### Where to Use It in System Design

- **API Gateway** → Optimize for **low latency** to reduce request overhead.
- **Database Layer** → Tune indexes for **latency**, scale shards for **throughput**.
- **Load Balancer** → Spread requests for **higher throughput**, reduce latency spikes.
- **Caching (Redis, CDN)** → Reduces **latency**, increases effective **throughput**.
- **Queues (Kafka, RabbitMQ)** → Designed for **throughput**, with possible latency trade-offs.

#### How to Choose Which to Optimize

- **Are users experiencing delays?** → Optimize **latency**.
- **Is the system crashing under load?** → Optimize **throughput**.
- **Both happening?** → Need **scalable architecture** (horizontal scaling, caching, async patterns).

#### How to Optimize for Latency

✔ Use **in-memory caches** (Redis, Memcached)  
✔ Deploy **CDNs for static assets**  
✔ **Reduce round trips** (batch requests, compress data)  
✔ Optimize **algorithms, DB indexes, queries**  
✔ Use **edge computing or multi-region deployments**

#### How to Optimize for Throughput

✔ Use **load balancers** to distribute traffic  
✔ **Scale horizontally** (add more machines)  
✔ Use **asynchronous processing** (message queues)  
✔ Apply **sharding & partitioning** in DBs  
✔ Optimize **thread pools & connection pooling**

#### Hybrid Considerations

Modern systems optimize **both** using hybrid designs:

- **Caching + async queues** → Reduces latency while increasing throughput.
- **CDN + sharded backend** → Fast reads + distributed scale.
- **DB read replicas** → Scale read throughput while maintaining acceptable latency.

#### Summary: Key Questions to Ask

- **Do you need instant responses?** → Focus on **latency**.
- **Are you processing tons of data per second?** → Focus on **throughput**.
- **Can users tolerate delay for high volume?** → Prioritize **throughput**.
- **Is it a user-facing app with heavy load?** → Optimize **both**.

### Load Estimation

#### What is Load Estimation?

Load Estimation is the process of predicting the expected operational demand on a system. It includes calculating metrics like:

- **Queries Per Second (QPS):** Database-level reads/writes per second
- **Requests Per Second (RPS):** API or web-level incoming HTTP calls
- **Storage Needs Estimation:** Projected volume of data stored over time

This process helps you anticipate how your system will behave under load, both at present and as it grows.

#### Breaking Down the Components

**1. Queries Per Second (QPS)**

Refers to how many database operations are performed each second—like selects, inserts, updates.  
**Why it matters:**

- Sizing your DB engine
- Optimizing indexes
- Planning read/write replicas

**2. Requests Per Second (RPS)**

Measures how many HTTP requests (or service calls) your system handles per second.  
**Why it matters:**

- Scaling application servers
- Configuring load balancers
- Frontend caching strategies

**3. Storage Needs Estimation**

Focuses on how much disk/data storage your application will require.  
**Includes:**

- Raw user data
- Logs, backups, caches
- Analytic aggregates

**Why it matters:**

- Deciding disk capacity
- Database sharding
- Object storage (like S3) planning

#### Why Load Estimation is Important

Load estimation directly informs system architecture and scalability planning. Without it, you may:

- Overprovision resources (wasting money)
- Underprovision and risk downtime/poor UX
- Fail to plan for scaling, caching, or disaster recovery

**Key Benefit:** Keeps your system **cost-effective, reliable, and performant**.

#### Advantages vs Disadvantages

**Advantages**

| **Benefit**               | **Why It Matters**                    |
| ------------------------- | ------------------------------------- |
| Prevents system overload  | Avoid crashes during traffic spikes   |
| Enables capacity planning | Save costs by scaling gradually       |
| Improves response time    | Helps design for latency/throughput   |
| Aligns with SLAs          | Keeps service levels within contracts |

**Disadvantages/Pitfalls**

- Requires guesswork for early-stage products
- Inaccurate forecasts → mis-provisioning
- Risk of over-engineering for hypothetical loads
- Needs constant re-estimation as usage grows

**Pro Tip:** Even an approximate estimate is better than none!

#### When and Where to Use Load Estimation

| **Scenario**                    | **Application**                          |
| ------------------------------- | ---------------------------------------- |
| Before designing architecture   | Monolith vs microservices, DB choice     |
| Scaling vertically/horizontally | Sizing machines, threads, containers     |
| Choosing caching strategies     | High QPS? Add Redis/Memcached            |
| Planning storage solutions      | TBs of data? Plan S3, retention policies |
| Setting SLAs & autoscaling      | Define latency/failure thresholds        |

#### What Problems Does Load Estimation Solve?

| **Problem**                      | **Solution via Load Estimation**       |
| -------------------------------- | -------------------------------------- |
| App crashes during traffic surge | Estimate RPS → autoscale instances     |
| Slow DB reads                    | Estimate QPS → add read replicas/cache |
| Running out of storage           | Estimate growth → size disks/buckets   |
| Laggy UX                         | Match workload to server capacity      |

#### Step-by-Step Load Estimation Approach

**Step 1: Define Core Metrics**

- Users per day
- Actions per user (e.g., likes, searches)
- API calls per action
- **Calculate:** `RPS = (Users × Actions × API Calls) / 86,400`

**Step 2: Peak vs Average Load**

- Plan for **peak load** (e.g., Black Friday)
- Add buffer (e.g., **3x peak**)

**Step 3: Storage Estimation**

- Avg size per record (e.g., 1KB/message)
- Records per user per month
- Add **10-30%** for logs/metadata

**Step 4: Model Growth Scenarios**

- Simulate **1x, 10x, 100x** growth
- Identify bottlenecks: compute, bandwidth, storage

**Step 5: Monitor & Refine**

- Use **Prometheus, Grafana, CloudWatch**
- Continuously adjust estimates with real data

#### Interaction Between QPS, RPS & Storage

**Example Cascade:**  
`1M RPS → 100K QPS → 500GB/month storage`  
**Design each layer accordingly:**  
Frontend → Backend → DB → Storage → Monitoring

#### Proactive vs Reactive Estimation

| **Approach** | **Description**                 | **Example**                     |
| ------------ | ------------------------------- | ------------------------------- |
| Proactive    | Estimate based on specs + usage | 10K users/day, 5MB uploads/user |
| Reactive     | Use real metrics post-launch    | Logs show 5 RPS at peak         |

**Best Practice:** Start proactive, refine reactively.

#### Key Takeaways

- Load estimation drives **smart system design**
- Impacts **storage, DB choice, scaling, caching**
- Always estimate **RPS, QPS, and data growth**
- Continuously **monitor and iterate**
- Design for **growth**, not just current load

#### How to Calculate Each Component

**1. Requests Per Second (RPS)**

**Formula:**  
RPS = (Daily Active Users × Avg Requests per User) / 86,400

**Example:**  
100,000 users × 50 requests/day → **~58 RPS**

**2. Queries Per Second (QPS)**

**Formula:**  
QPS = RPS × Avg DB Queries per Request

**Example:**  
58 RPS × 3 DB queries → **174 QPS**  
_(Tip: Separate read/write QPS!)_

**3. Storage Estimation**

**Formula:**  
Daily Storage = (Objects/Day × Avg Size)
Monthly Storage = Daily × 30 + 20-30% buffer

**Example:**  
100K users × 3 photos/day × 2MB → **600GB/day → 18TB/month**

#### Summary Checklist

| **Component** | **Calculation**                        |
| ------------- | -------------------------------------- |
| RPS           | (Users × Actions × API Calls) / 86,400 |
| QPS           | RPS × Avg DB Queries per Request       |
| Storage       | Objects/day × Size × Time × Buffer     |
| Network       | RPS × Avg Response Size × 8 (bits)     |

### Availability, Reliability, Durability

#### Availability

Availability is the measure of a system’s readiness to deliver its intended service at any given moment. It tells us how often a system is up and running.

**Example**: If an e-commerce site is not reachable due to server downtime, it's experiencing availability issues — regardless of whether its database or logic is working fine.

#### Formula

`Availability = Uptime / (Uptime + Downtime)`

Typically expressed as a percentage over time (monthly or yearly).

**Common industry targets**:

| Availability %         | Downtime/year  |
| ---------------------- | -------------- |
| 99.0%                  | ~3.65 days     |
| 99.9% ("three nines")  | ~8.76 hours    |
| 99.99%                 | ~52.56 minutes |
| 99.999% ("five nines") | ~5.26 minutes  |

#### Metrics

- Uptime monitoring
- MTTR (Mean Time To Recovery)
- Downtime duration/frequency

#### How to Achieve High Availability

- Load balancing (across zones/servers)
- Auto-healing infrastructure (e.g., Kubernetes)
- Failover systems (active-passive or active-active)
- Redundant instances, zones, and regions
- Health checks and graceful degradation

#### Design Tradeoffs

- High availability increases cost and complexity
- May sacrifice consistency (CAP Theorem)

---

#### Reliability

Reliability measures the consistency and correctness of a system's performance over time — that it does what it’s supposed to do, without errors or failure.

A reliable system won’t crash frequently, misbehave randomly, or corrupt data over time.

#### Formula (Typical Metrics)

`MTBF (Mean Time Between Failures) = Total Uptime / Number of Failures`

Other supporting metrics:

- Error rate
- Service degradation frequency
- Fault tolerance thresholds

#### How to Achieve Reliability

- Retry logic with exponential backoff
- Circuit breakers and rate limiters
- Redundant subsystems
- Automated testing and chaos engineering
- Idempotent APIs and graceful error handling

#### Design Tradeoffs

- Can result in slower responses (e.g., retry logic)
- May require deeper operational complexity and alerting

---

#### Durability

Durability ensures that data is not lost once it's acknowledged as saved — even in the event of crashes, power loss, or hardware failure.

It’s about long-term data survival, not short-term access.

#### Metric Approaches

No single formula, but often expressed as:

- % data retained over time (e.g., 99.999999999% durability for S3)
- Backup frequency and restore success rate

#### How to Achieve Durability

- Write-ahead logging (WAL)
- Data replication (multi-disk, multi-zone, multi-region)
- Regular snapshots and backups
- RAID storage, distributed file systems (e.g., HDFS, Ceph)
- Consensus protocols (Paxos, Raft)

#### Design Tradeoffs

- Often more costly (storage, replication)
- May increase write latency
- Requires operational processes for backup/restore verification

---

#### Combining All Three: The Reliability Triad

| Property     | Focus             | Key Risk Reduced |
| ------------ | ----------------- | ---------------- |
| Availability | Uptime            | Outage           |
| Reliability  | Consistency       | Errors & crashes |
| Durability   | Data Preservation | Data loss        |

These three are closely related. A real-world system needs all three but often emphasizes them based on specific use cases.

#### Example Mix

**Banking App**:

- Availability: Must be online 24/7
- Reliability: Transactions must be 100% correct
- Durability: Every transaction must be stored safely forever

**Streaming Service (e.g., Netflix)**:

- Availability: Very high to keep users watching
- Reliability: Video playback must not fail
- Durability: Can tolerate some loss (e.g., cache miss) — so it's lower priority

---

#### Importance in System Design

These three properties are central to building:

- Highly scalable systems
- SLA/SLO/SLI compliant systems
- Distributed systems that work across data centers and zones

They guide design decisions about:

- Redundancy
- Replication
- Backup strategies
- Error handling
- Deployment topologies

---

#### Calculations Summary

#### Availability

`= (Uptime) / (Uptime + Downtime)`

e.g., 364 days up, 1 day down → 364 / 365 ≈ 99.73%

#### Reliability

`
= 1 - (Number of failures / Total ops)`

`= Measured via MTBF: Mean Time Between Failures
`

#### Durability

No exact formula, but:

- Based on number of successful vs. failed data retention events
- % durability offered by storage systems (e.g., Amazon S3: 11 9's)

---

#### When to Use Each & Where in System Design

| Layer/Component      | Focus                        |
| -------------------- | ---------------------------- |
| Load balancers       | Availability                 |
| Retry mechanisms     | Reliability                  |
| Database replication | Durability                   |
| Health checks        | Availability                 |
| Distributed cache    | Often available, not durable |
| Backups              | Durability                   |

---

#### Advantages & Disadvantages

| Feature      | Advantages                         | Disadvantages                       |
| ------------ | ---------------------------------- | ----------------------------------- |
| Availability | Happy users, no downtime           | High infra cost, complex failovers  |
| Reliability  | Trustworthy experience, fewer bugs | Slower under retry-heavy conditions |
| Durability   | Data safety, legal compliance      | Slower writes, high storage costs   |

---

#### Design Guidelines & Tips

- Prioritize availability in real-time apps, user-facing services
- Prioritize reliability in APIs, payment processing, infrastructure
- Prioritize durability in data stores, analytics pipelines

**Important**: Often, you can't maximize all three simultaneously. Trade-offs are key.

---

#### Achieving These in Practice

| Strategy                              | What It Improves               |
| ------------------------------------- | ------------------------------ |
| Multi-region deployment               | Availability & Durability      |
| Redundant components (HA)             | Availability                   |
| Retry + backoff + circuit breakers    | Reliability                    |
| Quorum-based replication (Raft)       | Durability & Reliability       |
| Snapshots + backups + versioning      | Durability                     |
| Observability (logs, alerts, tracing) | All 3 via proactive monitoring |

---

#### Conclusion: Choosing What to Prioritize

| App Type          | Availability | Reliability | Durability |
| ----------------- | ------------ | ----------- | ---------- |
| E-commerce        | ✅✅✅       | ✅✅✅      | ✅✅✅     |
| Social Media Feed | ✅✅✅       | ✅✅        | ✅         |
| Video Streaming   | ✅✅✅       | ✅✅        | ✅         |
| Banking App       | ✅✅✅       | ✅✅✅      | ✅✅✅     |
| Analytics Jobs    | ✅           | ✅✅        | ✅✅✅     |

### Performance Bottlenecks

#### What Are Performance Bottlenecks?

A performance bottleneck is any component in a system that limits the overall throughput, responsiveness, or scalability of the application. It's the slowest or most overloaded part of your system, and it affects the entire system's ability to perform efficiently.

**Analogy**: Think of a system like a pipeline — even if 9 out of 10 pipes are wide, one narrow pipe limits the total flow. That narrow pipe is your bottleneck.

#### Types of Performance Bottlenecks

**1. CPU Bottlenecks**

**Definition**: Occurs when the processor is maxed out and cannot keep up with the incoming workload.

**Symptoms**:

- High CPU usage (near 100%)
- Slow computation or request handling
- Thread contention or process starvation

**Typical Causes**:

- Inefficient algorithms or tight loops
- Single-threaded operations in a multi-core system
- Lack of parallelism
- Blocking operations on CPU-bound tasks

**How to Resolve**:

- Optimize algorithms (e.g., Big-O complexity)
- Use concurrency and parallelism (multithreading, async)
- Offload to GPUs or specialized hardware (e.g., SIMD)
- Use caching to avoid recomputation

**2. I/O Bottlenecks**

**Definition**: Arises when input/output operations (disk, file systems, etc.) slow down the system.

**Symptoms**:

- Slow disk reads/writes
- Delayed log file processing
- Thread blocking on file access
- High latency in data retrieval

**Typical Causes**:

- Synchronous blocking I/O operations
- Too many write operations (e.g., logging)
- Poor disk performance or high seek times

**How to Resolve**:

- Use asynchronous I/O
- Use SSDs instead of HDDs
- Batch I/O operations (write less often, in bulk)
- Minimize logging or use log aggregation systems

**3. Network Bottlenecks**

**Definition**: Occurs when the network is congested or has insufficient bandwidth to handle data transmission.

**Symptoms**:

- High latency between services
- Timeouts and dropped packets
- Throttling by external APIs
- Low throughput despite available CPU

**Typical Causes**:

- Large payloads (uncompressed JSON, images)
- Too many synchronous API calls
- Inefficient communication protocols (e.g., HTTP/1.1 instead of gRPC)
- Network congestion or poor routing

**How to Resolve**:

- Use compression (gzip, Brotli)
- Switch to binary or efficient protocols (gRPC, Protobuf)
- Implement batching and aggregation
- Use CDNs for static assets
- Move services closer (e.g., edge computing)

**4. Database Bottlenecks**

**Definition**: Happens when database read/write performance lags behind request demand.

**Symptoms**:

- Slow queries and high query latency
- Locking, deadlocks, or timeouts
- Long-running transactions
- High CPU or memory usage in DB server

**Typical Causes**:

- Poor indexing or unoptimized queries
- High volume of reads/writes without caching
- Monolithic DB design (single instance serving all traffic)
- Too many joins or unnormalized data

**How to Resolve**:

- Add proper indexes, optimize queries (use EXPLAIN plans)
- Introduce caching layers (Redis, Memcached)
- Use read replicas or sharding
- Use denormalization where needed
- Offload analytics to data warehouses

#### Mix of All Bottlenecks in Real Systems

In real-world distributed systems, bottlenecks are often interdependent. For example:

- A CPU bottleneck in a service causes slower processing → leads to longer open network connections → triggers a network bottleneck.
- Slow DB queries delay responses → causes threads to queue up → creating a CPU bottleneck due to context switching.

**Identifying and fixing just one layer without understanding the others can lead to partial fixes or new problems elsewhere.**

#### Importance of Identifying Performance Bottlenecks

Performance bottlenecks are critical to:

- **System Scalability**: Bottlenecks restrict horizontal scaling (adding more instances won't help if the DB is slow)
- **User Experience**: Latency and downtime directly hurt the end-user experience
- **Resource Utilization**: Bottlenecks lead to under-utilization or overuse of infrastructure
- **Cost Optimization**: Fixing bottlenecks often reduces cloud costs — fewer instances, faster responses

#### Why Do We Analyze Bottlenecks?

We use performance bottleneck analysis to:

- Improve throughput and latency
- Meet SLAs/SLOs
- Design for scale and fault tolerance
- Plan capacity and provisioning
- Prioritize optimization efforts (not all slowdowns matter equally)

#### Advantages and Disadvantages

| Aspect              | Advantages                                 | Disadvantages                            |
| ------------------- | ------------------------------------------ | ---------------------------------------- |
| Performance tuning  | Improves scalability and user satisfaction | Can be time-consuming and complex        |
| Bottleneck analysis | Helps localize root cause of slowdowns     | May need deep instrumentation            |
| Optimization        | Can reduce cost and infra requirements     | May introduce complexity (e.g., caching) |

#### When to Analyze Which Bottleneck?

| Scenario                       | Likely Bottleneck        |
| ------------------------------ | ------------------------ |
| Slow API response              | CPU, DB, Network         |
| Slow startup or background job | Disk I/O, CPU            |
| Dropped requests under load    | CPU, Network, Threadpool |
| High DB load                   | DB, I/O                  |
| Long upload/download times     | Network, Disk I/O        |

**Use observability tools like**:

- APM: Datadog, New Relic
- Tracing: Jaeger, OpenTelemetry
- Profilers: Flame graphs, CPU profilers
- Logs & metrics: Prometheus + Grafana, ELK stack

#### Where in System Design Do Bottlenecks Appear?

| System Layer       | Bottleneck Type    |
| ------------------ | ------------------ |
| Frontend (browser) | Network, Rendering |
| Backend API        | CPU, DB, Network   |
| Microservices      | Network, CPU       |
| Databases          | Disk I/O, Memory   |
| Caches             | Network, Memory    |
| Batch processing   | I/O, CPU           |

#### How to Resolve Performance Bottlenecks

**Step-by-step Process:**

1. **Measure**: Use profiling, logging, tracing to identify where time/resources are spent
2. **Isolate**: Localize the layer or component causing delays
3. **Benchmark**: Compare against expected performance
4. **Optimize**: Apply known solutions (caching, compression, load balancing)
5. **Scale**: Add replicas, scale horizontally or vertically
6. **Re-test**: Ensure the bottleneck is removed and no new one appears

#### Optimization Techniques:

- Load balancing
- Query optimization
- Async processing (queues)
- Data partitioning/sharding
- CDN for static content
- Autoscaling
- Rate limiting and backpressure

#### Summary: Choosing the Right Focus

| Bottleneck | Impact Area             | Tooling                 | Fix Examples                   |
| ---------- | ----------------------- | ----------------------- | ------------------------------ |
| CPU        | Processing time         | Profiler, Tracer        | Optimize code, add threads     |
| I/O        | Latency in reads/writes | Disk metrics, Traces    | Async I/O, SSDs                |
| Network    | Latency & throughput    | Packet captures, Logs   | Compression, batching, CDN     |
| Database   | Latency, app errors     | Query Profiler, Slowlog | Indexing, caching, replication |

### Monolith vs Microservices vs Serverless

- **Characteristics, advantages, challenges**

---

## 2. Networking Basics & OS Concepts

- **DNS, IP, Ports**

  - How DNS resolves domain names to IP addresses
  - IPv4 vs IPv6
  - Common port usages

- **HTTP/HTTPS, REST, gRPC**

  - Protocol differences and use cases
  - Statelessness of REST
  - Advantages of gRPC (performance, contracts)

- **TCP vs UDP**

  - Connection-oriented vs connectionless
  - Use cases for each

- **Sockets, Threads, Processes Basics**

  - OS networking fundamentals

- **WebSockets, Long Polling, SSE**

  - Real-time communication techniques

- **SSL/TLS and Secure Communication**

  - Encryption basics
  - Handshake process
  - Certificate Pinning

- **CDN Basics**

  - How CDNs cache and deliver content globally

- **Anycast, GeoDNS**

  - Techniques for global load balancing and routing

- **Load Balancing Concepts**

  - L4 (Transport Layer) vs L7 (Application Layer)
  - Sticky sessions, failover, health checks

- **Reverse Proxy**
  - Role in request routing and security (Nginx, HAProxy)

---

## 3. Design Patterns and Architectures

- **Client-Server Architecture**

  - Basics and examples

- **Microservices Architecture**

  - Design principles, pros/cons

- **Service-Oriented Architecture (SOA)**

  - Differences from microservices

- **Event-Driven Architecture**

  - Event producers/consumers, asynchronous flow

- **Layered Architecture (3-tier, N-tier)**

  - Presentation, business logic, data layers

- **API Gateway Pattern**

  - Single entry point, routing, rate limiting

- **Circuit Breaker Pattern**

  - Prevent cascading failures

- **Backpressure Pattern**

  - Handling load spikes gracefully

- **Sidecar Pattern (Service Mesh)**

  - Service proxy for observability, security

- **Command Query Responsibility Segregation (CQRS)**

  - Separating read and write models

- **Saga Pattern**

  - Managing distributed transactions

- **Service Discovery**

  - Dynamic discovery of service instances

- **Retry, Timeout Patterns**
  - Ensuring resilience and responsiveness

---

## 4. Data Modeling and Storage Systems

- **Relational Databases**

  - Schema design, normalization, indexing

- **NoSQL Databases**

  - Document, Key-Value, Wide-column, Graph
  - Use cases and trade-offs

- **Key-Value Stores**

  - In-memory caching, session storage

- **Wide-column Stores**

  - Scalability with column families

- **Time-Series Databases**

  - Specialized for time-stamped data

- **Graph Databases**

  - Relationships and traversal

- **Sharding and Partitioning Strategies**

  - Range, Hash, Directory-based, Geo

- **Data Replication**

  - Synchronous vs asynchronous
  - Master-slave, multi-master setups

- **Read/Write Patterns**

  - Read replicas, write scaling

- **Indexing**

  - B-tree, hash, inverted index

- **Data Consistency Models**

  - Strong, Eventual, Causal consistency

- **Data Modeling: Normalization vs Denormalization**

  - Trade-offs for performance vs data integrity

- **Storage Types**

  - Block, file, object storage (S3, HDFS)

- **Storage Tiers**

  - Hot, warm, cold data storage

- **Data Deduplication and Compression**

---

## 5. Caching Systems

- **Why Cache?**

  - Reducing latency, offloading DBs

- **What to Cache?**

  - Database query results, session data, static assets

- **Cache Invalidation Strategies**

  - Write-through, write-around, write-back

- **TTL (Time To Live)**

- **Eviction Policies**

  - LRU, LFU, FIFO

- **Cache Stampede Problem**

  - Causes and mitigation (locking, early recomputation)

- **Redis and Memcached**

  - Use cases, data structures, performance considerations

- **Local Cache vs Global Cache**

  - Client-side vs distributed cache

- **CDN as Cache**

---

## 6. Load Balancing

- **Types of Load Balancing**

  - Round-robin, Least connections, IP hashing

- **Load Balancer vs Reverse Proxy**

- **Global Load Balancing**

  - GeoDNS, Anycast routing

- **Health Checks and Failover**

- **Sticky Sessions**

- **Load Balancing at Layers**
  - L4 (TCP), L7 (HTTP)

---

## 7. Message Queues & Stream Processing

- **Message Brokers**

  - Kafka, RabbitMQ, AWS SQS

- **Pub/Sub vs Message Queues**

- **Ordered vs Unordered Queues**

- **Delivery Guarantees**

  - At-most-once, At-least-once, Exactly-once

- **Dead Letter Queues**

- **Eventual Consistency Using Messaging**

- **Stream Processing**

  - Kafka Streams, Apache Flink, Spark Streaming

- **Consumer Groups**

- **Retry and Backoff Mechanisms**

---

## 8. Distributed Systems Principles

- **Distributed Consensus**

  - Paxos, Raft protocols

- **Leader Election**

  - Algorithms and tools (Zookeeper, Etcd)

- **Heartbeats and Gossip Protocol**

- **Clock Synchronization**

  - NTP, Logical Clocks, Lamport Timestamps

- **Quorum-Based Writes**

- **Vector Clocks**

- **Split Brain Problem**

- **Consistent Hashing**

- **Idempotency**

- **Event Sourcing & CQRS**

---

## 9. Search Systems

- **Inverted Index**

- **Full-Text Search Engines**

  - ElasticSearch, Solr

- **Pagination Techniques**

  - Offset vs cursor-based

- **Ranking Algorithms**

  - TF-IDF, BM25, PageRank

- **Autocomplete and Spell Correction**

- **Faceted Search**

- **Scalable Search Engine Design**

---

## 10. Rate Limiting & Throttling

- **Algorithms**

  - Token Bucket, Leaky Bucket

- **Windowing Techniques**

  - Fixed window, Sliding window

- **API Gateway Rate Limiting**

- **Quotas per User/IP**

- **Backoff Strategies**
  - Exponential backoff

---

## 11. Security & Authorization

- **Authentication vs Authorization**
- **OAuth 2.0 / OpenID Connect**
- **JWT (JSON Web Tokens)**
- **HTTPS, TLS, Certificate Pinning**
- **Data Encryption**
  - At-rest (AES), In-transit (TLS/SSL)
- **API Keys and Secrets Management**
- **Common Vulnerabilities**
  - CSRF, XSS, SQL Injection
- **Secure Service-to-Service Communication (mTLS)**
- **HSTS, CORS**

---

## 12. Monitoring, Logging & Observability

- **Metrics**
  - Collection and visualization (Prometheus, Grafana)
- **Distributed Tracing**
  - Jaeger, OpenTelemetry
- **Log Aggregation**
  - ELK Stack (Elasticsearch, Logstash, Kibana)
- **Alerting Systems**
  - PagerDuty, Opsgenie
- **SLOs, SLAs, SLIs**
- **Health Checks and Heartbeats**

---

## 13. Designing for Scale

- **Horizontal Scaling**

  - Stateless service design

- **Vertical Scaling**

  - Hardware limitations

- **Async vs Sync Processing**

- **Database Scaling**

  - Read replicas, write sharding

- **CDN Usage**

- **Pre-computing / Materialized Views**

- **Backpressure Handling**

- **Batching**

- **Load Estimation and Bottleneck Analysis**

---

## 14. Failure Recovery & Resilience

- **Retry Logic**

- **Circuit Breaker Pattern**

- **Graceful Degradation**

- **Failover Mechanisms**

- **Data Backups**

- **Redundancy and High Availability**

- **Disaster Recovery Planning**

- **Chaos Engineering**

---

## 15. Real-World Design Scenarios

- **Design Twitter (Timeline Service)**
- **Design WhatsApp (End-to-end Encrypted Chat)**
- **Design Uber (Real-time Tracking and Pricing)**
- **Design Dropbox (File Syncing and Sharing)**
- **Design YouTube (Video Upload and Delivery)**
- **Design News Feed / Notification System**
- **Design Rate Limiter Service**
- **Design Payment System (Stripe-like)**
- **Design Stock Ticker Dashboard**
- **URL Shortener (Bitly)**
- **Social Media Feed**
- **Video Streaming Platforms**
- **File Sharing & Sync Apps**
- **Messaging & Chat Apps**
- **Ride-Sharing Apps**
- **Notification Systems**

---

## 16. Other Advanced Topics & Best Practices

- **API Design Best Practices**

  - RESTful principles, contracts

- **Versioning APIs**

- **gRPC vs REST**

- **Schema Evolution**

  - Avro, Protobuf

- **Batch vs Stream Processing**

- **ID Generation**

  - UUID, Snowflake

- **Multi-region Architecture**

- **Infrastructure as Code**

  - Terraform, Pulumi

- **Docker & Kubernetes Basics**

- **CI/CD Pipelines**

- **Module Decomposition**

- **OOP Principles & SOLID**

- **Design Patterns**

  - Factory, Singleton, Observer, Strategy

- **Class Diagrams**

- **Data Structures & Algorithms in System Components**

- **Geolocation Services**

  - Quadtrees, Geohashing

- **Data Sync**
  - Delta Sync, Conflict Resolution
  - CRDTs (Conflict-Free Replicated Data Types)

---

## 17. System Design Interview Process

- **Clarify Functional & Non-functional Requirements**

- **Define Constraints**

  - Scale, latency, throughput

- **High-Level Architecture Drafting**

- **Component Breakdown & Data Modeling**

- **Identify Bottlenecks & Trade-offs**

- **Scaling Strategies**

- **Security & Monitoring Considerations**

- **Draw Architecture Diagrams**

- **Discuss Real-world Examples**
