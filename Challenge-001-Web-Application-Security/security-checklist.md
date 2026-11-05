
# Web Application Security Checklist

## PHP and MySQL Invoice Application

This checklist summarizes defensive practices studied during Cybersecurity Challenge 001.

**Status note:** These are learning outcomes and recommended controls. A checked item should only be marked implemented or tested after there is evidence confirming it.

## 1. Authentication

- [ ] Hash passwords using PHP `password_hash()`.
- [ ] Verify passwords using `password_verify()`.
- [ ] Implement login rate limiting.
- [ ] Monitor repeated failed login attempts.
- [ ] Use generic login error messages.
- [ ] Regenerate session IDs after successful authentication.

## 2. Database Security

- [ ] Use PDO prepared statements or equivalent parameterized queries.
- [ ] Avoid concatenating untrusted input into SQL statements.
- [ ] Validate incoming data.
- [ ] Use a database account with only the permissions it needs.
- [ ] Avoid exposing database credentials in public repositories.
- [ ] Handle database errors without exposing sensitive internal details.

## 3. Access Control

- [ ] Require authentication on protected pages.
- [ ] Enforce authorization on the server.
- [ ] Verify ownership or permissions before accessing sensitive records.
- [ ] Protect administrative operations.
- [ ] Do not rely on hidden buttons or frontend restrictions for security.

## 4. Session Security

- [ ] Use HTTPS in production.
- [ ] Configure session cookies with `HttpOnly`.
- [ ] Configure session cookies with `Secure` when using HTTPS.
- [ ] Choose an appropriate `SameSite` policy.
- [ ] Regenerate session IDs after login.
- [ ] Set appropriate session expiration.
- [ ] Invalidate sessions during logout.

## 5. Cross-Site Scripting (XSS)

- [ ] Encode untrusted output according to its HTML context.
- [ ] Avoid unsafe insertion of untrusted HTML.
- [ ] Sanitize content where HTML is intentionally allowed.
- [ ] Consider Content Security Policy.
- [ ] Do not assume HttpOnly cookies prevent XSS.

## 6. Additional Security Practices

- [ ] Keep PHP and dependencies updated.
- [ ] Keep secrets outside public source control.
- [ ] Use secure error handling.
- [ ] Back up important application data.
- [ ] Review logs for suspicious activity.
- [ ] Test security controls before deployment.

## 7. Evidence and Verification

For each control, record:

| Control | Evidence | Status |
|---|---|---|
| Password hashing | Code inspection and test | Not verified in this challenge |
| Prepared statements | Query inspection and test | Not verified in this challenge |
| Access control | Protected-page testing | Not verified in this challenge |
| Session configuration | Cookie and session inspection | Not verified in this challenge |
| XSS protection | Input/output testing | Not verified in this challenge |

## Final Reminder

A security checklist is not proof of security.

Controls should be implemented, tested, and reviewed. Do not mark a control as complete merely because it appears in this document.
