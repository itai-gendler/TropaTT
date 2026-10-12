---
appliesTo:
  - type: "capability"
    id: "lock-rate-period"
  - type: "capability"
    id: "unlock-rate-period"
  - type: "capability"
    id: "browse-rate-periods"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateCardController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/RateResolutionService.php"
---

# Scoped time rows coexist with a global period registry

Period operations lock/unlock Task-scoped Worklog rows while keeping an exact-range global period/settings registry. A scoped operation with no qualifying rows can return before touching that registry. Exact-range removal differs from regenerated summary ranges; entries lacking the required scoped Task relationship are excluded on that path.
