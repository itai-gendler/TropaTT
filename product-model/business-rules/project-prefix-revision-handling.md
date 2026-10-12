---
appliesTo:
  - type: "capability"
    id: "create-project"
  - type: "capability"
    id: "edit-project"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/project/ProjectController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ProjectService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/project/ProjectRepository.php"
---

# Project prefixes and revisions retain their implemented checks

Project creation/editing validates the applicable prefix uniqueness. A positive supplied revision can reject a stale edit; omitted/nonpositive revision differs, and the Project preliminary check is not Task-style transactional compare-and-swap.
