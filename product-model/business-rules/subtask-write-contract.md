---
appliesTo:
  - type: "capability"
    id: "create-subtask"
  - type: "capability"
    id: "edit-subtask"
  - type: "capability"
    id: "change-subtask-status"
  - type: "capability"
    id: "assign-subtask"
  - type: "capability"
    id: "unassign-subtask"
  - type: "capability"
    id: "delete-subtask"
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

# Subtask writes retain their separate contract

Subtask writes enforce their canonical statuses and description bound of 8,000 characters, inherit the applicable parent/project/key context and check explicitly supplied accessible projects. An unresolved assignee can normalize to null. Their repository writes do not inherit the ordinary Task lease/revision fence merely because the user-facing records are related.
