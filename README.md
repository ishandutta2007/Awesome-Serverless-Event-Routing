# Awesome-Serverless-Event-Routing

## Top Serverless Event Routing Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Event-Driven Architecture, Webhook Infrastructure & Serverless Automation*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Serverless Event Routing**. These tools connect event producers to consumers — routing, transforming, filtering, and delivering events across services, queues, and webhooks without managing servers.



**Examples** include Azure Event Grid, AWS EventBridge, Google Cloud Eventarc, Courier, Trigger.dev, Inngest, Knock, Svix, Hookdeck, and Cloudflare Queue (the category leaders).



**Open-source emphasis**: Serverless event routing is a rapidly maturing open-source domain. **Typhoon** provides a cloud-native EventBridge alternative on NATS and Knative . **Drasi** from Microsoft brings real-time change detection with continuous queries . **Outpost** and **Novu** deliver production-grade webhook and notification infrastructure . **Hookdash** and **xtandard/webhooks** offer lightweight, dependency-minimal webhook gateways . This section is heavily expanded.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[AWS EventBridge](https://aws.amazon.com/eventbridge/)**  

  AWS's serverless event bus for routing events between AWS services, SaaS applications, and custom applications. **The reference implementation for cloud-native event routing** — schema registry, event replay, and archive capabilities. The open-source Typhoon project explicitly positions itself as an AWS EventBridge alternative .



- **[Azure Event Grid](https://azure.microsoft.com/en-us/products/event-grid)**  

  Microsoft's fully managed event routing service with publish-subscribe semantics, dead-letter queues, and filtering. Integrates natively with Azure services and custom webhooks.



- **[Google Cloud Eventarc](https://cloud.google.com/eventarc)**  

  Google Cloud's event routing service with standard CloudEvents support, audit logging, and workflow integration.



- **[Inngest](https://www.inngest.com/)**  

  Event-driven workflow platform for serverless functions with automatic retries, step functions, and fan-out. **The modern developer experience for background jobs and event orchestration**.



- **[Trigger.dev](https://trigger.dev/)**  

  Open-source background jobs framework with event-driven triggers, long-running tasks, and real-time observability.



- **[Courier](https://www.courier.com/)**  

  Notification infrastructure API for routing messages across email, SMS, push, and chat with template management and routing rules.



- **[Knock](https://knock.app/)**  

  Notification infrastructure with workflow builder, subscriber preferences, and multi-channel delivery orchestration.



- **[Svix](https://www.svix.com/)**  

  **The leading webhook-as-a-service platform** — send webhooks from your application with retries, signatures, and a customer portal. Self-hostable with MIT-licensed server .



- **[Hookdeck](https://hookdeck.com/)**  

  Event gateway for receiving, routing, and monitoring webhooks with retries, transformations, and observability. Powers the open-source Outpost project .



- **[Cloudflare Queue](https://developers.cloudflare.com/queues/)**  

  Cloudflare's serverless message queue for asynchronous processing at the edge with guaranteed delivery and automatic retries.



## Open-Source GitHub Projects



### Event Routing & Event Mesh



- **[Typhoon](https://github.com/zeiss/typhoon)**  

  **Cloud-native open-source alternative to AWS EventBridge**, built on NATS.io and Knative Eventing . Designed for enterprise-ready event mesh routing across hybrid cloud environments. Features **event streaming with replay capability**, declarative event bridging with transformations, horizontal and vertical scalability, and resilience with security built in. Helm-based installation on Kubernetes 1.28+ with Knative Eventing/Serving 1.16+. **The most direct open-source EventBridge replacement** for organizations wanting event routing without cloud vendor lock-in.



- **[Drasi](https://github.com/drasi-project/drasi)**  

  **Microsoft's open-source system for real-time event processing and automation**, Apache-2.0 licensed . Detects critical events in complex infrastructures using **Continuous Queries** written in Cypher Query Language that evaluate data as it arrives — eliminating polling and batch processing overhead. Three components: **Sources** monitor databases, logs, and metrics; **Continuous Queries** integrate multi-source data in real-time; **Reactions** trigger automated responses (alerts, system updates, remediation). Prebuilt integrations with PostgreSQL, Microsoft Dataverse, and Azure Event Grid. **Best for real-time change detection across heterogeneous systems**.



- **[Cerk](https://github.com/ce-rust/cerk)**  

  **CloudEvents Router with a Microkernel architecture** — a modular, extensible event routing engine . Routes CloudEvents between different transport protocols and brokers. **Best for organizations standardized on CloudEvents needing a lightweight, pluggable router**.



- **[Vanus Connect](https://github.com/vanus-labs/vanus-connect)**  

  Event streaming platform that **skips complex integration with external services by offering out-of-the-box connectors** . **Best for teams wanting pre-built connectors for common event sources**.



- **[Hybrid Automation Router (HAR)](https://github.com/hyperpolymath/hybrid-automation-router)**  

  **Intelligent event routing for automation targets** with seven routing strategies: Direct, CapabilityMatch, TagMatch, RoundRobin, WeightedRandom, LeastLoaded, and Failover . Rust-based core with health checking, dead-letter queues, and metrics collection. **Best for routing automation events across heterogeneous tool estates** (Puppet, Salt, Terraform, Ansible).



### Webhook Infrastructure



- **[Outpost (Hookdeck)](https://github.com/hookdeck/outpost)**  

  **Open-source outbound webhooks and event destinations infrastructure**, Apache-2.0 licensed and maintained by Hookdeck . Enables event producers to add **outbound webhooks and Event Destinations** (Webhooks, EventBridge, SQS, S3, GCP Pub/Sub, RabbitMQ, Kafka) to their platform. Features **event topics with topic-based subscriptions**, at-least-once delivery guarantee, event fanout, automatic and manual retries, **multi-tenant support with user portal**, OpenTelemetry instrumentation, and webhook best practices (idempotency headers, signatures, signature rotation). Minimal dependencies (Redis, PostgreSQL/Clickhouse, message queue). **The most production-ready open-source webhook infrastructure** — built for high-throughput, low-cost operation.



- **[Hookdash](https://github.com/hookdash/hookdash)**  

  **Zero-config, self-hosted webhook gateway with beautiful dashboard**, MIT licensed . **No Redis. No Postgres. Just SQLite** — `npx hookdash start` and you're running. Features webhook ingestion from any source, **signature verification for Stripe, GitHub, Twilio, Shopify**, exponential backoff retries with jitter, **circuit breaker** for failing endpoints, dead-letter queue, **one-click replay**, real-time dashboard with SSE, and Docker deployment. **The simplest path to production webhook handling** — compare to Svix (requires PG+Redis+Kafka), Convoy (PG+Redis), Hookdeck (cloud only). **Best for developers and small teams wanting webhook reliability without infrastructure overhead**.



- **[xtandard/webhooks](https://github.com/xtandard/webhooks)**  

  **Webhook delivery as a library, not a service** . Built on **Standard Webhooks** specification — receivers verify with official `standardwebhooks` libraries in Python, Go, Ruby, Java, Rust, PHP. Two-plane architecture: **Control plane** (CRUD on applications, event types, endpoints) and **Delivery plane** (publish is one message write, dispatcher owns all network I/O). **Crash-safe with leases** — kill the process mid-retry, restart, and pending deliveries resume. Features customer self-serve portal, exponential retries, dead-letters, replay, observability. **Best for teams wanting webhook reliability without operating a separate service** — `bun add` and your existing database.



- **[AWS Serverless Webhooks](https://github.com/boringContributor/aws-serverless-webhooks)**  

  **Self-hosted, serverless webhook-as-a-service on AWS**, CDK-based . Similar to Svix but deployed on your own AWS infrastructure. Uses **AWS Durable Functions** for reliable delivery with automatic retries, API Gateway for management API, DynamoDB for configuration and delivery logs, and EventBridge integration. Includes example React configuration UI. **Best for AWS-native teams wanting webhook infrastructure without SaaS dependency**.



### Notification Infrastructure



- **[Novu](https://github.com/novuhq/novu)**  

  **Open-source notification infrastructure — self-hosted Knock, Courier, and OneSignal alternative**, MIT licensed . **Unified API for email, SMS, push, in-app inbox, Slack, Teams, Discord, WhatsApp**. Features **visual workflow editor** with drag-and-drop flow builder, conditions, delays, and digest; **in-app notification center** (embeddable React/Angular/Vue inbox); subscriber preference management; template editor with i18n; and delivery observability. Architecture: NestJS API, Bull/Redis worker, WebSocket service for real-time in-app, React dashboard, MongoDB + Redis. **No per-notification pricing** — pay only for compute. **The most complete open-source notification platform** — full data ownership.



### Job Queues & Workflow Engines



- **[Flowli](https://jsr.io/@alialnaghmoush/flowli)**  

  **Type-safe job and workflow framework for TypeScript/JavaScript** with explicit runtime wiring . **Single job surface, multiple execution modes** — in-process `run()`, persisted `enqueue()`, `delay()`, and `schedule()`. Supports **Redis/Valkey/Dragonfly drivers** with at-least-once, lease-based execution. **Framework-agnostic core** with adapters for Hono, Next.js, and TanStack Start. Features retry with exponential backoff, jitter, capped retries, and **inspection API** for observability. **Best for TypeScript teams wanting job queue semantics without a separate service**.



- **[Queueflow](https://github.com/benrobo/queueflow)**  

  **Minimal Redis-based task queue for TypeScript** with automatic worker management . **Define tasks with `defineTask()`, trigger with `.trigger()` — worker starts automatically**. Features delayed jobs, retry with backoff, error handling via `onError`, and **cron-scheduled recurring tasks**. Built on BullMQ. **Best for developers wanting dead-simple background job processing**.



- **[Iggy](https://github.com/iggy-rs/iggy)**  

  **High-performance, ultra-low-latency message streaming platform** in Rust, Apache-2.0 licensed . Positioned as the best in its class for **resource consumption, throughput, and latency**. Features horizontal scalability, real-time streaming, and SDKs for multiple languages. **Apache incubator project** with active community. **Best for teams needing a lightweight, fast alternative to Kafka** for event streaming.



### Additional Strong Open-Source Options



- **Accenture/reactive-interaction-gateway** — Low-latency, interactive user experiences for stateless microservices, Elixir-based .

- **silverton-io/buz** — Serverless multi-protocol + multi-destination event collection system, Go-based .

- **myntra/cortex** — Fault-tolerant events/alerts correlation engine .

- **CloudEvents SDKs** — Official SDKs for Python, Go, Java, .NET, JavaScript, Rust, C++, and more .

- **sasha-tkachev/venty** — Event-driven tooling built around CloudEvents .

- **summerwind/cloudevents-webhook-gateway** — HTTP gateway converting webhook requests to CloudEvents .



**Frameworks for building custom serverless event routing**: Combine **Typhoon** for cloud-native event mesh routing on Kubernetes with NATS and Knative . Use **Drasi** for real-time change detection and automated reactions across heterogeneous data sources . Deploy **Outpost** for production-grade outbound webhook infrastructure with multi-tenant support and event destination fanout . Choose **Hookdash** for zero-config, single-binary webhook handling with SQLite . Use **Novu** for unified multi-channel notification infrastructure with visual workflow builder . For TypeScript job queues, **Flowli** or **Queueflow** provide typed, framework-agnostic task processing . Note that true enterprise event routing with global infrastructure, managed SLAs, and integrated observability remains primarily commercial territory; open-source stacks provide strong event mesh, webhook, and notification foundations that require integration for complete event-driven architectures.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Serverless event routing handles sensitive event payloads and potentially credentials. Self-hosted solutions require proper security hardening, access controls, and compliance with data privacy regulations.

- **Webhook delivery is at-least-once by design** — receivers must be idempotent. Use idempotency keys or deduplication based on `webhook-id` headers .

- **Event routing introduces observability complexity** — distributed tracing, dead-letter queues, and replay capabilities are essential for debugging event-driven systems. Outpost provides OpenTelemetry instrumentation .

- **NATS and Knative prerequisites** — Typhoon requires Kubernetes 1.28+, Knative Eventing 1.16+, and NATS . Evaluate operational complexity against your team's Kubernetes expertise.

- The open-source ecosystem provides strong event mesh, webhook, and notification foundations, but **global infrastructure, managed SLAs, and integrated observability** remain primarily commercial offerings.



---



**Made for platform engineers, backend developers, and architects building event-driven systems.**  

Let's make serverless event routing more open, transparent, and reliable.
