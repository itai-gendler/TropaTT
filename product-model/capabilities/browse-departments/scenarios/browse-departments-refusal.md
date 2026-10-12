---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable record record is absent or returns a not-found result."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::departments"
      rest-work:
        place: "rest::work"
  - text: "An unavailable record record is absent or returns a not-found result."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::departments"
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

# Browse departments: refused or unavailable operation

## Trigger

An unavailable department record is absent or returns a not-found result.

## Outcome

An unavailable department record is absent or returns a not-found result.
