# Example Run

> **SYNTHETIC DEMONSTRATION — NOT A PRODUCTION TRACE**

```text
1. Application submits a document-analysis request.
2. Host evaluates the requested scope against policy.
3. A Builder produces a bounded draft.
4. A separate Validator evaluates the draft against requested evidence.
5. The result and supporting evidence are retained for the caller.
6. If an external outcome is uncertain, the run is not blindly repeated.
```

This is a conceptual sequence. It intentionally does not expose private state names, policy decisions, route selection rules, prompts, artifact formats, or recovery implementation details.
