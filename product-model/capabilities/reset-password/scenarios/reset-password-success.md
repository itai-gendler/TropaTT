---
kind: "primary"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Confirm recovery with a valid, unconsumed token and a strong replacement password."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::password-reset"
      rest-public:
        place: "rest::public"
  - text: "The Account password is replaced, the recovery token consumed and its sessions revoked."
    kind: "product"
    actor: "visitor"
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
      web-public:
        place: "web::public::password-reset"
      rest-public:
        place: "rest::public"
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

# Reset password: successful operation

## Trigger

Confirm recovery with a valid, unconsumed token and a strong replacement password.

## Outcome

The Account password is replaced, the recovery token consumed and its sessions revoked.
