---
appliesTo:
  - type: "entity"
    id: "worklog"
    effect: "changes"
permits:
  - configuredBy: "work-settings"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
---

# Recorded-time editing retains configured work-policy guards

Configured work-policy evaluation is conjunctive with the operation's Role-code, person, work and workspace guards. The actual tasks.worklog_policy setting chooses assignee_only or all_project_members for ordinary Log time and Edit worklog. Apply its implemented target-person/Task eligibility branch, including effective Root and applicable management bypasses; default missing/invalid configuration is all_project_members. Date, duration, daily limits and interval checks remain fixed independent constraints, not customer-configured thresholds. Rate-snapshot recalculation and period locking use their own dispatched finance operation rather than pretending to be ordinary time editing. The configuration grant delegates that actual operation decision; it does not relax fixed input validation or the deletion-path lock exception.
