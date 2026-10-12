---
kind: "validation"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Confirm password recovery using a token older than its two-hour validity."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::password-reset"
      rest-public:
        place: "rest::public"
  - text: "Confirmation fails and the current password remains unchanged."
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

# Expired reset token

## Trigger

Confirm password recovery using a token older than its two-hour validity.

## Outcome

Confirmation fails and the current password remains unchanged.
