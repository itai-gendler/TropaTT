---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable or no-longer-pending invitation cannot be reissued."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "An unavailable or no-longer-pending invitation cannot be reissued."
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

# Resend organization invitation: refused or unavailable operation

## Trigger

An unavailable or no-longer-pending invitation cannot be reissued.

## Outcome

An unavailable or no-longer-pending invitation cannot be reissued.
