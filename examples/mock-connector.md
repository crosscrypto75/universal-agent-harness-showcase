# Mock Connector Flow

> **CONCEPTUAL EXAMPLE — NOT A CURRENT CONNECTOR FRAMEWORK**

```text
incoming mailbox event
        |
        v
synthetic normalized event
        |
        v
application chooses a bounded task
        |
        v
Host evaluates policy and context
        |
        v
worker produces a draft or evidence
        |
        v
application or human decides what happens next
```

The example intentionally omits provider credentials, connector code, schemas, vendor-specific behavior, and business rules. A future connector layer should normalize events without becoming a source of authority.
