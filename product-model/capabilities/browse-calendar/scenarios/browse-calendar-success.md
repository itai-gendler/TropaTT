---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request readable events in a valid date interval."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "Calendar event and attendee facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "calendar-event"
        effect: "reads"
        facts:
          - "Title"
          - "Description"
          - "Owner"
          - "Starts at"
          - "Ends at"
          - "Work"
          - "Source"
          - "Privacy"
      - entity: "event-attendance"
        effect: "reads"
        facts:
          - "Account"
          - "Designation"
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

# Browse calendar: successful operation

## Trigger

Request readable events in a valid date interval.

## Outcome

Calendar event and attendee facts are returned.
