---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create a legal-entity customer through its addressed contract."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::clients"
      rest-work:
        place: "rest::work"
  - text: "A legal-entity Client is created."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "client"
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
        place: "web::work::clients"
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

# Legal entity Client

## Trigger

Create a legal-entity customer through its addressed contract.

## Outcome

A legal-entity Client is created.
