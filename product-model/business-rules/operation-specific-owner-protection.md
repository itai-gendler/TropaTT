---
appliesTo:
  - type: "capability"
    id: "add-member"
  - type: "capability"
    id: "change-member-role"
  - type: "capability"
    id: "remove-member"
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

# Owner protection follows the actual membership operation

Dedicated membership demotion/removal applies its last-owner and self protections. Membership upsert does not share all those checks. These operation-specific guards do not establish a concurrency-safe invariant that every organization always has an owner.
