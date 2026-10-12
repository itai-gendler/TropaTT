---
id: tropatt
summary: Self-hosted CRM and work platform for client projects, work coordination, collaboration, knowledge and recorded time.
category: work-management
tags: [crm, projects, tasks, collaboration, knowledge, time-tracking]
authors:
  - name: Anton Barinov
license: AGPL-3.0
languages: [en-GB, ru-RU, zh-CN]
references:
  - kind: doc
    role: context
    target: README.md
    title: Product identity and creator attribution
  - kind: code
    role: implementation
    target: upload/web/config/routes.php
    title: Browser work-platform subjects
  - kind: code
    role: implementation
    target: upload/api/config/routes.php
    title: Core work-platform interaction contracts
---

# TropaTT

TropaTT is a self-hosted CRM and work platform. People coordinate client projects and tasks, keep customer and contact records, collaborate in conversations and knowledge pages, organize calendar events, record time and resolve incoming work. Rate cards and recorded time support financial calculations. Browser pages, REST contracts and connected agents provide supported ways to interact with the work platform.

## Intent

Keep customer context and the work performed for it together on infrastructure operated by the people using the Product.
