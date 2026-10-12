---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable directory record is absent or returns a not-found result."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::teams"
      rest-work:
        place: "rest::work"
  - text: "An unavailable directory record is absent or returns a not-found result."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::teams"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TeamService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/DepartmentService.php"
---

# Browse teams: refused or unavailable operation

## Trigger

An unavailable directory record is absent or returns a not-found result.

## Outcome

An unavailable directory record is absent or returns a not-found result.
