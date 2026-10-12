---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request members of an addressed workspace."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "Organization membership entries and member identities are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-membership"
        effect: "reads"
        facts:
          - "Role"
          - "Joined at"
          - "Account"
      - entity: "account"
        effect: "reads"
        facts:
          - "Name"
          - "Email"
          - "Active"
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

# Browse members: successful operation

## Trigger

Request members of an addressed workspace.

## Outcome

Organization membership entries and member identities are returned.
