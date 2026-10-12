---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply changed supported record person facts."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::contacts"
      rest-work:
        place: "rest::work"
  - text: "The Contact facts change through its own addressed service."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "contact"
        effect: "changes"
        facts:
          - "Name"
          - "Email"
          - "Phone"
          - "Role"
          - "Primary"
          - "Counterparty"
          - "External account"
    contexts:
      web-work:
        place: "web::work::contacts"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ClientService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CompanyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CounterpartyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ContactService.php"
---

# Edit contact: successful operation

## Trigger

Supply changed supported contact person facts.

## Outcome

The Contact facts change through its own addressed service.
