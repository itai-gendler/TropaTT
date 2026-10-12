---
domain: "notifications"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/NotificationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/notification/NotificationController.php"
---

# Notification

Recipient/event/title/body/link/date/read status; Unread/Read.

## Information kept

- **Recipient** — Receiving person.
- **Event** — Event kind.
- **Title** — Notification title.
- **Body** — Notification content.
- **Link** — Destination supplied by the producing path.
- **Created at** — Production time.
- **Read** — Read designation.

## States

### Unread

The recipient has not marked this notification read.

### Read

The recipient has marked this notification read.
