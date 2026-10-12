---
appliesTo:
  - type: "capability"
    id: "delete-role"
    contexts:
      - place: "web::administration"
      - place: "rest::administration"
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

# Protected or assigned Roles cannot be deleted

Protected/system Roles and Roles still assigned to people cannot be deleted. Removing an assignment is a different operation from deleting the Role.
