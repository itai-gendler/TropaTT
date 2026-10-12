---
domain: "profile"
relations:
  - entity: "session"
    verb: "has-sessions"
    cardinality: "one-to-many"
  - entity: "user-role-assignment"
    verb: "holds"
    cardinality: "one-to-many"
  - entity: "api-key"
    verb: "binds"
    cardinality: "one-to-many"
  - entity: "organization-membership"
    verb: "holds-memberships"
    cardinality: "one-to-many"
  - entity: "task"
    verb: "creates-work"
    cardinality: "one-to-many"
  - entity: "task"
    verb: "is-assigned-work"
    cardinality: "one-to-many"
  - entity: "worklog"
    verb: "records"
    cardinality: "one-to-many"
  - entity: "chat-membership"
    verb: "participates-through"
    cardinality: "one-to-many"
  - entity: "chat-message"
    verb: "sends"
    cardinality: "one-to-many"
  - entity: "knowledge-page"
    verb: "owns-pages"
    cardinality: "one-to-many"
  - entity: "knowledge-space"
    verb: "owns-spaces"
    cardinality: "one-to-many"
  - entity: "calendar-event"
    verb: "owns-events"
    cardinality: "one-to-many"
  - entity: "event-attendance"
    verb: "attends-through"
    cardinality: "one-to-many"
  - entity: "notification"
    verb: "receives"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/auth/AuthController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/ProfileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/SessionController.php"
---

# Account

Login/email/name/language/time zone, active designation, credential/factor configuration and default financial rates.

## Information kept

- **Login** — Sign-in name.
- **Email** — Current contact email; changing a nonempty value requires verification.
- **Name** — Displayed full name.
- **Language** — Preferred shipped locale.
- **Time zone** — Personal time-zone preference.
- **Active** — Whether the person can authenticate.
- **Password** — Credential configuration; plaintext is never disclosed.
- **Second factor** — Enabled factor and recovery configuration.
- **Default cost rate** — Person-level cost fallback.
- **Default bill rate** — Person-level billing fallback.
- **Default payout rate** — Person-level payout fallback.
- **Currency** — Default financial currency.
