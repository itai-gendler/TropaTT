---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Select a person and a runtime record to assign."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
  - text: "The User role assignment is kept for the selected person."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "user-role-assignment"
        effect: "creates"
        facts:
          - "Account"
          - "Role"
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
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

# Assign user role: successful operation

## Trigger

Select a person and a runtime role to assign.

## Outcome

The User role assignment is kept for the selected person.
