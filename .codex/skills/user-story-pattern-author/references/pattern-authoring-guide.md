# Pattern Authoring Guide

A pattern is reusable product-behavior guidance for a common software domain or flow.

Patterns are not user stories. They are not final acceptance criteria. They give the writer skill the usual behavior to consider while still adapting to the user's request and product-specific rules.

## Pattern Library Shape

Each domain lives in its own folder:

```txt
[pattern-root]/[domain]/
```

Examples:
- `patterns/authentication/`
- `patterns/notifications/`
- `patterns/file-upload/`
- `patterns/approval-workflows/`

When patterns are later installed into the writer skill, the pattern root may become:

```txt
user-story-pattern-writer/references/patterns/
```

Installed examples:
- `authentication/`
- `notifications/`
- `file-upload/`
- `approval-workflows/`

Each domain folder may contain:
- `index.md`: the routing map for that domain.
- One flow file per authored product flow.
- Shared files only after behavior is reused by multiple flows.

Create files lazily. Do not create empty flow files just because the index mentions a future branch.

## Index Files

An index is a routing map, not a requirements document.

Use it to help the writer skill choose which flow file to read. Keep detailed happy paths, validations, UI behavior, error handling, and postconditions out of the index.

Every index branch uses:
- `Use when`
- `Signals`
- `Read`
- `Also consider`
- `Do not assume`

## Flow Files

A flow file describes reusable behavior for one common product flow.

Write flow files as guidance, not as a finished ticket. The writer skill will combine the flow guidance with the user's request and the fixed story format.

Every flow file uses:
- `Scope`
- `Usually include`
- `Happy path`
- `Preconditions`
- `Permissions`
- `Validations`
- `UI behavior`
- `Error handling`
- `Edge cases`
- `Postconditions`
- `Do not assume`

## Product-Focused Language

Use product-focused language. Include constraints that affect user behavior, system outcomes, security, validation, permissions, or acceptance criteria.

Avoid naming implementation technologies, storage mechanisms, frameworks, APIs, queues, databases, or infrastructure unless the user explicitly asks for technical acceptance criteria.

Prefer:
- Reset links expire after the configured time window.
- The same reset link cannot be used more than once.
- Delivery failure gives the user a retry path.

Avoid:
- Store reset tokens in Redis with a TTL.
- Publish the notification to Kafka.
- Add an endpoint that returns HTTP 500.

## Settled Behavior

Write settled behavior directly into the relevant section.

If behavior is undecided, do not invent a rule. Put the uncertainty under `Do not assume`, or ask one focused question when the missing decision changes the pattern structure.

## Shared Files

Create a shared file only when the same behavior appears across multiple flows.

Good shared-file candidates:
- password policy
- email delivery
- session handling
- rate limiting
- audit logging

Do not extract shared files early. Start inside the flow file, then extract when repetition appears.

## Source of Truth

- `index-template.md` is the source of truth for domain indexes.
- `flow-template.md` is the source of truth for flow files.
- Examples show tone and density, not alternate structure.
