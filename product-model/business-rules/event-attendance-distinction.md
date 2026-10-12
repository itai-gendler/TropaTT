---
appliesTo:
  - type: "capability"
    id: "browse-calendar"
  - type: "capability"
    id: "create-calendar-event"
  - type: "capability"
    id: "edit-calendar-event"
  - type: "capability"
    id: "delete-calendar-event"
  - type: "capability"
    id: "add-event-attendee"
  - type: "capability"
    id: "remove-event-attendee"
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

# Event attendance changes differ from owner-only detail changes

Calendar values normalize to UTC and readable events retain actual source/privacy scope. Base event detail mutation/removal is owner/Root restricted, while attendee synchronization is reachable through readable-event update. A readable nonowner can change attendance even when the base owner-only update changes no row; synchronization does not depend on that SQL boolean succeeding.
