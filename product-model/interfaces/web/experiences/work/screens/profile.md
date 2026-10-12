---
entities:
  - entity: "account"
    shows:
      - "Login"
      - "Email"
      - "Name"
      - "Language"
      - "Time zone"
      - "Active"
    collects:
      - "Name"
      - "Email"
      - "Language"
      - "Time zone"
      - "Password"
  - entity: "session"
    shows:
      - "Account"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Profile

Own personal profile, password replacement and the current session summary; the inspected control revokes other sessions.
