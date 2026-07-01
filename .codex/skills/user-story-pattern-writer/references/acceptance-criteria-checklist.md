# Acceptance Criteria Checklist

Before finalizing a story, check whether the acceptance criteria cover the relevant items below.

- Happy path: the normal successful user flow.
- Preconditions: required user, system, data, or configuration state before the flow starts.
- Permissions: who can perform the action, who cannot, and what blocked users see.
- Required fields and validations: required vs optional fields, format, length, allowed values, and friendly error text.
- Business rules: product rules, limits, state restrictions, and policy decisions.
- UI behavior: enabled and disabled states, loading states, confirmations, empty states, and inline feedback.
- Error handling: validation errors, failed requests, network failures, timeouts, expired sessions, and unavailable services.
- Edge cases: duplicates, stale data, concurrent edits, inactive records, expired tokens, already-used links, or missing dependencies.
- System outcomes: records created, updated, deleted, invalidated, logged, notified, or left unchanged.
- Postconditions: final state after success and any required audit, notification, or cleanup.

Do not include checklist items that do not apply to the requested story.
