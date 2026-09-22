# Recovery Principles

External effects are not always immediately knowable. A worker, network connection, or process can fail after an external action may already have succeeded.

```text
action dispatched
       |
connection lost
       |
outcome unknown
       |
DO NOT blindly retry
       |
reconcile / verify / escalate
```

## Why blind retry is unsafe

Repeating an uncertain action can duplicate a payment, mutation, notification, or other consequential effect. A local failure is not evidence that the external side did nothing.

## Conceptual response

1. Preserve the known state and evidence.
2. Classify the outcome as unknown when it cannot be established safely.
3. When appropriate, verify against the external system using a fresh, bounded operation.
4. Reuse an idempotency key only where the external system supports that guarantee.
5. Escalate when neither verification nor safe retry is available.

The private system includes durable lifecycle and reconciliation primitives, but this repository intentionally omits its implementation-specific state model, storage layout, and recovery logic.
