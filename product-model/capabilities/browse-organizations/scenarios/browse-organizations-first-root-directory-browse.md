---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Effective Root browses the management directory before a default workspace exists."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "An Organization and owner Organization membership are initialized before the directory is returned."
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

# First Root directory browse

## Trigger

Effective Root browses the management directory before a default workspace exists.

## Outcome

An Organization and owner Organization membership are initialized before the directory is returned.
