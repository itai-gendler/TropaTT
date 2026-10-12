---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply changed supported record facts."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::companies"
      rest-work:
        place: "rest::work"
  - text: "The Company facts change through its own addressed service."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "company"
        effect: "changes"
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

# Edit company: successful operation

## Trigger

Supply changed supported company facts.

## Outcome

The Company facts change through its own addressed service.
