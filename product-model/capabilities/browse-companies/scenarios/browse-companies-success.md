---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read the addressed record collection or selected record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::companies"
      rest-work:
        place: "rest::work"
  - text: "The Company facts are returned within its addressed contract."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "company"
        effect: "reads"
        facts:
          - "Title"
          - "Status"
          - "Email"
          - "Tax number"
    contexts:
      web-work:
        place: "web::work::companies"
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

# Browse companies: successful operation

## Trigger

Read the addressed company collection or selected record.

## Outcome

The Company facts are returned within its addressed contract.
