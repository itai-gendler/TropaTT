---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Select an active record identifier for individual revocation."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::sessions"
  - text: "The addressed Session is revoked."
    kind: "product"
    actor: "user"
    entities:
      - entity: "session"
        effect: "changes"
        facts:
          - "Revoked at"
        from: "Active"
        to: "Revoked"
    contexts:
      rest-work:
        place: "rest::work::sessions"
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
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/UserProfileService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SessionService.php"
---

# Revoke session: successful operation

## Trigger

Select an active session identifier for individual revocation.

## Outcome

The addressed Session is revoked.
