---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read the addressed record person collection or selected record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::contacts"
      rest-work:
        place: "rest::work"
  - text: "The Contact facts are returned within its addressed contract."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "contact"
        effect: "reads"
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

# Browse contacts: successful operation

## Trigger

Read the addressed contact person collection or selected record.

## Outcome

The Contact facts are returned within its addressed contract.
