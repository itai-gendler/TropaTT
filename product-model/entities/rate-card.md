---
domain: "rate-cards"
relations:
  - entity: "rate-card-line"
    verb: "has-lines"
    cardinality: "one-to-many"
  - entity: "rate-card-assignment"
    verb: "has-assignments"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateCardController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/RateResolutionService.php"
---

# Rate card

Title/description/currency/default/archive/creation facts; Active/Archived.

## Information kept

- **Title** — Card name.
- **Description** — Card description.
- **Currency** — Card currency.
- **Default** — Scoped default designation.
- **Archived at** — Archival time.
- **Created at** — Creation time.

## States

### Active

The card has no archival time and remains available under its workspace scope.

### Archived

The card carries its archival time; archival detaches assignments and clears its applicable default designation.
