---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing title or invalid time interval is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "Missing title or invalid time interval is rejected."
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

# Create calendar event: refused or unavailable operation

## Trigger

Missing title or invalid time interval is rejected.

## Outcome

Missing title or invalid time interval is rejected.
