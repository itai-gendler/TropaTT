---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply the current password and a valid strong replacement."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
  - text: "The Account password is replaced and other sessions are revoked."
    kind: "product"
    actor: "user"
    entities:
      - entity: "account"
        effect: "changes"
        facts:
          - "Password"
      - entity: "session"
        effect: "changes"
        facts:
          - "Revoked at"
        from: "Active"
        to: "Revoked"
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

# Change own password: successful operation

## Trigger

Supply the current password and a valid strong replacement.

## Outcome

The Account password is replaced and other sessions are revoked.
