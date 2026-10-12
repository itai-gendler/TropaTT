---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply a new email, admin or member designation and valid expiry days."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "A pending Organization invitation is kept and its invitation information returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-invitation"
        effect: "creates"
        facts:
          - "Email"
          - "Role"
          - "Inviter"
          - "Expires at"
          - "Accepted at"
          - "Revoked at"
        to: "Pending"
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

# Create organization invitation: successful operation

## Trigger

Supply a new email, admin or member designation and valid expiry days.

## Outcome

A pending Organization invitation is kept and its invitation information returned.
