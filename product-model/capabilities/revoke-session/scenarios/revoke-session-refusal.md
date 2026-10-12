---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable record identifier returns the addressed-record not-found result."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::sessions"
  - text: "An unavailable record identifier returns the addressed-record not-found result."
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

# Revoke session: refused or unavailable operation

## Trigger

An unavailable session identifier returns SESSION_NOT_FOUND.

## Outcome

An unavailable session identifier returns SESSION_NOT_FOUND.
