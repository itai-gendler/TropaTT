---
kind: primary
routes:
  web-work: Web Work
  rest-work: Rest Work
steps:
- text: Request available workspaces for the current identity.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    web-work:
      place: web::work::organizations
    rest-work:
      place: rest::work::organization-directory
- text: Available Organization display records are returned; an empty list remains an empty result.
  kind: product
  actor: root-administrator
  entities:
  - entity: organization
    effect: reads
    facts:
    - Title
    - Slug
  contexts:
    web-work:
      place: web::work::organizations
    rest-work:
      place: rest::work::organization-directory
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/OrganizationService.php
- kind: code
  role: implementation
  target: upload/api/system/library/service/OrganizationContextService.php
- kind: code
  role: implementation
  target: upload/api/system/library/service/InvitationService.php
---

# Browse available organizations: successful operation

## Trigger

Request available workspaces for the current identity.

## Outcome

Available Organization display records are returned; an empty list remains an empty result.
