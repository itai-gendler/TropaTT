---
kind: "validation"
routes:
  web-work: "Web Work"
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Missing or invalid authentication cannot revoke a current record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      web-administration:
        place: "web::administration::roles"
      rest-work:
        place: "rest::work::sessions"
  - text: "Missing or invalid authentication cannot revoke a current record."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      web-administration:
        place: "web::administration::roles"
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

# Sign out: refused or unavailable operation

## Trigger

Missing or invalid authentication cannot revoke a current session.

## Outcome

Missing or invalid authentication cannot revoke a current session.
