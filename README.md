# n8n SOC Alert Automation Pipeline

---

## **Project Overview**

The `n8n-soc-alert-automation-pipeline` project documents an automated alert handling workflow built as part of a larger SOC detection lab.

The pipeline is designed to retrieve raw security alert data, normalize the most important fields, generate AI-assisted triage content, send a formatted email notification, and create a ticket for investigation tracking.

Together, these components form a practical alert automation workflow that reflects how detection output can be transformed into a more readable, actionable, and trackable incident response process.

---

## **Project Purpose**

This repository was created to show how workflow automation can support security operations beyond simply generating alerts.

Many homelab security projects stop once a detection fires, but this project continues through the next operational steps by making the alert easier to interpret, sending a notification, and opening a case for follow-up.

Together, these stages demonstrate a more complete security engineering mindset by connecting detection logic to triage, communication, and incident tracking.

---

## **Workflow Summary**

The pipeline follows a structured sequence that moves alert data through ingestion, normalization, AI analysis, and delivery steps.

Each stage improves the quality and usefulness of the alert by converting raw technical data into formats that are easier for an analyst to review and act on.

Together, these stages create a repeatable workflow that supports both immediate alert visibility and longer-term investigation tracking.

```text
Schedule Trigger
    ↓
HTTP Request
    ↓
Edit Fields
    ↓
Message a model
    ↓
ai_response
    ↓
ai_parsed
    ↓
Send to Gmail
    ↓
osTicket HTTP Request


Repository Structure

The repository is organized into folders that document the workflow architecture, individual processing stages, setup process, example outputs, and supporting screenshots.

Each section is intended to explain not only what the workflow does, but also why each part matters from a SOC and security engineering perspective.

Together, these folders make the project easier to understand, easier to present publicly, and easier to expand later as the automation pipeline grows.

n8n-soc-alert-automation-pipeline/
├── README.md
├── architecture/
│   ├── workflow-diagram.md
│   └── system-overview.md
├── workflows/
│   ├── field-normalization.md
│   ├── alert-analysis.md
│   ├── ticket-creation.md
│   └── gmail-alerting.md
├── setup/
│   └── setup-and-testing.md
├── sample-data/
│   ├── sample-alert-document.md
│   ├── sample-normalized-output.md
│   ├── sample-ai-analysis.md
│   └── sample-ticket-payload.md
└── screenshots/
    ├── n8n-workflow.png
    ├── edit-fields-node.png
    ├── chatgpt-node.png
    ├── osticket-ticket.png
    └── gmail-alert.png
Architecture Folder

The architecture folder explains how the workflow is structured and how its major components fit together within the larger SOC alert handling process.

Each file in this folder is meant to describe the overall design of the automation pipeline rather than focusing only on individual nodes or screenshots.

Together, these documents provide the high-level view needed to understand how the system works before going deeper into the workflow-specific details.

Workflows Folder

The workflows folder contains detailed documentation for the major functional stages of the automation pipeline.

Each file focuses on an important workflow area such as field normalization, AI-assisted alert analysis, email alerting, or ticket creation, explaining both the technical role of the stage and its value in the overall SOC process.

Together, these documents break the pipeline into understandable pieces so the project can be studied, maintained, and presented more effectively.

Setup Folder

The setup folder documents how the workflow was built, configured, and tested inside the lab environment.

Each setup note is intended to explain the logic behind the implementation, the sequence of configuration steps, and the validation process used to confirm that each part of the workflow was functioning correctly.

Together, this section makes the project more reproducible and shows the practical engineering work required to move from design to a working automation pipeline.

Sample Data Folder

The sample-data folder contains example inputs and outputs that show how alert data changes as it moves through the workflow.

Each sample file represents a different stage of the pipeline, helping demonstrate how raw alert content is normalized, enriched with AI analysis, and prepared for final delivery into notification and ticketing systems.

Together, these examples make the workflow easier to understand by showing the actual transformation of data rather than only describing it conceptually.

Screenshots Folder

The screenshots folder contains visual references that support the written documentation throughout the repository.

Each image is intended to show a meaningful part of the workflow, such as the full n8n pipeline, important node configurations, email delivery output, or the final osTicket case that results from the automation.

Together, these screenshots provide proof of implementation and help make the project more concrete, readable, and portfolio-ready.

Security Engineering Relevance

This project reflects security engineering work because it focuses on improving the operational usefulness of alerts rather than only detecting suspicious activity.

Each part of the workflow is designed to reduce analyst friction, improve readability, preserve important context, and connect alert generation to a structured response process.

Together, these design choices show how automation can be used to strengthen SOC workflows by making alerts easier to process, communicate, and investigate.

Key Skills Demonstrated

This project demonstrates hands-on experience with workflow automation, alert normalization, AI-assisted triage, email-based alerting, and ticketing system integration.

Each of these areas supports practical SOC and security engineering work by showing how raw telemetry can be transformed into operational outputs that analysts can use in a repeatable way.

Together, these skills make the project a strong example of how detection engineering can extend into real workflow and response automation.

Future Improvements

The current pipeline provides a strong foundation, but it can be expanded with additional logic as the lab environment grows and new use cases are added.

Possible future improvements include enrichment from threat intelligence sources, duplicate alert suppression, severity-based branching, automatic ticket assignment, tagging by detection family, and additional delivery channels such as Slack or Teams.

Together, these possible enhancements show how the workflow can evolve from a focused lab project into a more mature and feature-rich SOC automation pipeline.

Documentation Goal

This repository is intended to be both a technical reference and a portfolio project that shows the thought process behind building a practical alert automation workflow.

Each document is written to explain the project in a way that is readable, technically grounded, and detailed enough to show how the workflow supports real SOC functions.

Together, the files in this repository present the project not just as an automation demo, but as an example of security engineering work that connects detection, triage, notification, and incident tracking.
