---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "The shipped record requests its own personal profile."
    kind: "actor"
    actor: "manager"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
  - text: "The Account profile is sanitized and returned; this result establishes no work-management privilege."
    kind: "product"
    actor: "manager"
    entities:
      - entity: "account"
        effect: "reads"
        facts:
          - "Login"
          - "Email"
          - "Name"
          - "Language"
          - "Time zone"
          - "Active"
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

# Shipped Manager

## Trigger

The shipped Manager requests its own personal profile.

## Outcome

The Account profile is sanitized and returned; this result establishes no work-management privilege.
