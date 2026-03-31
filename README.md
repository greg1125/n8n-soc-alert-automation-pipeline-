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
