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

## Logout

Use when:
- The story involves ending an authenticated session or signing out of the system.

Signals:
- logout
- log out
- sign out
- end session
- terminate session

Read:
- `logout.md`

Also consider:
- Shared session handling guidance when added.

Do not assume:
- Logout ends sessions on all devices.
- The user is redirected to a specific page.

## Registration

Use when:
- The story involves creating a new account through a self-service signup flow.

Signals:
- register
- registration
- sign up
- create account
- new account

Read:
- `registration.md`

Also consider:
- Shared password policy guidance when added.
- Shared email verification guidance when added.
- Shared notification or email delivery guidance when added.

Do not assume:
- Public registration is allowed.
- Email verification is required.
- Account approval is required.

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

## Change Password

Use when:
- The story involves an authenticated user changing their current password from account settings or profile security settings.

Signals:
- change password
- update password
- current password
- account security
- profile security

Read:
- `change-password.md`

Also consider:
- Shared password policy guidance when added.
- Shared session handling guidance when added.
- Shared notification or email delivery guidance when added.

Do not assume:
- Existing sessions are revoked.
- Admins can change another user's password through this flow.
- Password change is allowed without current-password confirmation.

## MFA Setup

Use when:
- The story involves enabling, configuring, verifying, or disabling a second authentication factor.

Signals:
- MFA
- multi-factor authentication
- two-factor authentication
- 2FA
- authenticator app
- verification code
- backup code

Read:
- `mfa-setup.md`

Also consider:
- Shared recovery guidance when added.
- Shared notification or email delivery guidance when added.

Do not assume:
- MFA is mandatory for all users.
- SMS, email, authenticator apps, or backup codes are all supported.
- Disabling MFA is allowed without additional verification.

## MFA Challenge

Use when:
- The story involves verifying a second factor during login, step-up authentication, or sensitive account actions.

Signals:
- MFA challenge
- 2FA code
- verification code
- one-time code
- step-up authentication
- trusted device

Read:
- `mfa-challenge.md`

Also consider:
- Shared session handling guidance when added.
- Shared account lockout guidance when added.

Do not assume:
- A trusted-device option exists.
- Backup codes are available.
- Failed MFA attempts lock the whole account.

## Session Expiry

Use when:
- The story involves inactivity timeout, expired sessions, forced reauthentication, or session renewal.

Signals:
- session expiry
- session timeout
- inactivity timeout
- reauthenticate
- remember me
- stay signed in

Read:
- `session-expiry.md`

Also consider:
- Shared notification or warning guidance when added.

Do not assume:
- A warning appears before expiry.
- Sessions refresh automatically.
- Session duration is the same for every role or device.

## Account Lockout

Use when:
- The story involves blocking access after repeated failed attempts or other security-risk conditions.

Signals:
- account lockout
- locked account
- failed login attempts
- too many attempts
- suspicious activity

Read:
- `account-lockout.md`

Also consider:
- Shared notification or email delivery guidance when added.
- Shared admin unlock guidance when added.

Do not assume:
- Lockout is permanent.
- Admin unlock is available.
- The user is told exactly which security rule triggered the lock.

## Invitation Acceptance

Use when:
- The story involves an invited user accepting an invitation and activating or joining an account, organization, team, or workspace.

Signals:
- invite
- invitation
- accept invite
- join workspace
- join organization
- invited user

Read:
- `invitation-acceptance.md`

Also consider:
- Shared registration guidance when added.
- Shared password policy guidance when added.
- Shared role and permission guidance when added.

Do not assume:
- The invited user already has an account.
- Invitations can be reused.
- Invitation acceptance automatically grants admin access.
