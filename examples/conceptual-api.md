# Conceptual API Example

> **CONCEPTUAL API EXAMPLE — NOT CURRENT PRODUCTION API**

This synthetic shape illustrates the kind of intent an application might submit. It is not a private TaskContract, schema, or public endpoint specification.

```json
{
  "task": "analyse_document",
  "input": {
    "document": "example.pdf"
  },
  "requestedOutcome": "structured_summary",
  "constraints": ["no external side effects"]
}
```

The Host would be responsible for deciding whether the request is admissible, what authority is granted, which worker path is appropriate, and what evidence is required.
