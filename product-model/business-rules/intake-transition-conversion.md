---
appliesTo:
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

# Intake resolution retains its transition and conversion sequencing

Intake transitions allow Pending to Accepted/Rejected/Snoozed/Duplicate; Snoozed to Pending/Accepted/Rejected/Duplicate; Rejected and Duplicate to Pending. Accepted cannot reopen. Ordinary updates exclude status, resolution links and creator. Positive supplied revision is preliminary, not Task CAS. Acceptance creates a Task before updating the Intake item and is not atomic or established idempotency; duplicate target lookup is unscoped on its inspected path.
