---
domain: "intake"
relations:
  - entity: "intake-activity"
    verb: "has-activity"
    cardinality: "one-to-many"
  - entity: "task"
    verb: "converts-to"
    cardinality: "one-to-one"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/IntakeItemService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/intake/IntakeItemController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/intake/IntakeItemRepository.php"
---

# Intake item

Title/description/source/context/priority/dates/assignee/revision/resolution/Task/duplicate links; Pending/Snoozed/Accepted/Rejected/Duplicate.

## Information kept

- **Title** — Incoming request title.
- **Description** — Request description.
- **Source** — Origin classification.
- **Context** — Project, customer and contact references.
- **Priority** — Request priority.
- **Start date** — Planned start.
- **Due date** — Planned due date.
- **Assignee** — Assigned person or empty assignment.
- **Revision** — Preliminary revision.
- **Resolution** — Resolution reason, resolving person and date.
- **Snoozed until** — Stored deferral date supplied by the snooze operation and cleared on reopening.
- **Task** — Converted work link.
- **Duplicate** — Duplicate work or intake link.
- **Creator** — Submitting person.

## States

### Pending

The incoming request awaits acceptance, rejection, deferral or duplicate resolution.

### Snoozed

Resolution is deferred until the stored date.

### Accepted

A created Task has been linked and the incoming request marked accepted.

### Rejected

The request has been rejected with a reason.

### Duplicate

The request points to duplicate work or another request.
