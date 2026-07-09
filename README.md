# Hi, I'm Morteza Asghari

**Senior / Lead Backend Engineer — .NET, Distributed Systems**

I build backend systems where correctness, maintainability, and operational clarity matter.

My main background is in **C# / .NET backend engineering**, with 10+ years across **loyalty platforms, FinTech, e-commerce, real-time systems, and distributed backend architecture**. I have also worked in betting/gaming-related domains, but that is not the main direction of my profile.

I care about architecture, but I care more about architecture that survives real delivery pressure.

Based in **Berlin, Germany** (EU Blue Card). Currently open to senior/lead backend roles.

---

## What I work with

**Backend**

* C# / .NET / ASP.NET Core
* Minimal APIs, REST, gRPC, SignalR
* EF Core, Dapper, background services
* Native AOT (two active projects ship AOT binaries)
* Avalonia, Blazor, WPF, .NET MAUI when needed

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
* FASTER

**Infrastructure**

* Docker / Docker Compose
* Kubernetes
* GitHub Actions / Azure DevOps
* Linux-based development and deployment

**Also worked with**

* Go
* Java
* Swift (iOS capture client for TrustCapture)
* Akka.NET
* AI-assisted development workflows

---

## Selected projects

### TrustCapture

A cryptographic photo/video provenance system currently in progress.

The idea is simple: **proof, not detection**.

Instead of trying to detect whether media was manipulated after the fact, TrustCapture focuses on capture-time signing and verifiable provenance.

Current technical direction:

* iOS capture signing (Swift)
* Secure Enclave / App Attest concepts
* C# backend
* Native AOT
* gRPC / QUIC
* PostgreSQL-backed registry
* Tamper-evident manifests

Current state: active but unfinished; repositories are private for now. The registry is deployed, some MVP-level verification/provenance pieces exist, but important parts such as the verification page, admin/dashboard, Android support, and full production hardening are still missing or incomplete.

---

### [DownloadManager](https://github.com/mortezasghari/DownloadManager)

A cross-platform desktop download manager built on .NET 10, Avalonia, and **Native AOT**, designed to reliably download files from a few KB to 100+ GB on unstable networks — surviving application crashes and system reboots.

What makes it interesting:

* Durability-first design: data fsync → progress append → progress fsync, enforced in one place
* CRC-protected binary progress log with torn-tail recovery
* `If-Range` resume with correct 200-fallback handling
* Source-generated JSON metadata (no reflection, AOT-clean)
* Architecture decisions recorded as ADRs in the repo
* CI builds, tests, AOT-publishes and smoke-runs on linux-x64, linux-arm64, win-x64, and osx-arm64

Phase 1 (crash-safe single-stream engine) is complete and green with a focused test suite; parallel segmented downloads are the next phase.

---

### [BluezNet](https://github.com/mortezasghari/BluezNet)

A Linux Bluetooth manager written in C#, talking **directly to BlueZ 5 over the D-Bus system bus** — no `bluetoothctl`, no shelling out. It ships a CLI and an Avalonia GUI on a shared, signal-driven core, and both compile to Native AOT binaries.

Key parts:

* Scan, pair (with a registered pairing agent), trust, connect, disconnect, remove
* `Tmds.DBus.Protocol` + source-generated proxies — zero runtime reflection, AOT/trim safe
* Generic `a{sv}` property-change parsing where the generated typed parser can't survive real BlueZ signals
* Hand-written pairing agent so declines map precisely to `org.bluez.Error.Rejected`

A project about doing systems-level Linux integration properly from .NET, with the "why" behind each technology choice documented in the README.

---

### [StepsCasino / StepPoker](https://github.com/StepPoker/StepsCasino)

A distributed multiplayer Texas Hold'em backend used as a technology demonstrator for advanced backend architecture.

Built with:

* .NET / C#
* Akka.NET cluster sharding
* EventStoreDB
* Event Sourcing / CQRS
* gRPC over HTTP/2 and HTTP/3 (QUIC)
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
* Unit and integration tests (no real network in tests — in-memory sink + WireMock)
* Configuration through environment variables / user secrets

---

### [Skein](https://github.com/mortezasghari/Skein)

An **embedded distributed cache library** for .NET, built on FASTER, exploring low-latency distributed state for workloads where the round-trip to a separate cache service (Redis, Garnet) is too expensive.

The architectural thesis: real low-latency workloads have (at least) four distinct data shapes, and forcing them into one replication model is the failure mode of most distributed cache libraries. Skein models them as four tiers:

* **Replicated** — reference data mirrored to every node, gossip-propagated
* **Sharded** — hash-partitioned persistent entities, primary + replica
* **Followers** — owner-authoritative data with opt-in read-only replicas on reading nodes
* **Session** — hot ephemeral state with an active warm replica for sub-second failover, no journal replay

Status: pre-alpha learning project, deliberately scoped and honestly labeled. The value is in the technical exploration of replication protocols, placement, and failover in the .NET ecosystem — not in pretending it competes with Garnet.

---

### [pace-poker](https://github.com/mortezasghari/pace-poker)

A Go-based multiplayer poker backend experiment.

Focus areas:

* gRPC API design
* Actor-per-session concurrency (one goroutine per game)
* PostgreSQL persistence
* Append-only event log with optimistic concurrency
* Go concurrency patterns from a C# backend engineer's perspective

This project is experimental. It is useful as a learning and architecture exploration project, not as something I would present as a mature production system.

---

## Experience highlights

* Owned backend architecture for a national loyalty/cashdesk system at Oetker Digital (Berlin) — two production microservices with ASP.NET Core, EF Core, PostgreSQL, and RabbitMQ, including full coupon/discount logic for 15+ promotion types.
* Led a monolith-to-microservices migration (Strangler Fig) for an education platform that scaled from ~35K to 500K+ active users — cutting average API response time ~90% and bringing error rates from 5–10% to negligible at 300–400 req/s peak.
* Won a key architecture decision under delivery pressure: a dedicated cashdesk microservice over the planned stored-procedure approach, improving testability and separation of concerns.
* Co-founded a crypto payment gateway and owned security-critical backend areas such as wallet management and transaction integrity.
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

* Email: [morteza.asghari@live.com](mailto:morteza.asghari@live.com)
* GitHub: [github.com/mortezasghari](https://github.com/mortezasghari)
* LinkedIn: [linkedin.com/in/morteza-asghari](https://www.linkedin.com/in/morteza-asghari/)

<!--
**mortezasghari/mortezasghari** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
-->
