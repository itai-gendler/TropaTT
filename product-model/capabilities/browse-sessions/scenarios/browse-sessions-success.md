---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request the current authentication's record information."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work::sessions"
  - text: "Session information is returned; Web presents its own summary."
    kind: "product"
    actor: "user"
    entities:
      - entity: "session"
        effect: "reads"
        facts:
          - "Device"
          - "Created at"
          - "Expires at"
          - "Revoked at"
          - "Account"
    contexts:
      web-work:
        place: "web::work::profile"
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

# Browse sessions: successful operation

## Trigger

Request the current authentication's session information.

## Outcome

Session information is returned; Web presents its own summary.
