---
appliesTo:
  - type: "entity"
    id: "task"
    effect: "changes"
permits:
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthzService.php#permissionsForUser"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/task/TaskRepository.php"
---

# Only people authorized for the requested operation change task records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Edit task, Change task status, Assign task, Unassign task, Set task parent, Remove task parent, Archive task, Restore task, Delete task, Move task: internal task.manage and actual object access; inspected agent counterparts.
- Edit task rates: internal task.manage AND (effective Root OR finance.rate.manage).

Ordinary Edit task, Change task status, Assign/Unassign, parenting and archive/restoration require internal task.manage and existing-object access. Ordinary positive-version writes retain the MySQL revision/lease/graph fence and independent active-lease checks; effective Root does not bypass those fences. Dedicated Move task has task.manage and destination access but only its preliminary revision/WIP checks; it does not forward supplied fence context. Edit task rates additionally requires effective Root OR finance.rate.manage; failed field authority strips overrides rather than rejecting the whole ordinary update. Dictionary deletion's raw status replacement runs under task.manage and dictionary scope without the normal revision/lease/history path. Agent ordinary edit/status/assignment/movement inherits connected-person checks and registry/credential bounds; unadvertised parent/archive/rate input is not supported.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

