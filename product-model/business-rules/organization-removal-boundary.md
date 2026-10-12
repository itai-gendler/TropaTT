---
appliesTo:
  - type: "capability"
    id: "delete-organization"
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

# Organization removal does not purge all business records

Organization removal cleans its membership rows through the inspected service. It does not establish a purge of all projects, tasks, CRM records or other business data that previously referenced the organization.
