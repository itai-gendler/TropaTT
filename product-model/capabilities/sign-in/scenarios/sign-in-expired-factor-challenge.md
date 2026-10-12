---
kind: "edge"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Continue a password sign-in after the pending factor challenge has expired."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::sign-in"
      rest-public:
        place: "rest::public"
  - text: "The expired challenge cannot establish a record."
    kind: "condition"
    actor: "visitor"
    entities: []
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

# Expired factor challenge

## Trigger

Continue a password sign-in after the pending factor challenge has expired.

## Outcome

The expired challenge cannot establish a session.
