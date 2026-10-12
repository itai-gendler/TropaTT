---
appliesTo:
  - type: "capability"
    id: "change-project-status"
    contexts:
      - place: "web::work"
      - place: "rest::work"
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

# Project completion checks current open work

Project completion checks for open work at the time of the requested change, excluding deleted/archived Tasks as implemented. Refusal offers resolution through closing or moving work. Passing that check is not a perpetual invariant against later open work.
