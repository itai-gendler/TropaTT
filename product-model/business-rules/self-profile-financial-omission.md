---
appliesTo:
  - type: "entity"
    id: "account"
    effect: "reads"
    facts:
      - "Default cost rate"
      - "Default bill rate"
      - "Default payout rate"
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

# Nobody receives default rates in their sanitized profile

Read own profile always strips default-rate fields for every person, including effective Root. This configured dispatch decision returns denial for that self-profile output. Preview rates may instead read Account defaults internally under task.manage plus any financial-view code, and its derived response follows the independent preview family Rules. A preview within REST Work must not inherit the self-profile output prohibition.

Own means a nonempty response row user_public_id equal to the authenticated person's public_id; Task assignment or a selected preview person does not substitute for it. External classification is checked before Root. Rate, amount and provenance in a family are removed together. Filtering follows row visibility and cannot authorize a previously inaccessible record. Account-derived and line-derived preview outputs contain no matching own-row identity, so own-only codes do not disclose those values. Candidate configuration identifiers additionally require finance.ratecard.manage or internal effective Root.

## Rationale

The decision depends on the dispatched response and its authenticated person. Internal calculation reads do not by themselves disclose financial fields.
