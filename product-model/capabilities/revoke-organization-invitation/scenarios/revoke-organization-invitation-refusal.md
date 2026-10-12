---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable invitation cannot be revoked."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "An unavailable invitation cannot be revoked."
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

# Revoke organization invitation: refused or unavailable operation

## Trigger

An unavailable invitation cannot be revoked.

## Outcome

An unavailable invitation cannot be revoked.
