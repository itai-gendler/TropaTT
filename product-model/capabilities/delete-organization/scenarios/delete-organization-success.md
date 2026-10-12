---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a workspace to remove."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization and its membership records are removed; no general business-record purge is asserted."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization"
        effect: "removes"
      - entity: "organization-membership"
        effect: "removes"
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

# Delete organization: successful operation

## Trigger

Select a workspace to remove.

## Outcome

The Organization and its membership records are removed; no general business-record purge is asserted.
