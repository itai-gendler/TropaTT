---
appliesTo:
  - type: "capability"
    id: "assign-user-role"
  - type: "capability"
    id: "remove-user-role"
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
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/UserService.php"
---

# Nonroot role and Root-flag input is discarded

Nonroot user-update role input and direct Root-flag input are discarded by the inspected update path. The Root-only role-assignment path retains its actual target hierarchy/workspace checks; discarded input does not become a kept assignment.
