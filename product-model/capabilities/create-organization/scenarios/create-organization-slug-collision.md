---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create a workspace using a slug already held by another workspace."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "A distinct candidate slug is generated and the Organization is created with its owner Organization membership."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization"
        effect: "creates"
        facts:
          - "Title"
          - "Slug"
          - "Created at"
      - entity: "organization-membership"
        effect: "creates"
        facts:
          - "Role"
          - "Joined at"
          - "Account"
        with: "organization"
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

# Slug collision

## Trigger

Create a workspace using a slug already held by another workspace.

## Outcome

A distinct candidate slug is generated and the Organization is created with its owner Organization membership.
