---
domain: "tasks"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/subtask/SubtaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SubtaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/subtask/SubtaskRepository.php"
---

# Subtask

Addressed child-work facts, parent and order; shares underlying Task identity where implemented.

## Information kept

- **Title** — Addressed child-work title.
- **Description** — Child-work description.
- **Status** — Child-work status code.
- **Priority** — Child-work priority.
- **Due date** — Child-work due date.
- **Order** — Position under its parent.
- **Parent** — Parent work address.
- **Project** — Inherited or explicitly selected project.
- **Assignee** — Assigned person or empty assignment.
- **Deleted at** — Underlying child-work soft-deletion date.
