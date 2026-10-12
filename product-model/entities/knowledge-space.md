---
domain: "knowledge"
relations:
  - entity: "knowledge-space"
    verb: "contains-spaces"
    cardinality: "one-to-many"
  - entity: "knowledge-page"
    verb: "contains-pages"
    cardinality: "one-to-many"
  - entity: "space-permission"
    verb: "has-permissions"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgeController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/KnowledgePageVersionService.php"
---

# Knowledge space

Title/description/hierarchy/owner/visibility/default access/revision/archive/trash.

## Information kept

- **Title** — Space title.
- **Description** — Space description.
- **Parent** — Hierarchy placement.
- **Owner** — Owning person.
- **Visibility** — Authenticated visibility designation.
- **Default access** — Default ranked access.
- **Revision** — Preliminary revision.
- **Archived at** — Archival time.
- **Deleted at** — Trash time.
- **System** — Protected system-space designation.
