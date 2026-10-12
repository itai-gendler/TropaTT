---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
steps:
  - text: "An unavailable identifier is absent from the list or returns a not-found response."
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
  - text: "An unavailable identifier is absent from the list or returns a not-found response."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Browse counterparties: refused or unavailable operation

## Trigger

An unavailable identifier is absent from the list or returns a not-found response.

## Outcome

An unavailable identifier is absent from the list or returns a not-found response.
