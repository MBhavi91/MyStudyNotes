# Roadmap to Become a Full Stack Software Engineer

When I decided to re-enter the industry as a full-stack software engineer after a one-year break, I felt completely lost. I had no idea where to begin. There were countless articles on what to learn as a frontend developer, backend developer, or even about system architecture, but none of them provided a comprehensive, structured guide in one place.

After extensive research, I decided to start with HTML, as it forms the foundation of web development. To keep myself organized, I created a rough roadmap. However, I was fortunate to come across a website called [roadmap.sh](https://roadmap.sh/) one night while mindlessly scrolling through Instagram. This website turned out to be an invaluable resource, offering a clear learning path for various technologies. It also provided a wealth of project ideas for hands-on practice. While I will include as many of these as possible here, I highly recommend visiting the website for additional insights, assuming it remains available.

You might wonder why I am creating a GitHub page if such a website already exists. In today's digital landscape, nothing is guaranteed to last forever—websites can go offline at any time. Therefore, I wanted to document my own personalized roadmap, tailored to my learning needs.

Below is a comprehensive roadmap to becoming a full-stack software engineer. To avoid overwhelming information, I have categorized it systematically. The roadmap provides an overview of the full-stack development journey, followed by a detailed breakdown of each aspect.

## Role-Based Road Map

### Full Stack

- [HTML](./HTML)
- CSS
  - Checkpoint - Static Webpages
- JavaScript
  - Checkpoint - Interactivity
- Npm
  - Checkpoint - External Packages
- [Git](./Github/)
- GitHub
  - Checkpoint - Collaborative work
- Tailwind
- React
  - Checkpoint - Frontend Apps
- Node.js _(Backend start from here)_
  - Checkpoint - CLI Apps
- PostgreSQL
  - Checkpoint - Simple CRUD Apps
- Restful APIs
- JWT Auth
- Redis
  - Checkpoint - Complete App
- Linux basics _(DevOps start from here)_
- Basic AWS Service
  - Checkpoint - Deployment
- Monit
  - Checkpoint - Monitoring
- GitHub Actions
  - Checkpoint - CD/CI
- Ansible
  - Checkpoint - Automation
- Terraform
  - Checkpoint - Infrastructure

### Frontend

- Internet
  - How does the internet work?
  - What is HTTP?
  - What is a domain name?
  - What is hosting?
  - DNS and how it works?
  - Browsers and how they work?
- [HTML](./HTML)
  - Learn the basics
  - Writing semantic HTML
  - Forms and validations
  - Accessibility
  - SEO basics
- CSS
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

- Internet
  - How does the internet work?
  - What is HTTP?
  - What is a domain name?
  - What is hosting?
  - DNS and how it works?
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

### API Security Best Practices

### API Performance Best Practices

### Software Architecture

## Skill-Based Roadmap

### Git and GitHub

### React

### Asp.net Core

### JavaScript

### TypeScript

### SQL

### PostgreSQL

### Docker

### Kubernetes

### Data Structure

### System Design

### Code Review
