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
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Rate cards

Financial price lists, selector lines, effective dates and target assignments.
