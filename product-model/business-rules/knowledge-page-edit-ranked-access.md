---
appliesTo:
  - type: "entity"
    id: "knowledge-page"
    effect: "changes"
permits:
  - configuredBy: "page-permission"
  - configuredBy: "space-permission"
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php#pageAccessSql"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php#actorBypassesKnowledgeAcl"
---

# Only people with edit-ranked access change page content and status

The current authenticated person must have edit-ranked page access, independently ANDed with the dispatched operation's exact route permission and credential restrictions. Within the Page configuration alternative, the person owns the page or matches a Page permission entry at edit rank or higher. Within the Space configuration alternative, the person owns its space, matches a Space permission entry at edit rank or higher, or a public space's default access reaches edit rank. Subjects match the actual Account or its Role, Team or Department memberships. Within the administrative alternative, effective Root or raw actor permission codes containing '*' or knowledge.admin bypass this ACL; an Account Root flag alone does not restore effective Root lost to scoped credentials.

These three configuration alternatives are OR. Active-workspace boundaries, page deletion and containing-space trash filters remain AND conditions even for administrative bypasses. Ordinary editing/restoration/review requests and explicit publication/review decisions/version restoration retain their different route permission requirements. Page removal separately requires manage rank. Page content and status changes use this edit-ranked object check. Page removal retains its separate manage-ranked Rule. Trashing/restoring a containing space changes space records and its visibility filter; it does not rewrite descendant pages' Deleted at facts.

