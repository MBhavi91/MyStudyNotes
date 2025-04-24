# Roadmap to Become a Full Stack Software Engineer

When I decided to re-enter the industry as a full-stack software engineer after a one-year break, I felt completely lost. I had no idea where to begin. There were countless articles on what to learn as a frontend developer, backend developer, or even about system architecture, but none of them provided a comprehensive, structured guide in one place.

After extensive research, I decided to start with HTML, as it forms the foundation of web development. To keep myself organized, I created a rough roadmap. However, I was fortunate to come across a website called [roadmap.sh](https://roadmap.sh/) one night while mindlessly scrolling through Instagram. This website turned out to be an invaluable resource, offering a clear learning path for various technologies. It also provided a wealth of project ideas for hands-on practice. While I will include as many of these as possible here, I highly recommend visiting the website for additional insights, assuming it remains available.

You might wonder why I am creating a GitHub page if such a website already exists. In today's digital landscape, nothing is guaranteed to last forever—websites can go offline at any time. Therefore, I wanted to document my own personalized roadmap, tailored to my learning needs.

Below is a comprehensive roadmap to becoming a full-stack software engineer. To avoid overwhelming information, I have categorized it systematically. The roadmap provides an overview of the full-stack development journey, followed by a detailed breakdown of each aspect.

## Table of Content

1. [FullStack](#full-stack)
2. [FrontEnd](#frontend)
3. [Backend](#backend)
4. [API Design](#api-design)
5. [API Security Best Practices](#api-security-best-practices)
6. [API Performance Best Practices](#api-performance-best-practices)
7. [Software Architecture](#software-architecture)
8. [Git and GitHub](#git-and-github)
9. [React](#react)
10. [Asp.net Core](#aspnet-core)
11. [JavaScript](#javascript)
12. [TypeScript](#typescript)
13. [SQL](#sql)
14. [PostgreSQL](#postgresql)
15. [Docker](#docker)
16. [Kubernetes](#kubernetes)
17. [Data Structure](#data-structure)
18. [System Design](#system-design)
19. [Code Review](#code-review)

## Role-Based Road Map

### Full Stack

- [HTML](./HTML)
- [CSS](./CSS/)
- JavaScript
- Npm
- [Git](./Github/)
- GitHub
- Tailwind
- React
- Node.js _(Backend start from here)_
- PostgreSQL
- Restful APIs
- JWT Auth
- Redis
- Linux basics _(DevOps start from here)_
- Basic AWS Service
- Monit
- GitHub Actions
- Ansible
- Terraform

### Frontend

- [Internet](./Internet/README.md)
  - How does the internet work?
  - What is HTTP?
  - What is a domain name?
  - What is hosting?
  - Browsers and how they work?
- [HTML](./HTML)
  - Learn the basics
  - Writing semantic HTML
  - Forms and validations
  - Accessibility
  - SEO basics
- [CSS](./CSS/)
  - Learn the basics
  - Making layouts
  - Responsive design
- JavaScript
  - Learn the basics
  - Learn DOM manipulation
  - Fetch API / AJAX (XHR)
- Version control system
  - [Git](./Github/)
- VCS Hosting
  - GitHub
  - GitLab
  - Bitbucket
- Package Managers
  - Npm
  - Pnpm
  - Yarn
- Pick Framework
  - React
  - Vue.js
  - Angular
  - Svelte
  - Solid JS
  - Qwik
- Writing CSS
  - Tailwind
  - CSS Architecture
    - BEM
  - CSS preprocessors
    - Sass
    - PostCSS
- Build Tools
  - Linters and Formatters
    - Prettier
    - ESLint
  - Module Bundlers
    - Vite
    - SWC, esBuild
    - Webpack
    - Rollup
    - Parcel
- Testing
  - Vitest
  - Jest
  - Playwright
  - Cypress
- Authentication Strategies
  - JWT, OAuth, SSO, Basic Auth, Session Auth
- Web Security
  - CORS
  - HTTPS
  - Content Security Policy
  - OWASP Security Risks
- Web Components
- Type Checkers
  - TypeScript
- SSR
  - React
  - Next.js
  - Astro
  - React-router
  - Angular
  - Vue.js
  - Nuxt.js
  - Svelte
  - SvelteKit
- GraphQL
  - Apollo
  - Relay Modern
- PWAs
  - Measure & Improve Performance
    - PRPL Pattern
    - RAIL Model
    - Performance Metrics
    - Using Lighthouse
    - Using DevTools
- Browser APIs
  - Storage
  - Web Sockets
  - Server Sent Event
  - Service Workers
  - Location
  - Notifications
  - Device Orientation
  - Payments
  - Credentials
- Static Site Generators
  - Next.js
  - Astro
  - Vuepress
  - Eleventy
  - Nuxt.js
- Mobile Apps
  - React Native
  - Flutter
  - Ionic
- Desktop Apps
  - Electron
  - Tauri
  - Flutter

### Backend

- [Internet](./Internet/README.md)
  - How does the internet work?
  - What is HTTP?
  - What is a domain name?
  - What is hosting?
  - Browsers and how they work?
- Pick a Language
  - Javascript
  - Go
  - Python
  - Java
  - PHP
  - GO
  - Ruby
  - C#
  - Rust
- Version Control System
  - Git
- Repo Hosting Services
  - GitHub
  - GitLab
- Relational Databases
  - PostgreSQL
  - MySQL
  - MariaDB
  - Ms SQL
  - Oracle
  - SQLite
- Learn about APIs
  - Rest
  - Json
  - Soap
  - gRPC
  - GraphQL
  - HATEOAS
  - Open API Specs
  - Authentication
    - JWT
    - OAuth
    - Basic Authentication
    - Token Authentication
    - Cookie Based Auth
    - OpenId
    - SAML
- Caching
  - Server Side
    - Redis
    - Memacached
      -CDN
      -Client Side
- Web Security
  - Hashing Algorithms
    - MD5
    - SHA
    - Scrypt
    - Bcrypt
  - API Security Best Practices
    - HTTPs
    - OWASP Risks
    - CORS
    - SSL/TLS
    - CSP
    - Server Security
- Testing
  - Integration Testing
  - Unit Testing
  - Functional Testing
- CD/CI
- More about Databases
  - ORMs
  - ACID
  - Transactions
  - N + 1 Problems
  - Normalization
  - Failure Modes
  - Profiling Perforamance
  - Migrations
- Scaling Databases
  - Database Indexes
  - Data Replication
  - Sharding Strategies
  - CAP Theorem
- Software Design & Architecture
  - Architectual Patterns
    - Monolithic Apps
    - Microservices
    - SOA
    - Serverless
    - Service Mesh
    - Twelve Factor Apps
  - Design & Development Principles
    - GOF Design Patterns
    - Domain Driven Design
    - Test Driven Developement
    - CQRS
    - Event Sourcing
  - Containerxation Vs Virtualization
    - Docker
      -LXC
    - Kubernets
  - Message Brokers
    - RabbitMQ
    - Kafta
  - Search Engines
    - Elastic Search
    - Solr
  - Web Servers
    - Nginx
    - Apache
    - Caddy
    - Ms IIS
  - Real-Time Data
    - Server Sent Events
    - WebSockets
    - Long Polling
    - Short Polling
- GraphQL
  - NoSQL Databases
    - Key-Value
      - Redis
      - DynamoDB
    - Document DBs
      - MangoDB
      - CouchDB
    - Realtime
      - Firebase
      - RethinkDB
    - Time Series
      - Influx DB
      - TimeScale
    - Column DBs
      - Cassandra
      - Base
    - Graph DBs
      - Neo4j
      - AWS Neptune
  - Building For Scale
    - Mitigation Strategies
      - Graceful Degradation
      - Throttling
      - Backpressure
      - Loadshifting
      - Circuit Breaker
    - Types of Scaling
    - Obervability
    - Difference & Usage
      - Instrumentation
      - Monitoring
      - Telemetry

### API Design

- Learn the basics (Building APIs)
  - What is APIs
  - HTTP
    - HTTP Versions
    - HTTP Methods
    - HTTP Status Codes
    - HTTP Headers
    - Cookies
    - CORS
    - HTTP Caching
  - URL, Query & Path Parameters
  - Content Negotiation
  - Understand TCP/IP
  - Basics of DNS
- Different APIs Styles
  - RESTful APIs
  - Simple JSON APIs
  - SOAP APIs
  - GraphQL APIs
  - gRPC APIs
- Building JSON/RESTful APIs
  - REST Principles
  - URI Design
  - Versioning Stratergies
  - Handling CRUD OPerations
  - Pagination
  - Rate Limiting
  - Idempotency
  - HATEOAS
  - Error Handling
  - RFC 7807 - Problem Details for APIs
- Authentication Methods (API Authentication and Authorization)
  - Basic Auth
  - Token Based Auth
  - JWT
  - OAuth 2.0
  - Session Based Auth
- Authoization Methods
  - Role Based Access Control(RBAC)
  - Atrribute Based Access Control(ABAC)
- API Keys & Management
- API Documentation Tools
  - Swagger / Open API
  - Readme
  - Stoplight
  - Postman
- API Security
  - API Security Best Practices
- API Performance
  - Performance Metrics
  - Caching Strategies
  - Load Balancing
  - Rate Limitting/ Throttling
  - Profiling & Monitoring
  - Performance Testing
  - Error Handling / Retries
  - API Performance Best Practices
- API Integration Patterns
  - Synchronous vs Asynchronous APIs
  - Event Driven Architecture
  - API Gateways
  - Microservices Architecture
  - Webhooks vs Polling
  - Batch Processing
  - Messaging Queues
    - Rabbit MQ
    - Kafta
- API Testing
  - Mocking APIs
  - Contract Testing
- Real-time APIs
  - Web Sockets
  - Server Sent Events
- API Lifecycle Management
- Standards and Compliance
  - GDPR
  - CCPA
  - PCI DSS
  - HIPAA
  - PII

### Software Architecture

- Understand the Basics
  - What is Software Architecture
  - Level of Architecture
    - Application Architecture
    - Solution Architecture
    - Enterprice Architecture
- Responsibilities
  - Tech Decision
  - Design & Architecture Decisions
  - Requirements Elicitation
  - Documentation
  - Enfocing Standards
  - Collaborate with others
  - Consult & Coach Developers
- Important Skills to Learn
  - Design & Architecture
  - Decision Making
  - Simplifyling Things
  - How to code
  - Documentation
  - Communication
  - Estimate and Evaluate
  - Balance
  - Consult & Coach
  - Marketing Skills
- Techincal Skills
- Programming Language
  - Java/Kotlin/Scala
  - Python
  - Ruby
  - Go
  - Typescript/Javascript
  - .Net Framework Based
- Patterns & Design Principles
  - MVC, MVP, MVVM
  - CQRS, Eventual Consistency
  - OOP
  - Actors
  - ACID, CAP Theorem
  - SOLID/TDD/DDD
- Tools
  - Git/Github
  - Slack
  - Trello
  - Atlassian Tools
- Architecture
  - Microservices
  - Serverless
  - Client/Server
  - Layered
  - Distributed Systems
  - Service Oriented
- Security
  - Hasing Algorithms
  - PKI
  - OWASP
  - Auth Stratergies
- Working with Data
  - Hadoop, Spark, MapReduce
  - ETL, Datawarehouses
  - SQL Databases
  - NoSQL Databases
- API & Integrations
  - gRPC
  - ESB/SOAP
  - REST
  - GraphQL
  - BPM, BPEL
  - Messaging Queues
- Web, Mobile
  - Reactive Programming
  - Functional Programming
  - React, Vue, Angular
  - SPA, SSR, SSG
  - Microfrontends
  - W3C and WHATWQ
- Frameworks
  - BABOK
  - IAF
  - UML
  - TOGAF
- Management
  - Agile Model
- Networks
  - OSI
  - TCP/IP Model
  - HTTP, HTTPs
  - Proxies
  - Firewalls
- Operational Knowledge
  - Infrastructure as Code
  - Cloud Providers
  - Serverless Concepts
  - Linux/ Unix
  - Serice Mesh
  - CD/CI
  - Containers
  - Clound Design Patterns
    -Enterprice Softwares
  - MS Dynamics
  - SAP ERP, HANA, Business Objects
  - EMC DMS
  - IBM BPM
  - SalesForce

## Skill-Based Roadmap

### JavaScript

- Introduction to Javascript
  - What is Javascript
  - History of Javascript
  - Javascript Version
  - How to run Javascript
- All About Variables
  - Variable Declaration
    - var, let, const
  - Hoisting
  - Variable Naming Rules
  - Variable Scopes
    - Block, Function, Global
- DataTypes
  - Primitive Types
    - string
    - undefined
    - nuber
    - bigint
    - boolean
    - null
    - symbol
  - Object
    - Object Prototypes
    - Prototypal Inheritance
    - Built-in Objects
  - typeof operator
- Type Casting
  - Type Conversion vs Coercion
  - Implicit Type Casting
  - Explicit Type Casting
- Data Structure
  - Keyed Collections
    - Map
    - Weak Map
    - Set
    - Weak Set
  - Structured Data
    - JSON
  - Indexed Collections
    - Typed Arrays
    - Arrays
- Equality Comparisons
  - Value Comparison Operators
    - ==, ===, Object.is
  - Equality Algorithms
    - isLooselyEqual
    - isStrictlyEqual
    - SameValueZero
    - SameValue
- Loops and Iterations
  - for
  - do...while
  - while
  - break / continue
  - for...of loop
  - for...in loop
- Control Flow
  - COnditional Statements
    - if...else
    - Switch
  - Exceptional Handling
    - throw statement
    - try/catch/finally
    - Error objects
- Expressions & Operators
  - Conditional Operators
  - Comma Operators
  - Unary Operators
  - Assignment Operators
  - Comparison Operators
  - Arithmetic Operators
  - Bitwise Operators
  - Logical Operators
  - BigInt Operators
  - String Operators
- Functions
  - Functional Parameters
    - Default Param
    - Rest
  - Arrow Function
  - IIFEs
  - arguments objecr
  - Scope & Function Stack
  - Built-in Functions
- DOM APIs
- Strict Mode
- Using(this) keyword
  - in a method
  - in a function
  - using it alone
  - in event handlers
  - in arrow functions
  - Function Borrowing
  - Explicit Binding
    - call, apply, bind
- Asynchronous Javascript
  - Event Loop
  - Call backs
    - Call back hell
  - Promise
    - Async/await
  - setTimeout
  - setInterval
- Working with APIs
- Classes
- Iterators & Generators
- Modules in javascript
  - CommonJS
  - ESM
- Memory Management
  - Memory lifecycle
  - Garbage Collection
- Using browser DevTools
  - Debugging Issues
  - Debugging Memory Leaks
  - Debugging Performance

### Git and GitHub

### React

### Asp.net Core

### TypeScript

### SQL

### PostgreSQL

### Docker

### Kubernetes

### Data Structure

### System Design

### Code Review
