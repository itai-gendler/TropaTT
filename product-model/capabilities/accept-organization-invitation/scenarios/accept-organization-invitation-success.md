---
kind: "primary"
routes:
  rest-public: "Rest Public"
steps:
  - text: "Submit a valid record token and registration information."
    kind: "actor"
    actor: "visitor"
    entities: []
    contexts:
      rest-public:
        place: "rest::public"
  - text: "The Organization invitation becomes accepted; an account is created and membership insertion is attempted."
    kind: "product"
    actor: "visitor"
    entities:
      - entity: "account"
        effect: "creates"
        facts:
          - "Login"
          - "Email"
          - "Name"
          - "Language"
          - "Time zone"
          - "Active"
          - "Password"
          - "Second factor"
          - "Default cost rate"
          - "Default bill rate"
          - "Default payout rate"
          - "Currency"
      - entity: "organization-invitation"
        effect: "changes"
        facts:
          - "Accepted at"
        from: "Pending"
        to: "Accepted"
      - entity: "organization-membership"
        effect: "creates"
        facts:
          - "Role"
          - "Joined at"
          - "Account"
        with: "account"
      - entity: "user-role-assignment"
        effect: "creates"
        facts:
          - "Account"
          - "Role"
        with: "account"
    contexts:
      rest-public:
        place: "rest::public"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationContextService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/InvitationService.php"
---

# Accept organization invitation: successful operation

## Trigger

Submit a valid organization invitation token and registration information, with the default user Role present and successful membership insertion.

## Outcome

The Organization invitation becomes accepted; an account is created and membership is inserted on this successful path.

## Edge cases

- Acceptance does not inspect the membership-insertion result; an insertion failure can leave an accepted invitation and created Account without that membership.
- Assignment to the default user Role occurs only when that Role exists.
