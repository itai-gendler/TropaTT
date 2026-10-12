---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Reissue an existing pending record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::organization-directory"
  - text: "The Organization invitation receives a replacement token and seven-day expiry; its old token no longer accepts."
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

# Resend invitation

## Trigger

Reissue an existing pending organization invitation.

## Outcome

The Organization invitation receives a replacement token and seven-day expiry; its old token no longer accepts.
