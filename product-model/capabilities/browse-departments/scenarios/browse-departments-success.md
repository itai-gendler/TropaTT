---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request the record directory or addressed record record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::departments"
      rest-work:
        place: "rest::work"
  - text: "Department titles, hierarchy, responsible person and member facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "department"
        effect: "reads"
        facts:
          - "Title"
          - "Code"
          - "Parent"
          - "Manager"
          - "Members"
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

# Browse departments: successful operation

## Trigger

Request the department directory or addressed department record.

## Outcome

Department titles, hierarchy, manager and member facts are returned.
