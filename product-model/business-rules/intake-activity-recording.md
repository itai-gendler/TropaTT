---
appliesTo:
  - type: "entity"
    id: "intake-activity"
  - type: "capability"
    id: "create-intake-item"
  - type: "capability"
    id: "edit-intake-item"
  - type: "capability"
    id: "assign-intake-item"
  - type: "capability"
    id: "unassign-intake-item"
  - type: "capability"
    id: "delete-intake-item"
  - type: "capability"
    id: "accept-intake-item"
  - type: "capability"
    id: "reject-intake-item"
  - type: "capability"
    id: "snooze-intake-item"
  - type: "capability"
    id: "mark-intake-duplicate"
  - type: "capability"
    id: "reopen-intake-item"
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

# Intake activity records its implemented request and resolution events

The traced creation/edit/resolution/snooze/reopen paths record their implemented activity events for the Intake item. Acceptance's Task-first sequencing and partially failing source operations retain their actual boundaries; recording does not make conversion atomic or idempotent.
