---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Request invitations for the addressed workspace."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "Organization invitation records and validity information are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-invitation"
        effect: "reads"
        facts:
          - "Email"
          - "Role"
          - "Inviter"
          - "Expires at"
          - "Accepted at"
          - "Revoked at"
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

# Browse organization invitations: successful operation

## Trigger

Request invitations for the addressed workspace.

## Outcome

Organization invitation records and validity information are returned.
