---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Invalid identity cannot return a personal profile."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
  - text: "Invalid identity cannot return a personal profile."
    kind: "condition"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
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

# Read own profile external observer boundary

## Trigger

Invalid identity cannot return a personal profile.

## Outcome

Invalid identity cannot return a personal profile.
