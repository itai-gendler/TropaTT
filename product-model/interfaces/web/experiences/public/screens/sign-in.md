---
entities:
- entity: account
  collects:
  - Login
  - Password
references:
- kind: code
  role: implementation
  target: upload/web/config/routes.php
- kind: code
  role: implementation
  target: upload/web/assets/js/br1.js
---

# Sign in

Credential and factor continuation of the one sign-in process; it reports the authentication outcome without revealing credentials.
