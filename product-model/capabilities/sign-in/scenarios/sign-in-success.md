---
kind: "primary"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Supply a valid login and password without a required factor continuation."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::sign-in"
      rest-public:
        place: "rest::public"
  - text: "A new active Session and authentication credential are returned."
    kind: "product"
    actor: "visitor"
    entities:
      - entity: "session"
        effect: "creates"
        facts:
          - "Device"
          - "Created at"
          - "Expires at"
          - "Revoked at"
          - "Account"
        to: "Active"
    contexts:
      web-public:
        place: "web::public::sign-in"
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

# Sign in: successful operation

## Trigger

Supply a valid login and password without a required factor continuation.

## Outcome

A new active Session and authentication credential are returned.
