---
entities:
  - entity: "account"
    collects:
      - "Email"
      - "Password"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Password reset

Recovery request and conditional token confirmation. A reset request does not deliver or return the plaintext token in the inspected core path.
