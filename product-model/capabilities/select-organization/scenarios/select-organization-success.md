---
kind: "primary"
routes:
  web-work: "Web Work"
steps:
  - text: "Choose an available workspace for subsequent requests."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
  - text: "The selected Organization is retained as browser request context and subsequent requests carry it."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization"
        effect: "reads"
        facts:
          - "Title"
          - "Slug"
    contexts:
      web-work:
        place: "web::work::organizations"
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

# Select organization: successful operation

## Trigger

Choose an available workspace for subsequent requests.

## Outcome

The selected Organization is retained as browser request context and subsequent requests carry it.
