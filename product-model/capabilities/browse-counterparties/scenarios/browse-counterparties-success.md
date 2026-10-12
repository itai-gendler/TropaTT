---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
steps:
  - text: "Read the addressed business record collection or selected record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::counterparties"
      rest-work:
        place: "rest::work"
      web-detail:
        place: "web::work::counterparty-detail"
  - text: "The Counterparty facts are returned within its addressed contract."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "counterparty"
        effect: "reads"
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
      web-detail:
        place: "web::work::counterparty-detail"
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

# Browse counterparties: successful operation

## Trigger

Read the addressed business record collection or selected record.

## Outcome

The Counterparty facts are returned within its addressed contract.
