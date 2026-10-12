---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Reparent an addressed record that links an external record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::contacts"
      rest-work:
        place: "rest::work"
  - text: "Contact customer record changes; the linked external Account is deactivated and Session records revoked through the inspected service path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "contact"
        effect: "changes"
        facts:
          - "Counterparty"
      - entity: "account"
        effect: "changes"
        facts:
          - "Active"
      - entity: "session"
        effect: "changes"
        facts:
          - "Revoked at"
        from: "Active"
        to: "Revoked"
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

# Contact reparenting

## Trigger

Reparent an addressed contact that links an external account.

## Outcome

Contact Counterparty changes; the linked external Account is deactivated and Session records revoked through the inspected service path.
