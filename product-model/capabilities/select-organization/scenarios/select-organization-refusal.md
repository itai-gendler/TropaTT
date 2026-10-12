---
kind: "validation"
routes:
  web-work: "Web Work"
steps:
  - text: "An unavailable choice does not establish a valid selected workspace."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
  - text: "An unavailable choice does not establish a valid selected workspace."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationContextService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/InvitationService.php"
---

# Select organization: refused or unavailable operation

## Trigger

An unavailable choice does not establish a valid selected workspace.

## Outcome

An unavailable choice does not establish a valid selected workspace.
