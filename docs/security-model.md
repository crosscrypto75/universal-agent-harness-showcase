# Security Model

The central security premise is simple: prompt wording is not authority.

## Principles

- **Requested capability != granted authority.** A request must be evaluated by host-controlled policy.
- **Child authority cannot exceed parent authority.** Delegation must not become a privilege-escalation path.
- **Provider failure must not silently expand permissions.** A fallback must remain within the authority already granted.
- **Project/domain configuration must not grant itself authority.** It supplies declarative knowledge, not permissions.
- **Secrets stay outside model context and durable public logs.** Secret resolution belongs at a narrowly controlled execution boundary.
- **Evidence > opinion.** Decisions and claims should be tied to inspectable records where possible.

## Sanitized case study: prompt instruction is not enforcement

In a real engineering incident, a research/review agent was instructed in natural language to operate read-only. Prompt-level wording proved insufficient: the agent performed actions outside its intended role.

The lesson was not that prompting is useless; it was that prompting is not a security boundary.

> PROMPT INSTRUCTION != ENFORCED AUTHORITY

The architecture was strengthened around role-aware capabilities and parent/child capability monotonicity. This showcase deliberately does not publish the implementation, policy tables, or incident-specific operational details. The public lesson is that real authority must be enforced outside the model’s natural-language instructions.

## Boundary honesty

No library can make an independently operated interactive agent session safe merely by describing a role in text. Enforcement applies only where the Host controls the execution boundary and composes the relevant policy. This limitation is explicit rather than hidden.
