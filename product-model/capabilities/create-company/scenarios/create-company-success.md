---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a nonempty displayed name and the supported record fields."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::companies"
      rest-work:
        place: "rest::work"
  - text: "The Company record is created with supplied and default facts."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "company"
        effect: "creates"
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

# Create company: successful operation

## Trigger

Supply a nonempty displayed name and the supported company fields.

## Outcome

The Company record is created with supplied and default facts.
