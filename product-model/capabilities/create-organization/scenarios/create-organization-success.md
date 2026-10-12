---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title and optional workspace slug."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization is created with the creator's owner membership."
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

# Create organization: successful operation

## Trigger

Supply a title and optional workspace slug.

## Outcome

The Organization is created with the creator's owner membership.
