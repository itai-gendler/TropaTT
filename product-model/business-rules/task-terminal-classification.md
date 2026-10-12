---
appliesTo:
- type: entity
  id: task
- type: entity
  id: task-status
references:
- kind: code
  role: implementation
  target: upload/api/system/library/support/TaskStatusSemantics.php#isTerminal
- kind: code
  role: implementation
  target: upload/api/system/library/support/TaskStatusSemantics.php#map
---

# Terminal status uses dictionary flags before fallback

Terminal classification uses a found dictionary row's is_closed value. Where no relevant row is found it falls back to done, completed, closed, canceled, cancelled and archived. The queries are unscoped, and duplicate dictionary codes have no established organization precedence.
