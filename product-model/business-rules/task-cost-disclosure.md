---
appliesTo:
  - type: "entity"
    id: "task"
    effect: "reads"
    facts:
      - "Cost rate"
    contexts:
      - place: "web::work"
      - place: "rest::work"
permits:
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/security/FinancialFieldPolicy.php#allowedFamilies"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateController.php#preview"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateCardController.php#listLines"
---

# Only people admitted by the cost policy receive Task cost values

Internal effective Root may disclose. Otherwise an internal person's own row requires finance.rate.view_own_cost OR finance.rate.view_cost; another row requires finance.rate.view_cost. External people never receive cost.

Ordinary Task list/detail/update and archive responses use this family policy. Raw Task creation and dedicated movement responses do not establish the same filtering guarantee: those dispatched responses follow their route/object authorization without the field strip. Rate preview may internally read overrides after its task.manage plus any-financial-code gate; the internal basis read is not disclosure and its actual output still receives this family filter.

Own means a nonempty response row user_public_id equal to the authenticated person's public_id; Task assignment or a selected preview person does not substitute for it. External classification is checked before Root. Rate, amount and provenance in a family are removed together. Filtering follows row visibility and cannot authorize a previously inaccessible record. Account-derived and line-derived preview outputs contain no matching own-row identity, so own-only codes do not disclose those values. Candidate configuration identifiers additionally require finance.ratecard.manage or internal effective Root.

## Rationale

The decision depends on the dispatched response and its authenticated person. Internal calculation reads do not by themselves disclose financial fields.
