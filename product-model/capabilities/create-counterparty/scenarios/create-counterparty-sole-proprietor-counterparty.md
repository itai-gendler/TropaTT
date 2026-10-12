---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create a sole-proprietor business record with supported optional facts."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::counterparties"
      rest-work:
        place: "rest::work"
  - text: "A sole-proprietor Counterparty is created using the common optional fact list."
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

# Sole proprietor Counterparty

## Trigger

Create a sole-proprietor business record with supported optional facts.

## Outcome

A sole-proprietor Counterparty is created using the common optional fact list.
