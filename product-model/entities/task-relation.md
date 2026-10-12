---
domain: "tasks"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskRelationController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskRelationService.php"
---

# Task relation

Source/target/kind/note/creator/date; typed canonicalized relationship.

## Information kept

- **Source** — Source work address.
- **Target** — Target work address.
- **Kind** — Typed relation with canonical reverse or symmetric forms.
- **Note** — Optional relationship note.
- **Creator** — Creating person.
- **Created at** — Relationship creation date.
