---
domain: "users"
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

# User role assignment

Account–Role entry, separately assigned/removed.

## Information kept

- **Account** — Person holding the assignment.
- **Role** — Assigned runtime role.
