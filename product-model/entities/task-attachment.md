---
domain: "tasks"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/file/FileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/FileService.php"
---

# Task attachment

Task/uploader/name/type/size/visibility/quarantine/deletion facts.

## Information kept

- **Name** — Original file name.
- **Type** — File media type.
- **Size** — Stored byte size.
- **Visibility** — Internal or client-visible designation.
- **Uploader** — Uploading person.
- **Quarantined** — Configured safe-treatment designation.
- **Deleted at** — Logical removal date.
