---
entities:
  - entity: "company"
    shows:
      - "Title"
      - "Status"
      - "Email"
      - "Tax number"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Companies

Addressed companies facts and inspected record input, with contract-specific validation.
