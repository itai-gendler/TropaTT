---
kind: "validation"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "An invalid login/password returns an authentication failure and creates no record."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::sign-in"
      rest-public:
        place: "rest::public"
  - text: "An invalid login/password returns an authentication failure and creates no record."
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

# Sign in: refused or unavailable operation

## Trigger

An invalid login/password returns an authentication failure and creates no session.

## Outcome

An invalid login/password returns an authentication failure and creates no session.
