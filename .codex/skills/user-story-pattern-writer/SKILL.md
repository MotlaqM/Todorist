---
name: user-story-pattern-writer
description: Pattern-backed user story writer. Use when drafting or standardizing Jira-style user stories, acceptance criteria, pre-conditions, or post-conditions with reusable software behavior patterns.
---

# User Story Pattern Writer

## Steps

1. Lock the contract by reading `references/story-format.md`.
   Completion: the output sections and their order are fixed.

2. Set the coverage bar by reading `references/acceptance-criteria-checklist.md`.
   Completion: every relevant coverage category is either used or intentionally skipped.

3. Route the pattern by identifying the feature domain and flow.
   Completion: one primary pattern file is selected, or no matching pattern exists yet.

4. Compose the story from the user's request, the contract, the checklist, and the selected pattern.
   Completion: the story follows the contract and does not include unsupported assumptions.

## Routes

Authentication:
- Use for login, logout, registration, password reset, MFA, session expiry, account lockout, account recovery, and invitation acceptance.
- Read `references/patterns/authentication/index.md`.
- Then read only the flow file named by that index.

## Pruning

- Keep the contract in `story-format.md`.
- Keep coverage categories in `acceptance-criteria-checklist.md`.
- Keep feature behavior in pattern files.
- Do not repeat the same rule in more than one place.
