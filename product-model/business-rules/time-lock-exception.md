---
appliesTo:
  - type: "capability"
    id: "log-time"
  - type: "capability"
    id: "edit-worklog"
  - type: "capability"
    id: "delete-worklog"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/security/FinancialFieldPolicy.php"
---

# Time locks guard creation and editing with the deletion exception

Locked dates refuse ordinary time creation and a locked existing entry refuses ordinary editing. The inspected deletion path has no equivalent lock check and can remove a locked entry. Period registration is a separate global-registry operation.
