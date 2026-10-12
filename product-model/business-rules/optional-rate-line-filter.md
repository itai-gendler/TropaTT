---
appliesTo:
  - type: "capability"
    id: "browse-rate-cards"
    contexts:
      - place: "web::work"
      - place: "rest::work"
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

# Optional rate-line filtering retains its registration and envelope behavior

The core container does not provide the optional rate-line FinancialFieldPolicy entry. If supplied, listLines passes its authentication envelope rather than the contained person to that policy, so financial fields can be stripped even for Root. The normal core list preserves line rates under its price-list route gate; policy documentation alone does not prove universal filtering.
