---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Request the record-scope status dictionary."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "Task status entries are returned for internal callers."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-status"
        effect: "reads"
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

# Browse task statuses: successful operation

## Trigger

Request the task-scope status dictionary.

## Outcome

Task status entries are returned for internal callers.
