# Authentication Pattern Index

Routing rule:
- Read only the flow files needed for the requested authentication behavior.
- Prefer one primary flow file plus clearly relevant shared files when they exist.
- Do not load the full authentication folder.

Shared files:
- None yet.

## Login

Use when:
- The story involves a user signing in, starting an authenticated session, or accessing the system with credentials.

Signals:
- login
- log in
- sign in
- authenticate
- credentials
- SSO login

Read:
- `login.md`

Also consider:
- Shared session handling guidance when added.
- Shared MFA guidance when added.

Do not assume:
- MFA is required.
- SSO is available.
- Users remain signed in across browser sessions.

## Password Reset

Use when:
- The story involves forgotten passwords, reset links, reset codes, account recovery, or setting a new password after identity verification.

Signals:
- forgot password
- reset password
- password recovery
- reset link
- reset code
- set new password

Read:
- `password-reset.md`

Also consider:
- Shared password policy guidance when added.
- Shared notification or email delivery guidance when added.
- Shared session handling guidance when added.

Do not assume:
- The system reveals whether an email address exists.
- Existing sessions are revoked after reset.
- MFA or identity verification is required beyond the reset flow.
