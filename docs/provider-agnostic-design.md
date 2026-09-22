# Provider-Agnostic Design

Provider-agnostic does not mean every provider is implemented. It means application semantics should not depend on a single model vendor, CLI, or model identifier.

## Architecture

The architecture uses replaceable adapter boundaries so a Host can make an explicit routing and execution decision. Provider-specific behavior belongs at the edge; task intent, authority, validation, and recovery semantics remain independent of a particular provider.

## Current demonstrated implementation

The private implementation currently demonstrates narrow supervised subprocess paths:

- Claude CLI for Builder/Corrector work
- Codex CLI for Validator work

These are bounded, read-only worker paths with catalogued capabilities. They are not a universal provider SDK, a generic connector ecosystem, a claim of Gemini/GLM/local-model support, or provider failover.

## Intended extension

Additional providers can be introduced through replaceable adapter boundaries after their capabilities, failure behavior, and permission limits are demonstrated and reviewed. A new provider should not require rewriting application business logic or relaxing authority controls.
