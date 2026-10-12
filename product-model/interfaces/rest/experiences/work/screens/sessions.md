---
entities:
  - entity: "session"
    shows:
      - "Device"
      - "Created at"
      - "Expires at"
      - "Revoked at"
      - "Account"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Sessions

Own session records and individual or other-session revocation outcomes.
