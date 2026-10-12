---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Invalid authentication cannot return personal record information."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work::sessions"
  - text: "Invalid authentication cannot return personal record information."
    kind: "condition"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
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

# Browse sessions: refused or unavailable operation

## Trigger

Invalid authentication cannot return personal session information.

## Outcome

Invalid authentication cannot return personal session information.
