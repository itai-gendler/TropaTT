---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "A readable event's nonowner submits ordinary detail changes."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The owner-filtered event update changes no ordinary details; no success of the requested detail mutation is asserted."
    kind: "condition"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/calendar/CalendarController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CalendarService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/calendar/CalendarEventRepository.php"
---

# Readable nonowner event

## Trigger

A readable event's nonowner submits ordinary detail changes.

## Outcome

The owner-filtered event update changes no ordinary details; no success of the requested detail mutation is asserted.
