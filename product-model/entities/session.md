---
domain: "profile"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/auth/AuthController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/ProfileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/SessionController.php"
---

# Session

Account, device/creation information, expiry and revocation; Active/Revoked; expiry is validity information.

## Information kept

- **Device** — Device and client information.
- **Created at** — Session creation time.
- **Expires at** — Validity deadline.
- **Revoked at** — Explicit revocation time.
- **Account** — Person whose authentication this session represents.

## States

### Active

The session has not been explicitly revoked; its expiry and Account activity separately determine authentication validity.

### Revoked

The session has been explicitly revoked and no longer authenticates.
