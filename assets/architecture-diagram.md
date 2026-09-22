# Architecture Diagram Notes

```text
Application intent
       |
       v
Host-controlled boundary
  /        |         \
policy   context    routing
  \        |         /
       bounded worker work
          /       \
      Builder    Validator
          \       /
           evidence
              |
            audit
```

This diagram is conceptual. It communicates separation of concerns, not internal modules, classes, protocols, or production deployment topology.
