---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create an individual business record with supported optional personal facts."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::counterparties"
      rest-work:
        place: "rest::work"
  - text: "An individual Counterparty is created using the common optional fact list."
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

# Individual Counterparty

## Trigger

Create an individual business record with supported optional personal facts.

## Outcome

An individual Counterparty is created using the common optional fact list.
