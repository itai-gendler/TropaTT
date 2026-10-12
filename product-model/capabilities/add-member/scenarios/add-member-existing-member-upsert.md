---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Upsert an existing owner through the add-member path with member designation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::organizations"
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization membership access classification changes to member; the dedicated last-owner guard is not applied by upsert."
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

# Existing-member upsert

## Trigger

Upsert an existing owner through the add-member path with member designation.

## Outcome

The Organization membership Role changes to member; the dedicated last-owner guard is not applied by upsert.
