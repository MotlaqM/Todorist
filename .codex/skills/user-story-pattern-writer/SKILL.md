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

4. Load relevant preferences.
   Completion: `references/preferences/README.md` is read, and any preference file matching the selected domain or component is read.

5. Compose the story from the user's request, the contract, the checklist, the selected pattern, and relevant preferences.
   Completion: the story follows the contract, applies relevant defaults, and does not include unsupported assumptions.

## Routes

Authentication:
- Use for login, logout, registration, password reset, MFA, session expiry, account lockout, account recovery, and invitation acceptance.
- Read `references/patterns/authentication/index.md`.
- Then read only the flow file named by that index.
- Read `references/preferences/authentication.md`.

List views:
- Use for tables, record lists, searchable lists, filtered lists, paginated lists, and row-based navigation.
- Read `references/preferences/list-views.md`.

Forms:
- Use for create, edit, submit, validate, save, cancel, and multi-step form behavior.
- Read `references/preferences/forms.md`.

Notifications:
- Use for email, SMS, push, in-app notifications, reminders, delivery status, notification preferences, and notification history.
- Read `references/preferences/notifications.md`.

## Pruning

- Keep the contract in `story-format.md`.
- Keep coverage categories in `acceptance-criteria-checklist.md`.
- Keep feature behavior in pattern files.
- Keep reusable default decisions in preference files.
- Do not repeat the same rule in more than one place.
