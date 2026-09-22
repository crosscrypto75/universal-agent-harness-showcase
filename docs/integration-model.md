# Integration Model

The intended product direction is to add bounded AI capability to existing software rather than require a business to rebuild itself around an AI platform.

## Intended direct integration

```text
Existing software
       |
API / SDK (planned)
       |
Local Host
       |
Harness
```

An application would submit a scoped task and receive evidence or a bounded outcome. The application continues to own business data, user experience, final authorization, and operational policy.

## Intended legacy and event-driven integration

```text
Email / Folder / Webhook / ERP
       |
Connector (planned)
       |
Normalized event
       |
Intake / workflow selection
       |
Harness
```

The connector framework and Control API are productization targets, not currently shipped interfaces. This matters because integration claims should be as bounded as agent-permission claims.

## Practical division of responsibility

- AI: interpretation, drafting, classification, bounded analysis
- Deterministic systems: rules, reconciliation, authorization, persistence, and audit
- Humans: approval, exception handling, and decisions where confidence or authority is insufficient
