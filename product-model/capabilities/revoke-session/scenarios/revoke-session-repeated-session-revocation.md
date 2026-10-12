---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Repeat individual revocation of an already-revoked record identifier."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::sessions"
  - text: "The implemented the addressed-record not-found result or unavailable result is returned."
    kind: "condition"
    actor: "user"
    entities: []
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

# Repeated session revocation

## Trigger

Repeat individual revocation of an already-revoked session identifier.

## Outcome

The implemented SESSION_NOT_FOUND or unavailable result is returned.
