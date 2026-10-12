---
appliesTo:
  - type: "capability"
    id: "archive-chat"
  - type: "capability"
    id: "restore-chat"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Conversation restoration retains its actual participant facts

Conversation archival/restoration retains the actual participant/creator and archived-by facts and restores the implemented participant set. AI chats do not acquire the ordinary archive behavior.
