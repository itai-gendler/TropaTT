---
kind: "validation"
routes:
  rest-public: "Rest Public"
steps:
  - text: "An invalid, expired or already-used token prevents acceptance."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      rest-public:
        place: "rest::public"
  - text: "An invalid, expired or already-used token prevents acceptance."
    kind: "condition"
    actor: "visitor"
    entities: []
    contexts:
      rest-public:
        place: "rest::public"
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

# Accept organization invitation: refused or unavailable operation

## Trigger

An invalid, expired or already-used token prevents acceptance.

## Outcome

An invalid, expired or already-used token prevents acceptance.
