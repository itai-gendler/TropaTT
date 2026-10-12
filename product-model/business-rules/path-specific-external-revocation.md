---
appliesTo:
  - type: "capability"
    id: "delete-counterparty"
  - type: "capability"
    id: "edit-contact"
  - type: "capability"
    id: "delete-contact"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ClientService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CompanyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CounterpartyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ContactService.php"
---

# External revocation follows the actual CRM path

Contact reparenting/deletion and direct CounterpartyService deletion revoke or deactivate the actually linked external access through their inspected path. Client/Company proxy deletions do not inherit that guarantee merely because they address a related CRM subject.
