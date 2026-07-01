# Password Reset

Scope:
- Covers account recovery by reset link, reset code, or equivalent reset challenge.
- Covers requesting the reset, validating the reset challenge, setting a new password, and completing the reset.
- Does not cover authenticated password change; use `change-password.md` for that flow.

Usually include:

Happy path:
- User starts from the unauthenticated access flow, usually from login.
- User submits a recovery identifier such as email, username, or phone number.
- System accepts the request and sends a reset link or code when the account is eligible.
- User opens the reset link or enters the reset code before it expires.
- User enters a new password and confirms it when confirmation is part of the UI.
- System validates the reset challenge and password, updates the password, and confirms completion.

Preconditions:
- Password reset is enabled for the product, tenant, or account type.
- The user is unauthenticated or unable to access the account.
- A recovery channel exists if the flow depends on email, SMS, or another delivery method.
- The account is eligible for password reset under the product's account-state rules.

Permissions:
- Unauthenticated users may request password reset.
- A reset challenge authorizes only the account it was issued for.
- Users may reset only their own account password through this flow.
- Admin or support users must not see the user's password, reset link, reset code, or token secret.

Validations:
- Recovery identifier is required when the flow asks for one.
- Recovery identifier format is validated when the identifier type is known.
- Reset link, code, or token must be valid, unexpired, unused, and associated with the intended account.
- New password is required.
- New password must satisfy the product password policy.
- Confirm password is required when present.
- Confirm password must match the new password.

UI behavior:
- Password reset entry point is discoverable from the login flow.
- Request action is disabled while required fields are empty or invalid.
- Submission shows a loading state and prevents duplicate submits while processing.
- Success confirmation after reset request does not expose sensitive account details.
- Reset form clearly shows password requirements before or during password entry.
- Password validation feedback appears near the password field when the user can act on it.
- Recoverable errors preserve safe user-entered values.
- Successful password reset moves the user to the next intended step, usually login or signed-in access depending on product policy.

Error handling:
- Missing recovery identifier shows a friendly required-field message.
- Invalid recovery identifier format shows a friendly format message.
- Unknown or ineligible account handling follows product security policy and avoids unnecessary account disclosure.
- Expired, invalid, or already-used reset challenge shows a recovery path to request a new one.
- Weak password shows the specific password rule that failed.
- Password confirmation mismatch shows a clear mismatch message.
- Too many reset requests or attempts shows a wait or retry message without exposing security-rule internals.
- Delivery failure shows a retry path without exposing sensitive account information.
- Network or service failure preserves safe input and lets the user retry.

Edge cases:
- Multiple reset requests for the same account.
- Several valid reset links or codes issued close together.
- Reset attempted after password was already changed.
- Reset attempted for inactive, locked, invited, disabled, deleted, or externally managed accounts.
- Reset attempted after the user's session expires during the flow.
- Reset request submitted repeatedly by refresh, back button, or double-click.
- Password manager autofill into new password and confirm password fields.

Postconditions:
- Password is updated only after a valid reset challenge and valid new password.
- Used reset challenge cannot be reused.
- Superseded reset challenges are invalidated when product policy requires it.
- Security-relevant event is recorded when audit logging exists.
- Confirmation or security notification is sent when notification policy requires it.
- User lands in the product-defined completion state, such as login, confirmation screen, or authenticated session.

Do not assume:
- The system reveals whether the recovery identifier belongs to an account.
- Reset is email-based; SMS, code-based, admin-issued, or identity-provider flows may exist.
- A specific expiry duration for links or codes.
- Existing sessions are revoked after password reset.
- Password history is checked.
- MFA, security questions, or additional identity verification are required.
- The user is automatically signed in after resetting the password.
