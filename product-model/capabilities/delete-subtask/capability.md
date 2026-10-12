---
availability:
  - place: "web::work"
  - place: "rest::work"
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
domain: "tasks"
---

# Delete subtask

The Subtask is soft-deleted and its parent-link entry removed.
