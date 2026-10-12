---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a valid person and container record for an addressed workspace."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization membership is added; existing-person upsert is distinguished separately."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-membership"
        effect: "creates"
        facts:
          - "Role"
          - "Joined at"
          - "Account"
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

# Add member: successful operation

## Trigger

Select a valid person and container role for an addressed workspace.

## Outcome

The Organization membership is added; existing-person upsert is distinguished separately.
