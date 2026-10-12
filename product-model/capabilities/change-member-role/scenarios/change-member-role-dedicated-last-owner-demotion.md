---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Use the dedicated member-record change to demote the sole remaining owner."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The last-owner guard refuses demotion and the owner designation remains."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
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

# Dedicated last-owner demotion

## Trigger

Use the dedicated member-role change to demote the sole remaining owner.

## Outcome

The last-owner guard refuses demotion and the owner designation remains.
