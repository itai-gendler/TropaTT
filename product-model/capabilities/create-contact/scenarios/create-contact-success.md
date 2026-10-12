---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a nonempty displayed name and the supported record person fields."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::contacts"
      rest-work:
        place: "rest::work"
  - text: "The Contact record is created with supplied and default facts."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "contact"
        effect: "creates"
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

# Create contact: successful operation

## Trigger

Supply a nonempty displayed name and the supported contact person fields.

## Outcome

The Contact record is created with supplied and default facts.
