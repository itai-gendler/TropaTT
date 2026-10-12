---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request the group directory or addressed group record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::teams"
      rest-work:
        place: "rest::work"
  - text: "Team titles, hierarchy, responsible person and member facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "team"
        effect: "reads"
        facts:
          - "Title"
          - "Type"
          - "Code"
          - "Parent"
          - "Creator"
          - "Manager"
          - "Members"
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

# Browse teams: successful operation

## Trigger

Request the group directory or addressed group record.

## Outcome

Team titles, hierarchy, manager and member facts are returned.
