---
appliesTo:
  - type: "entity"
    id: "worklog"
    effect: "reads"
    facts:
      - "Bill rate"
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

# Only people admitted by the bill policy receive Worklog bill values

Internal effective Root or finance.rate.view_bill may disclose. External people never receive bill, margin or their amount/rate equivalents.

Worklog list/detail, reports, earnings and the inspected mutation response paths apply this family policy. Calculation may internally read snapshot values under the source operation's gate without disclosing them; projected output is independently filtered.

Own means a nonempty response row user_public_id equal to the authenticated person's public_id; Task assignment or a selected preview person does not substitute for it. External classification is checked before Root. Rate, amount and provenance in a family are removed together. Filtering follows row visibility and cannot authorize a previously inaccessible record. Account-derived and line-derived preview outputs contain no matching own-row identity, so own-only codes do not disclose those values. Candidate configuration identifiers additionally require finance.ratecard.manage or internal effective Root.

## Rationale

The decision depends on the dispatched response and its authenticated person. Internal calculation reads do not by themselves disclose financial fields.
