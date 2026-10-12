---
domain: "roles"
relations:
  - entity: "role-permission"
    verb: "contains"
    cardinality: "one-to-many"
  - entity: "user-role-assignment"
    verb: "is-assigned-through"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/RoleService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/PermissionService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/user/UserController.php"
---

# Role

Code/title, system/protected designation; related assignments and permission entries.

## Information kept

- **Code** — Runtime role code.
- **Title** — Displayed role title.
- **System** — Protected or system designation.
