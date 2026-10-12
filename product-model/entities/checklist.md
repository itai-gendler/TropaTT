---
domain: "tasks"
relations:
  - entity: "checklist-item"
    verb: "has-items"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/checklist/ChecklistController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChecklistService.php"
---

# Checklist

Task, title and order.

## Information kept

- **Title** — Checklist name.
- **Order** — Checklist position under work.
