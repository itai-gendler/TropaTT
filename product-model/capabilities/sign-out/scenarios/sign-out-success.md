---
kind: "primary"
routes:
  web-work: "Web Work"
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Submit the sign-out request using the current authentication."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      web-administration:
        place: "web::administration::roles"
      rest-work:
        place: "rest::work::sessions"
  - text: "The current Session is revoked; sign-in is required for subsequent authenticated requests."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "session"
        effect: "changes"
        facts:
          - "Revoked at"
        from: "Active"
        to: "Revoked"
    contexts:
      web-work:
        place: "web::work::profile"
      web-administration:
        place: "web::administration::roles"
      rest-work:
        place: "rest::work::sessions"
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

# Sign out: successful operation

## Trigger

Submit the sign-out request using the current authentication.

## Outcome

The current Session is revoked; sign-in is required for subsequent authenticated requests.
