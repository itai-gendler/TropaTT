---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an addressed record record for deletion."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::companies"
      rest-work:
        place: "rest::work"
  - text: "The Company record is removed through its contract-specific path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "company"
        effect: "removes"
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

# Delete company: successful operation

## Trigger

Select an addressed company record for deletion.

## Outcome

The Company record is removed through its contract-specific path.
