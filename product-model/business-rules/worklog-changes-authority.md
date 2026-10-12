---
appliesTo:
  - type: "entity"
    id: "worklog"
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
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
---

# Only people authorized for the requested operation change worklog records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Log time's post-save snapshots inherit its authorized creation: task.manage OR worklog.manage with the actual target-person/work eligibility checks. Edit worklog's conditional re-resolution inherits the authorized ordinary edit. Neither requires the separate finance.rate.manage recalculation code.

- Edit worklog, Delete worklog: task.manage AND (owner OR unscoped effective Root OR same-organization task.manage OR worklog.manage_all).
- Recalculate worklog rates, Lock rate period, Unlock rate period: finance.rate.manage, actual Task-derived organization scope.

Ordinary editing uses task.manage AND (owner OR unscoped effective Root OR same-organization task.manage OR worklog.manage_all). It refuses locked entries and applies work-policy validation. Recalculate snapshots and lock/unlock instead require finance.rate.manage and Task-derived organization row scope. Recalculation affects unlocked rows; period operations combine scoped row updates with the global registry. These dispatched permissions are alternatives by operation, not codes required together.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

