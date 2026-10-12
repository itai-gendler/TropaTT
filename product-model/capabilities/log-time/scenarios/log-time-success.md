---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply existing open work, positive minutes, activity and a valid logging date."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "An unlocked Worklog is saved; best-effort financial snapshots are distinguished from the saved time."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "creates"
        facts:
          - "Owner"
          - "Task"
          - "Project"
          - "Date"
          - "Minutes"
          - "Started at"
          - "Ended at"
          - "Note"
          - "Activity"
          - "Currency"
          - "Locked"
        to: "Unlocked"
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "Successful rate resolution changes the Worklog snapshots and their provenance after core persistence."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "changes"
        facts:
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
          - "Provenance"
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-collection"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/security/FinancialFieldPolicy.php"
---

# Log time: successful operation

## Trigger

Supply existing open work, positive minutes, activity and a valid logging date, with a successfully resolvable rate configuration.

## Outcome

An unlocked Worklog is saved first; successful resolution then stores independent financial snapshots and their provenance.
