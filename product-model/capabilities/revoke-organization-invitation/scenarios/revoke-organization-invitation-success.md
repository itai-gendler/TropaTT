---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Select a pending invitation for revocation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization invitation becomes revoked."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-invitation"
        effect: "changes"
        facts:
          - "Revoked at"
        from: "Pending"
        to: "Revoked"
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

# Revoke organization invitation: successful operation

## Trigger

Select a pending invitation for revocation.

## Outcome

The Organization invitation becomes revoked.
