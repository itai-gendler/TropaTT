---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable event is absent from the response or returns CALENDAR_EVENT_NOT_FOUND."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "An unavailable event is absent from the response or returns CALENDAR_EVENT_NOT_FOUND."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
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

# Browse calendar: refused or unavailable operation

## Trigger

An unavailable event is absent from the response or returns CALENDAR_EVENT_NOT_FOUND.

## Outcome

An unavailable event is absent from the response or returns CALENDAR_EVENT_NOT_FOUND.
