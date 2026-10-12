---
kind: "primary"
routes:
  web-public: "Web Public"
  rest-public: "Rest Public"
steps:
  - text: "Request password recovery with an identifier, without a confirmation token."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      web-public:
        place: "web::public::password-reset"
      rest-public:
        place: "rest::public"
  - text: "The generic reset request is accepted without returning or delivering the plaintext token; record existence is not disclosed."
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

# Generic reset request

## Trigger

Request password recovery with an identifier, without a confirmation token.

## Outcome

The generic reset request is accepted without returning or delivering the plaintext token; account existence is not disclosed.
