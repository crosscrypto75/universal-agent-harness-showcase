# Architecture

The Harness is a library-first architecture for bounded agent execution. It separates application intent, host-owned control, and worker reasoning so that an AI worker cannot define its own authority.

## Conceptual layers

| Layer | Responsibility | Boundary |
|---|---|---|
| Existing application | Defines business intent and owns its domain | Does not delegate unrestricted authority to a model |
| Integration surface | Future API/SDK or connector entry point | Planned; not a current product interface |
| Local Host | Composes policy, persistence, routing, and worker supervision | Owns activation decisions |
| Harness | Manages bounded lifecycle, evidence, validation, and recovery semantics | Domain-neutral; not a business application |
| Workers | Perform constrained Builder or Validator tasks | Produce evidence, not self-issued authority |

## Design choices

The architecture favors explicit state and evidence over conversational assumptions. A task is validated and authorized before work proceeds; decisions and outcomes are retained so a later reviewer or recovery process has something concrete to inspect.

The current private implementation demonstrates deterministic lifecycle handling, policy/capability checks, durable records, worker supervision, routing, context controls, and separated Builder/Corrector/Validator paths. It is not a deployed service, public API, dashboard, or general integration platform.

## Project and domain configuration

Domain configuration can describe context, validation needs, and task-relevant references. It must not grant itself permissions, choose unrestricted tools, or override host policy. This preserves a key distinction: configuration describes work; the host controls authority.
