---
appliesTo:
  - type: "capability"
    id: "log-time"
  - type: "capability"
    id: "edit-worklog"
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

# Recorded time must satisfy its implemented eligibility checks

REST time creation/editing requires its addressed Task, minutes and activity inputs. Single entry and daily totals use the implemented 1–1,440-minute and 1,440-minute bounds, future dates and invalid intervals are rejected, and deleted/terminal work fails eligibility. Archived-at is not a universal additional prohibition. Person/date policy remains independently configured.
