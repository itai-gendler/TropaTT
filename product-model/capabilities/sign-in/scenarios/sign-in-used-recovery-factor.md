---
kind: "validation"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Continue a pending password sign-in using an already-consumed recovery factor."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::sign-in"
      rest-public:
        place: "rest::public"
  - text: "The consumed recovery factor is refused and no record is created."
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

# Used recovery factor

## Trigger

Continue a pending password sign-in using an already-consumed recovery factor.

## Outcome

The consumed recovery factor is refused and no session is created.
