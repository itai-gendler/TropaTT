---
domain: "knowledge"
relations:
  - entity: "knowledge-page"
    verb: "contains-pages"
    cardinality: "one-to-many"
  - entity: "knowledge-version"
    verb: "has-versions"
    cardinality: "one-to-many"
  - entity: "page-permission"
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

# Knowledge page

Title/content/type/hierarchy/owner/client visibility/revision/review/publication; Draft/Review/Published/Archived/Needs update.

## Information kept

- **Title** — Page title.
- **Content** — Saved page content and text.
- **Type** — Page classification.
- **Parent** — Hierarchy placement.
- **Owner** — Owning person.
- **Client visible** — Customer-visibility designation.
- **Revision** — Preliminary revision.
- **Review** — Review designation and dates.
- **Publication** — Publishing person and time.
- **Deleted at** — Logical removal time.

## States

### Draft

The page is kept as a draft.

### Review

The page awaits a review decision.

### Published

The page is published within authenticated knowledge access.

### Archived

The page carries the Archived status; this is distinct from logical deletion and space trash.

### Needs update

The page carries the needs-update status.
