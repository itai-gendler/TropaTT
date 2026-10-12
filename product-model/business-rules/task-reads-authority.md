---
appliesTo:
  - type: "entity"
    id: "task"
    effect: "reads"
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

# Only people authorized for the requested operation read task records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Browse tasks Web/REST: task.view OR task.manage, actual scope and external alternatives.
- Browse task board, Browse tasks M: task.manage, applicable scope; agent through connected person.
- Create task, Move task: their route/object grants; no invented controller financial filter.

Ordinary Web/REST browse uses task.view OR task.manage with the actual Project/work visibility and organization predicates. Board listing and the named MCP task read require task.manage. Task creation and dedicated movement responses use their write route/object grants and do not invoke the ordinary financial response filter. External observer reads are limited to linked-customer work; executor reads to granted Projects. MCP registry and advertised-schema checks precede delegation; agent authority is that of its connected person. Rate preview's internal basis read follows its preview route and reference lookups, without asserting universal tenant isolation.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

