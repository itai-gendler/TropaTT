---
appliesTo:
  - type: "entity"
    id: "task"
    effect: "reads"
    facts:
      - "Cost rate"
      - "Bill rate"
      - "Payout rate"
    contexts:
      - place: "mcp"
permits: []
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

# Nobody receives stripped Task financial fields through inspected MCP responses

The inspected MCP publicData transformation strips these Task financial fields regardless of the connected person's financial codes. Internal producer reads and raw REST creation/movement are different dispatched operations.

Own means a nonempty response row user_public_id equal to the authenticated person's public_id; Task assignment or a selected preview person does not substitute for it. External classification is checked before Root. Rate, amount and provenance in a family are removed together. Filtering follows row visibility and cannot authorize a previously inaccessible record. Account-derived and line-derived preview outputs contain no matching own-row identity, so own-only codes do not disclose those values. Candidate configuration identifiers additionally require finance.ratecard.manage or internal effective Root.

## Rationale

The decision depends on the dispatched response and its authenticated person. Internal calculation reads do not by themselves disclose financial fields.
