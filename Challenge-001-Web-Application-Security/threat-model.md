
# Threat Model: PHP/MySQL Invoice Application

## 1. Application Context

The application is a PHP and MySQL invoice management system.

Its functionality includes:
- User authentication.
- Client management.
- Invoice creation and management.
- Payment records.
- Dashboard access.
- Database-backed application data.

This document identifies potential threats based on the application's functionality. It is a learning threat model, not the result of a formal penetration test or complete code audit.

## 2. Assets Worth Protecting

| Asset | Why It Matters |
|---|---|
| User accounts | Prevent unauthorized access |
| Login credentials | Protect account identity |
| Session identifiers | Prevent session misuse |
| Client information | Protect customer confidentiality |
| Invoice records | Preserve financial data integrity |
| Payment records | Protect sensitive transaction information |
| Database | Protect stored application information |

## 3. Trust Boundaries and Attack Surface

Potential entry points include:

- Login forms.
- User-submitted form fields.
- URL parameters.
- Protected dashboard pages.
- Database queries.
- Browser cookies and sessions.

User input crosses into application processing and may eventually reach database queries or HTML output. Each transition requires appropriate validation and security controls.

## 4. Threat Analysis

### Threat 1: Brute-Force Login Attacks

**Target:** Authentication system.

**Threat:** An attacker repeatedly attempts different passwords against an account.

**Potential impact:**
- Unauthorized account access.
- Exposure of client and invoice information.
- Compromise of administrator privileges.

**Recommended controls:**
- Rate limiting.
- Progressive login delays.
- Monitoring repeated failed attempts.
- Strong password hashing.
- Appropriate account protection mechanisms.

### Threat 2: SQL Injection

**Target:** Database queries.

**Threat:** Malicious input is interpreted as part of an SQL statement.

**Potential impact:**
- Unauthorized data access.
- Modification or deletion of records.
- Potential compromise of database operations.

**Recommended controls:**
- Prepared statements with parameter binding.
- Avoid unsafe SQL string concatenation.
- Validate input according to expected data types.
- Apply least-privilege database permissions.

### Threat 3: Broken Access Control

**Target:** Protected pages and application operations.

**Threat:** A user accesses a resource or performs an action without the required authorization.

**Example:** Directly opening `dashboard.php` without a valid authenticated session.

**Potential impact:**
- Unauthorized dashboard access.
- Exposure or modification of protected records.

**Recommended controls:**
- Enforce authentication on protected pages.
- Check authorization on the server for every sensitive operation.
- Verify that users can access only resources they are permitted to use.

### Threat 4: Session Hijacking

**Target:** Authentication sessions.

**Threat:** An attacker obtains or misuses a valid session identifier.

**Potential impact:**
- Impersonation of an authenticated user.
- Unauthorized access to protected functionality.

**Recommended controls:**
- HTTPS.
- Secure session cookie configuration.
- Session ID regeneration after authentication.
- Session expiration and invalidation.
- Protection against cross-site scripting.

### Threat 5: Cross-Site Scripting (XSS)

**Target:** Browser-rendered application content.

**Threat:** Untrusted content is interpreted as executable JavaScript in another user's browser.

**Potential impact:**
- Unauthorized browser actions.
- Access to information exposed to JavaScript.
- Abuse of an authenticated user's session.

**Recommended controls:**
- Context-aware output encoding.
- Safe handling of user-generated content.
- Avoid unsafe DOM manipulation.
- Apply Content Security Policy where appropriate.
- Keep session cookies HttpOnly.

## 5. Important Session and Cookie Concepts

| Attribute | Purpose |
|---|---|
| HttpOnly | Prevents JavaScript from directly reading the cookie |
| Secure | Restricts cookie transmission to HTTPS |
| SameSite | Helps mitigate cross-site request forgery (CSRF) |

**Important distinction:** HttpOnly does not prevent XSS. Malicious JavaScript running in an authenticated browser may still perform actions through that browser because eligible cookies can be attached automatically to same-origin requests.

## 6. Risk Summary

| Threat | Main Security Concern |
|---|---|
| Brute force | Account compromise |
| SQL injection | Database compromise |
| Broken access control | Unauthorized resource access |
| Session hijacking | Account impersonation |
| XSS | Malicious browser-side execution |

## 7. Conclusion

Threat modelling helps developers identify what needs protection, where attacks may occur, and which defensive controls should be considered.

Security should be considered throughout application development rather than added only after a vulnerability is discovered.
