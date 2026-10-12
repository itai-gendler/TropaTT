---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Create an invitation using an email already held by an record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The existing email is rejected and no invitation is created."
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

# Existing email invitation

## Trigger

Create an invitation using an email already held by an account.

## Outcome

The existing email is rejected and no invitation is created.
