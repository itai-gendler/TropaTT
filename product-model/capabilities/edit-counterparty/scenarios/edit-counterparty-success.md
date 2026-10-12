---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply changed supported business record facts."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::counterparties"
      rest-work:
        place: "rest::work"
  - text: "The Counterparty facts change through its own addressed service."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "counterparty"
        effect: "changes"
        facts:
          - "Kind"
          - "Title"
          - "Person details"
          - "Legal details"
          - "Tax number"
          - "Bank details"
          - "Email"
          - "Phone"
          - "Address"
          - "Status"
          - "Additional information"
    contexts:
      web-work:
        place: "web::work::counterparties"
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

# Edit counterparty: successful operation

## Trigger

Supply changed supported business record facts.

## Outcome

The Counterparty facts change through its own addressed service.
