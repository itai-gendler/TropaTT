---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Invalid email, record or expiry input is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "Invalid email, record or expiry input is rejected."
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

# Create organization invitation: refused or unavailable operation

## Trigger

Invalid email, role or expiry input is rejected.

## Outcome

Invalid email, role or expiry input is rejected.
