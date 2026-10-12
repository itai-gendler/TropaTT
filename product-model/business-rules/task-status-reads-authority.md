---
appliesTo:
  - type: "entity"
    id: "task-status"
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
    target: "upload/api/controller/status/StatusController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/StatusService.php"
---

# Only people authorized for the requested operation read task status records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Browse task statuses: internal Task-scope listing requires task.manage; the external executor branch is forced to worklog_activity and does not disclose Task status records.

Internal task-scope listing requires task.manage and actual dictionary organization handling. External executor list requests are forced to worklog_activity; no Task status dictionary disclosure is granted by that branch. External observers cannot use that list path.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

