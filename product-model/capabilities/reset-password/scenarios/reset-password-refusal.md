---
kind: "validation"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Invalid token or replacement input cannot complete recovery."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::password-reset"
      rest-public:
        place: "rest::public"
  - text: "Invalid token or replacement input cannot complete recovery."
    kind: "condition"
    actor: "visitor"
    entities: []
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

# Reset password: refused or unavailable operation

## Trigger

Invalid token or replacement input cannot complete recovery.

## Outcome

Invalid token or replacement input cannot complete recovery.
