---
domain: "intake"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/IntakeItemService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/intake/IntakeItemController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/intake/IntakeItemRepository.php"
---

# Intake activity

Displayed actor/event/field/prior/new value/note/time.

## Information kept

- **Actor** — Person attributed to the event.
- **Event** — Recorded request or resolution event.
- **Field** — Changed field when present.
- **Previous value** — Recorded prior value.
- **New value** — Recorded resulting value.
- **Note** — Optional event note.
- **Created at** — Event time.
