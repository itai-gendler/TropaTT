---
entities:
  - entity: "counterparty"
    shows:
      - "Kind"
      - "Title"
      - "Person details"
      - "Legal details"
      - "Tax number"
      - "Bank details"
      - "Email"
      - "Phone"
      - "Address"
      - "Status"
      - "Additional information"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Counterparties

Addressed counterparties facts and inspected record input, with contract-specific validation.
