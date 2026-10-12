---
kind: "primary"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Continue a valid pending password sign-in using an unused valid factor."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::sign-in"
      rest-public:
        place: "rest::public"
  - text: "The pending sign-in completes and an active Session is established."
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

# Sign in with a second factor

## Trigger

Continue a valid pending password sign-in using an unused valid factor.

## Outcome

The pending sign-in completes and an active Session is established.
