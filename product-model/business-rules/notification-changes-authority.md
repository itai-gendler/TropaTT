---
appliesTo:
  - type: "entity"
    id: "notification"
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
    target: "upload/api/system/library/service/NotificationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/notification/NotificationController.php"
---

# Only people authorized for the requested operation change notification records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Browse notifications, Create notification, Mark notification read, Mark notification unread: canonical task.manage gate AND recipient selection; manual target override Root-only; explicit external read-state writes.

Read-state mutation requires task.manage and recipient ownership. Mark-all-read is own-recipient scoped. Observer REST read-state writes are explicitly whitelisted and do not inherit the general observer write prohibition.

Canonical Browse notifications and Mark notification read/unread require task.manage and the current recipient; external read/read-state writes use the route's actual external whitelist. Canonical Create notification requires task.manage, while the inspected legacy /notification/create self-service alias has authentication but no required_permissions code. Both retain actual recipient selection: only effective Root may override the target person. Automatic creation inherits its authorized source operation and actual recipient calculation, rather than requiring a separate manual task.manage grant. Organization input retains the actual service qualification and does not establish universal tenant isolation.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

