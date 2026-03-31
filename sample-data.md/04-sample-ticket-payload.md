# Sample Ticket Payload (Sanitized)

---

## **Overview**

This file shows the final payload used to create a ticket in the ticketing system.

It represents the last stage of the automation pipeline, where normalized alert data and AI-generated analysis are combined into a structured format suitable for case creation.

Sensitive details such as hostnames, email addresses, and internal links have been sanitized while preserving the overall structure and intent.

---

## **What This Represents**

This payload reflects the exact data sent from n8n to the ticketing system API.

It includes both structured alert fields and contextual analysis, ensuring that each ticket contains enough information for an analyst to begin investigation without needing to reference other systems immediately.

---

## **Why It Matters**

This stage is critical because it ensures alerts are not only detected and communicated, but also formally tracked.

By converting alerts into tickets, the workflow creates accountability, enables case management, and supports a structured incident response process.

---

## **Example Ticket Payload**

```json
{
  "alert": true,
  "source": "API",
  "system": "Elastic",
  "contact_email": "redacted@example.com",
  "subject": "SOC Alert - Mythic-C2-Apollo-Agent-Detected",
  "alert_type": "Command and Control Activity Detected",
  "rule_name": "MyDFIR-Mythic-C2-Apollo-Agent-Detected",
  "host_name": "HOST-REDACTED",
  "command_line": "\"C:\\Users\\Public\\Downloads\\windows-update.exe\"",
  "image": "C:\\Users\\Public\\Downloads\\windows-update.exe",
  "original_file_name": "Apollo.exe",
  "event_time": "2026-03-29T18:27:33.748Z",
  "instructions": "Please investigate immediately.",
  "analysis": {
    "summary": "Alert triggered for suspected command-and-control agent execution on a host. The executable originated from a user-accessible directory and is associated with known malicious tooling.",
    "suspicion_level": "high",
    "likely_false_positive": false,
    "escalate": true
  }
}
```
---

## **Key Components**

The payload is structured to include both technical details and contextual information.

Fields such as `rule_name`, `host_name`, `command_line`, and `event_time` provide the core details of the alert, while the `analysis` section adds interpretation and severity context.

This combination ensures that the ticket is both informative and actionable.

---

## **Operational Context**

The ticket represents a potential command-and-control event that requires investigation.

The presence of a suspicious executable in a public directory, combined with detection logic tied to known malicious tooling, indicates behavior that should be treated as high priority.

This context explains why the alert is escalated and tracked within the ticketing system.

---

## **Key Takeaway**

This payload demonstrates how alert data is transformed into a structured case record, enabling consistent tracking, investigation, and response within a SOC workflow.
