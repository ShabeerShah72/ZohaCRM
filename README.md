# Zoho CRM Deal Stage Workflow Automation

An enterprise-grade automation framework for Zoho CRM that streamlines deal stage management, automates follow-ups, handles escalations, and ensures accountability with centralized audit logging.

---
  
##✨ Features

-📌 Automated Stage Workflows – Follow-up tasks created when deals reach milestones
-⚡ Escalation Management – Detects stalled deals and escalates to managers
-⏳ Stalled Deal Detection – Flags inactive deals with scoring logic
-🗂️ Centralized Audit Logging – Custom Deal_Audit module for all automation events
-📢 Notifications & Integrations – Alerts via Email, Slack, Teams, or secure webhooks
-⚙️ Configurable Settings – All thresholds, templates, and endpoints managed in config

---

##🖥️ Demo

- Workflow: Fully automated deal stage lifecycle with zero manual intervention
- Integrations: Slack/Teams/Email + secure API webhooks
- Audit Trail: Transparent event logging in Zoho CRM custom module
- What you can manage:
- Deal Stages & Follow-Ups
- Escalations for Stalled Deals
- Scoring & Prioritization
- Notifications & Alerts
- Historical Logs

---

##🚀 Quick Start
Prerequisites

- Zoho CRM Developer Edition
- Access to Deluge Scripting
- Slack/Teams webhook (optional)
- Zoho Vault for secret storage
- Installation
  
#  Create custom fields in Deals:
- Next_Followup_Date
- Deal_Score
- Stalled
- Escalation_Level
- Create custom module Deal_Audit.
- Upload Deluge functions to Zoho CRM Functions.
- Configure workflow rules for deal stage changes.
- Set up scheduled jobs for reconciliation.
- Import notification templates.
- Add Slack/Teams webhooks in config.

---

##🏗️ Project Structure
Zoho-Deal-Automation/
├── src/
│   ├── components/
│   │   └── ui/
│   ├── hooks/
│   │   ├── use-mobile.tsx
│   │   └── use-toast.tsx
│   ├── lib/
│   └── pages/
├── components.json
├── eslint.config.js
├── index.html
├── package-lock.json
├── postcss.config.ts
├── tailwind.config.ts
├── tsconfig.json
├── tsconfig.app.json
├── tsconfig.node.json
├── vite.config.ts
└── README.md

---

##🔧 Configuration

Deal Thresholds & Escalations → Defined in config object

Webhook Endpoints → Secure URLs with HMAC-SHA256 signing

Notification Templates → Stored in Zoho CRM / Vault

Modify via config:

Follow-up intervals

Escalation levels

Notification channels

---

##🌐 API / Workflow Events
Stage Change → Follow-up

Trigger: Deal moves to Sales Qualified

Action: Follow-up task created + notification

Escalation Workflow

Trigger: Deal stuck at Proposal Sent beyond threshold

Action: Escalation task + manager notified

Stalled Deal Detection

Trigger: Inactive deal for N days

Action: Deal flagged + score updated

Manual Re-Evaluation

Trigger: Admin request

Action: Automation re-runs, logged in Deal_Audit

---

##📊 Workflow Diagram
flowchart TD
    A[Deal Stage Change] --> B{Stage = Sales Qualified?}
    B -- Yes --> C[Create Follow-up Task]
    B -- No --> D[Check if Stalled/Proposal Sent]
    D -- Stalled --> E[Flag Deal & Update Score]
    D -- Proposal Sent & Expired --> F[Escalate to Manager + Notify]
    C --> G[Log in Deal_Audit]
    E --> G
    F --> G

##🔒 Security Features

🛡️ HMAC-SHA256 signing for external API/webhook calls
🔑 Secrets stored in Zoho Vault or secure config module
♻️ Retry logic for failed notifications
✅ Role-based access within Zoho CRM

---

📝 Outcome

Timely follow-ups for every deal

Reduced leakage due to missed actions

Higher accountability through escalations

Improved visibility with centralized logging

---

##🤝 Contributing

Fork the repository

Create your feature branch (git checkout -b feature/amazing-feature)

Commit changes (git commit -m 'Add amazing feature')

Push branch (git push origin feature/amazing-feature)

Open a Pull Request

Development Guidelines:

Follow Zoho coding standards

Document Deluge functions clearly

Add test cases for workflows

---

##📞 Support

Issues: GitHub Issues

Email: shabeershah4777@gmail.com

---

##🔄 Changelog

v1.2.0 (Latest)
✅ Added escalation workflows
✅ Enhanced stalled deal detection
✅ Secure webhook signing
✅ Improved audit logging

v1.1.0
✅ Introduced custom Deal_Audit module
✅ Configurable thresholds & templates

v1.0.0
✅ Initial release with stage-based follow-up tasks

⭐ Star this repository if you found it helpful!
Made with ❤️ by Syed Shabeer Abbas Shah

