---
appliesTo:
- type: entity
  id: role
- type: entity
  id: api-client
- type: entity
  id: api-key
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/ApiClientService.php#authenticateByKey
- kind: code
  role: implementation
  target: upload/api/system/library/service/AuthzService.php#permissionsForUser
---

# Credentials only narrow the bound Account's authority

Key authentication applies actual Client scopes then Key scopes to the bound Account's authority. Empty arrays and exactly ['*'] inherit, other arrays restrict by the implemented wildcard replacement/intersection. Restricted empty codes deny without Role fallback; any restriction removes effective Root. Mixed wildcard arrays are not the unrestricted case.
