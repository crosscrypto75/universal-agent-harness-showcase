# Universal Agent Harness — Public Technical Showcase

This repository documents the architectural approach behind a private implementation for bounded, auditable agent work. It is a showcase of engineering principles and sanitized demonstrations, not an open-source release or a runnable clone of the private product.

## The problem

Useful AI systems must combine probabilistic reasoning with deterministic controls. An agent may draft, analyze, or review effectively, but it should not receive authority merely because it was asked to act. The Harness is designed to make work explicit, bounded, observable, and recoverable.

## Conceptual architecture

```text
Existing Application
        |
        v
Control Surface / Integration (planned productization)
        |
        v
Local Agent Host
        |
        v
Universal Agent Harness
   /       |        \
Policy   Routing   Context
   |        |        |
   +--------+--------+
            |
         Workers
     /             \
 Builder          Validator
     |              |
     +------> Evidence
                |
              Audit
```

The current implementation is a tested library and local-host prototype. A public Control API, external connector framework, CLI product surface, dashboard, and network service are planned productization work—not shipped interfaces.

## Why these boundaries matter

- **Provider-agnostic architecture:** applications should not be designed around one model vendor. Current demonstrated paths are deliberately narrow: Claude CLI for Builder/Corrector work and Codex CLI for Validator work. Additional providers are an adapter-boundary goal, not a claim of current support.
- **Bounded permissions:** requested capability is not granted authority. Parent/child authority must remain monotonic, and provider failure must not expand permissions.
- **Independent validation:** generation and validation have different incentives. Builder and Validator responsibilities are intentionally separated, with evidence retained for review.
- **Deterministic control:** rules, authorization, persistence, and lifecycle boundaries should be deterministic where possible; model reasoning is used where it adds value.
- **Honest recovery:** if an external outcome is uncertain, the correct next step is reconcile, verify, or escalate—not blind retry.

## Current implementation status

Implemented in the private system:

- Deterministic task lifecycle, policy/capability checks, audit evidence, and durable attempts
- Builder / Corrector / Validator mission paths with review gating
- Role-aware capabilities and parent/child authority monotonicity helpers
- Provider routing with supervised Claude and Codex worker paths
- Durable worker handling, continuation, recovery, and reconciliation primitives
- Auditable context routing, context budgeting, and controlled memory-retrieval planning
- Local SQLite and in-memory persistence plus deterministic test coverage

Deliberately incomplete or not implemented:

- Public Control API, HTTP/RPC service, connector framework, CLI commands, dashboard, and SaaS deployment
- Provider failover, cost/value optimization, learned scoring, and a second proven execution strategy
- A general project-pack marketplace or public application workflow product

## Why the implementation is private

The production implementation contains proprietary engineering details and is not published here. This showcase intentionally omits source code, private schemas, policies, routing rules, prompts, recovery algorithms, store designs, credentials, paths, and business/application logic. It presents the architectural reasoning without making the private system reconstructable.

## Read the showcase

- [Architecture](docs/architecture.md)
- [Security model](docs/security-model.md)
- [Provider-agnostic design](docs/provider-agnostic-design.md)
- [Recovery principles](docs/recovery-principles.md)
- [Integration model](docs/integration-model.md)
- [Sanitized conceptual examples](examples/)

## Scope note

All examples are conceptual and synthetic. They are not current production APIs, schemas, configuration formats, or implementation guidance.
