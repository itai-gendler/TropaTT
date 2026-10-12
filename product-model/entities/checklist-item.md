---
domain: "tasks"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/checklist/ChecklistController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChecklistService.php"
---

# Checklist item

Checklist, text/order/completion; Open/Complete.

## Information kept

- **Text** — Item text.
- **Order** — Item position.
- **Completed** — Completion designation.

## States

### Open

The checklist entry is incomplete.

### Complete

The checklist entry is complete.
