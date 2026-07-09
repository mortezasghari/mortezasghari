# Hi, I'm Morteza Asghari

**Senior / Lead Backend Engineer — .NET, Distributed Systems**

I build backend systems where correctness, maintainability, and operational clarity matter.

My main background is in **C# / .NET backend engineering**, with experience in **loyalty platforms, FinTech, e-commerce, real-time systems, and distributed backend architecture**. I have also worked in betting/gaming-related domains, but that is not the main direction of my profile.

I care about architecture, but I care more about architecture that survives real delivery pressure.

Based in **Berlin, Germany**.

---

## What I work with

**Backend**

* C# / .NET / ASP.NET Core
* Minimal APIs, REST, gRPC, SignalR
* EF Core, Dapper, background services
* Blazor, WPF, .NET MAUI when needed

**Architecture**

* Domain-Driven Design
* Clean Architecture
* Microservices
* Event-driven systems
* CQRS / Event Sourcing
* Actor Model
* Strangler Fig migrations

**Data & messaging**

* PostgreSQL
* SQL Server
* Redis
* RabbitMQ
* EventStoreDB

**Infrastructure**

* Docker / Docker Compose
* Kubernetes
* GitHub Actions / Azure DevOps
* Linux-based development and deployment

**Also worked with**

* Go
* Java
* Akka.NET
* AI-assisted development workflows

---

## Selected projects

### [StepsCasino / StepPoker](https://github.com/StepPoker/StepsCasino)

A distributed multiplayer Texas Hold'em backend used as a technology demonstrator for advanced backend architecture.

Built with:

* .NET / C#
* Akka.NET cluster sharding
* EventStoreDB
* Event Sourcing / CQRS
* gRPC over HTTP/2 and HTTP/3
* MessagePack serialization
* Docker Compose
* xUnit / Akka.TestKit

This is **not** a finished product and not production-ready. It is a research and architecture demonstrator for distributed systems, actor-based design, event-sourced game logic, and real-time backend coordination.

---

### [NotificationService](https://github.com/mortezasghari/NotificationService)

A .NET backend service that receives notifications over HTTP, classifies warning-level or higher messages using an LLM, and forwards human-readable alerts to Discord.

Key parts:

* .NET 10 Minimal API
* Background processing with `System.Threading.Channels`
* Sliding-window outbound rate limit: 10 messages/minute
* LLM fallback behavior
* Discord webhook integration
* Unit and integration tests
* Configuration through environment variables / user secrets

---

### [pace-poker](https://github.com/mortezasghari/pace-poker)

A Go-based multiplayer poker backend experiment.

Focus areas:

* gRPC API design
* Session-oriented backend architecture
* PostgreSQL persistence
* Append-only event log ideas
* Go concurrency patterns from a C# backend engineer's perspective

This project is experimental. It is useful as a learning and architecture exploration project, not as something I would present as a mature production system.

---

### TrustCapture

A cryptographic photo/video provenance system currently in progress.

The idea is simple: **proof, not detection**.

Instead of trying to detect whether media was manipulated after the fact, TrustCapture focuses on capture-time signing and verifiable provenance.

Current technical direction:

* iOS capture signing
* Secure Enclave / App Attest concepts
* C# backend
* Native AOT
* gRPC / QUIC
* PostgreSQL-backed registry
* Tamper-evident manifests

Current state: active but unfinished. The registry is deployed, some MVP-level verification/provenance pieces exist, but important parts such as the verification page, admin/dashboard, Android support, and full production hardening are still missing or incomplete.

---

### Skein Project

Skein is an experimental project, not a polished product.

I include it because it reflects how I approach architecture, prototyping, and backend design, but I would not describe it as production-ready or complete.

Current state:

* unfinished
* experimental
* useful as a design/prototyping project
* not something I would claim is production-hardened
* not yet at the level where the README should oversell it as a finished system

The value of the project is in the technical exploration, not in pretending it is more complete than it is.

---

## Experience highlights

* Built backend services for a national loyalty/cashdesk system using ASP.NET Core, EF Core, PostgreSQL, RabbitMQ, and clean architecture.
* Led a monolith-to-microservices migration for an education platform that scaled from around 35K to 500K+ active users.
* Worked on systems where transactional correctness, maintainability, and clear service boundaries mattered.
* Co-founded a crypto payment gateway and owned security-critical backend areas such as key management and transaction integrity.
* Comfortable bridging business requirements and engineering implementation without hiding behind vague architecture language.

---

## How I think about software

I prefer systems that are:

* explicit over magical
* boring where possible
* carefully designed where necessary
* observable when they fail
* testable without heroic effort
* understandable by the next engineer who has to maintain them

I am especially interested in backend architecture, distributed systems, event-driven design, and production-shaped prototypes that prove whether an idea can actually work.

---

## Contact

* GitHub: [github.com/mortezasghari](https://github.com/mortezasghari)
* LinkedIn: [linkedin.com/in/morteza-asghari](https://www.linkedin.com/in/morteza-asghari/)

<!--
**mortezasghari/mortezasghari** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
