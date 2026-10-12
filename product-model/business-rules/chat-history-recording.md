---
appliesTo:
  - type: "entity"
    id: "chat-history"
  - type: "capability"
    id: "edit-chat-message"
  - type: "capability"
    id: "delete-chat-message"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Chat history records message changes and removals

The actual edit/removal paths record the original and changed/deleted message information presented in conversation history. This recording is a source-operation consequence, not an independently invocable history-creation ability or an audit guarantee for every chat path.
