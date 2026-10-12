---
appliesTo:
  - type: "capability"
    id: "recalculate-worklog-rates"
    contexts:
      - place: "rest::work"
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

# Recalculation retains dry-run and partial outcomes

Snapshot recalculation processes unlocked entries in bounded batches and reports processed, changed and failure outcomes. Dry-run does not persist changes; a partially failed batch is not an atomic rollback of earlier successful snapshots.
