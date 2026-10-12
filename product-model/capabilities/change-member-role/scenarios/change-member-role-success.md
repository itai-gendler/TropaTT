---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a member and a valid replacement container record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization membership access classification changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-membership"
        effect: "changes"
        facts:
          - "Role"
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

# Change member role: successful operation

## Trigger

Select a member and a valid replacement container role.

## Outcome

The Organization membership role changes.
