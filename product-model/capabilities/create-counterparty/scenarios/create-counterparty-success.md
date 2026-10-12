---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a nonempty displayed name and the supported business record fields."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::counterparties"
      rest-work:
        place: "rest::work"
  - text: "The Counterparty record is created with supplied and default facts."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "counterparty"
        effect: "creates"
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

# Create counterparty: successful operation

## Trigger

Supply a nonempty displayed name and the supported business record fields.

## Outcome

The Counterparty record is created with supplied and default facts.
