---
appliesTo:
  - type: "entity"
    id: "organization"
  - type: "entity"
    id: "organization-membership"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthzService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationContextService.php"
---

# Workspace resolution retains its operation-specific boundaries

Workspace resolution distinguishes an explicit inaccessible organization, an implicit single available organization, a required selection and supported legacy/unscoped operation paths. Explicit forbidden selection is rejected before scoped processing. An absent selection is not evidence of universal access or of universal refusal: Root and legacy/global paths retain their implemented dispatch.
