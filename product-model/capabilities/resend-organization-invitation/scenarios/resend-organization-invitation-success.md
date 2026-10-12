---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Select a pending invitation for reissue."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization invitation receives replacement token validity with a seven-day deadline."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "organization-invitation"
        effect: "changes"
        facts:
          - "Expires at"
    contexts:
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

# Resend organization invitation: successful operation

## Trigger

Select a pending invitation for reissue.

## Outcome

The Organization invitation receives replacement token validity with a seven-day deadline.
