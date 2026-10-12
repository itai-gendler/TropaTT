---
entities:
  - entity: "contact"
    shows:
      - "Name"
      - "Email"
      - "Phone"
      - "Role"
      - "Primary"
      - "Counterparty"
      - "External account"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Contacts

Addressed contacts facts and inspected record input, with contract-specific validation.
