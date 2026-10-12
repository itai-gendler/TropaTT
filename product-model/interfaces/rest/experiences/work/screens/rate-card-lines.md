---
entities:
  - entity: "rate-card"
    shows:
      - "Title"
      - "Description"
      - "Currency"
      - "Default"
      - "Archived at"
      - "Created at"
  - entity: "rate-card-line"
    shows:
      - "Person"
      - "Role"
      - "Activity"
      - "Cost rate"
      - "Bill rate"
      - "Payout rate"
      - "Currency"
      - "Effective from"
      - "Effective to"
      - "Note"
  - entity: "rate-card-assignment"
    shows:
      - "Target"
      - "Priority"
      - "Effective from"
      - "Effective to"
  - entity: "account"
    shows:
      - "Default cost rate"
      - "Default bill rate"
      - "Default payout rate"
      - "Currency"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Rate-card lines

Price-list selectors, effective dates, assignments and derived preview outcomes. Core line responses retain financial fields inside the price-list gate.
