---
appliesTo:
  - type: "capability"
    id: "browse-organizations"
    contexts:
      - place: "web::work"
      - place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationContextService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/InvitationService.php"
---

# Root management browsing can initialize the default workspace

Root management organization browsing can initialize the default organization and owner membership. Available-organization listing does not establish that same initialization effect.
