---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Submit a nonempty email differing from the current profile email."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
  - text: "EMAIL_CHANGE_REQUIRES_VERIFICATION is returned; the current email and accompanying unsaved changes remain unchanged."
    kind: "condition"
    actor: "user"
    entities: []
    contexts:
      web-work:
        place: "web::work::profile"
      rest-work:
        place: "rest::work"
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

# Changed nonempty email

## Trigger

Submit a nonempty email differing from the current profile email.

## Outcome

EMAIL_CHANGE_REQUIRES_VERIFICATION is returned; the current email and accompanying unsaved changes remain unchanged.
