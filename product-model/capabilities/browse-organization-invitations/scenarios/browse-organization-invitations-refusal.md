---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable workspace cannot return its invitations."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "An unavailable workspace cannot return its invitations."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
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

# Browse organization invitations: refused or unavailable operation

## Trigger

An unavailable workspace cannot return its invitations.

## Outcome

An unavailable workspace cannot return its invitations.
