---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable parent event cannot receive attendance."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "An unavailable parent event cannot receive attendance."
    kind: "condition"
    actor: "root-administrator"
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

# Add event attendee: refused or unavailable operation

## Trigger

An unavailable parent event cannot receive attendance.

## Outcome

An unavailable parent event cannot receive attendance.
