---
appliesTo:
  - type: "entity"
    id: "worklog"
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
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
---

# Only people authorized for the requested operation read worklog records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Browse worklogs: task.manage OR worklog.view, visible-person scope.
- Browse worklogs, Browse time analytics: task.manage, actual person/Task guards.
- Browse own earnings: own Account and applicable internal payout/cost or executor payout grant; narrower Web gate retained.

List uses task.manage OR worklog.view and visible-person hierarchy/team/organization selection. Addressed record and report paths use task.manage and their actual owner/person/Task guards. Own earnings is always the current Account/date range, not an Organization-specific payment: REST requires task.manage plus effective Root, wildcard, finance.rate.view_own_payout or finance.rate.view_cost; the Web gate is narrower. External executor time is scoped to visible own/granted work and only its permitted own payout output; observers do not gain recorded-time access. Financial field policy is an independent output restriction.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

