---
appliesTo:
  - type: "capability"
    id: "create-rate-card"
  - type: "capability"
    id: "edit-rate-card"
  - type: "capability"
    id: "archive-rate-card"
  - type: "capability"
    id: "add-rate-card-line"
  - type: "capability"
    id: "edit-rate-card-line"
  - type: "capability"
    id: "delete-rate-card-line"
  - type: "capability"
    id: "assign-rate-card"
  - type: "capability"
    id: "unassign-rate-card"
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

# Rate-card archival detaches assignments and applicable defaults

Rate cards retain actual workspace scope, default selection, selector/date validation and assignment references. Archiving detaches assignments and clears the applicable default. Line and assignment changes do not imply financial-family disclosure elsewhere.
