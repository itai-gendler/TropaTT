---
appliesTo:
- type: capability
  id: reset-password
  contexts:
  - place: web::public
  - place: rest::public
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/PasswordResetService.php
- kind: code
  role: implementation
  target: upload/api/system/library/security/PasswordPolicy.php
---

# Password recovery consumes a valid unexpired token

Recovery confirmation requires a valid, unconsumed token within its two-hour lifetime and a replacement password satisfying PasswordPolicy. Successful confirmation consumes the token, changes the password and revokes sessions. Requesting recovery returns its generic response without the inspected implementation delivering the token; request success is not evidence that the person received a usable link.
