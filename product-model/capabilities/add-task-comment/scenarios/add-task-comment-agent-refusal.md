---
kind: "validation"
routes:
  agent: "Agent"
steps:
  - text: "Submit a tool request with invalid advertised input, an unavailable object or a credential whose scope intersection is empty."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The tool returns its validation, not-found or registry-gate error and performs no successful mutation."
    kind: "condition"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CommentService.php"
---

# Add task comment agent request is rejected

## Trigger

Submit a tool request with invalid advertised input, an unavailable object or a credential whose scope intersection is empty.

## Outcome

The tool returns its validation, not-found or registry-gate error and performs no successful mutation.
