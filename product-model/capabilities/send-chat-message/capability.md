---
availability:
  - place: "web::work"
  - place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
domain: "chat"
---

# Send chat message

A Chat message is saved and returned; a requested outbound assistant continuation is separate from persistence.
