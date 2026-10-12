---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Supply record scope, code and displayed title."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "A runtime Task status is created."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-status"
        effect: "creates"
        facts:
          - "Code"
          - "Title"
          - "Order"
          - "Active"
          - "Terminal"
          - "WIP limit"
          - "Organization"
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/status/StatusController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/StatusService.php"
---

# Create task status: successful operation

## Trigger

Supply task scope, code and displayed title.

## Outcome

A runtime Task status is created.
