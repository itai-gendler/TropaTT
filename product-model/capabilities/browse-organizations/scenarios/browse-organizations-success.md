---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request the workspace management directory."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "Organization management records are returned within the resolved context."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization"
        effect: "reads"
        facts:
          - "Title"
          - "Slug"
          - "Created at"
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

# Browse organizations: successful operation

## Trigger

Request the workspace management directory.

## Outcome

Organization management records are returned within the resolved context.
