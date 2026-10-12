---
domain: "contacts"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ClientService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CompanyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CounterpartyService.php"
---

# Contact

Name/email/phone/role/primary designation; owning customer and linked external Account.

## Information kept

- **Name** — Contact person name.
- **Email** — Contact email.
- **Phone** — Contact telephone.
- **Role** — Contact's business responsibility.
- **Primary** — Primary-contact designation.
- **Counterparty** — Owning customer or business.
- **External account** — Linked external person whose access may be revoked.
