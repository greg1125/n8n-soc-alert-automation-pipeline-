# Sample Alert Document (Sanitized)

---

## **Overview**

This file contains a sanitized example of an alert document retrieved from the `soc_ticket_queue` index.

Sensitive details such as internal IP addresses, hostnames, and links have been generalized to preserve privacy while still accurately representing the structure and content of the alert.

---

## **What This Represents**

This document represents how an alert is stored in Elasticsearch after it has been processed by the automation pipeline.

It includes both detection-related fields and additional metadata added by the workflow to support notification and ticketing.

---

## **Why It Matters**

This example demonstrates how alert data is structured once it is ready for operational use.

It shows how detection context, system metadata, and workflow status are combined into a single document that can be used for downstream automation.

---

## **Example Alert Document**

```json
{
  "_index": "soc_ticket_queue",
  "_id": "REDACTED_ID",
  "_source": {
    "alert": true,
    "autorespond": true,
    "source": "API",
    "system": "Elastic",
    "contact_email": "redacted@example.com",
    "subject": "Mythic-C2-Apollo-Agent-Detected - MyDFIR-Mythic-C2-Apollo-Agent-Detected",
    "alert_type": "Mythic / Apollo Agent Detected",
    "rule_name": "MyDFIR-Mythic-C2-Apollo-Agent-Detected",
    "host_hostname": "HOST-REDACTED",
    "host_name": "host-redacted",
    "command_line": "\"C:\\Users\\Public\\Downloads\\windows-update.exe\"",
    "image": "C:\\Users\\Public\\Downloads\\windows-update.exe",
    "original_file_name": "Apollo.exe",
    "event_time": "2026-03-29T18:08:33.750Z",
    "kibana_link": "http://<kibana-instance>/app/security/...",
    "instructions": "Please investigate immediately.",
    "ticket_sent": true,
    "status": "sent"
  }
}
```
---

## **Key Fields Explained**

The alert includes several important fields that provide context for the detected activity.

The `rule_name` identifies the detection logic that triggered the alert, while `alert_type` provides a broader classification of the activity. The `host_name` and `host_hostname` fields identify the affected system, and `event_time` indicates when the activity occurred.

Fields such as `command_line`, `image`, and `original_file_name` provide visibility into the process execution associated with the alert. These fields are especially useful when identifying suspicious or potentially malicious binaries.

The `kibana_link` allows direct access to the alert within the SIEM for further investigation, while `ticket_sent` and `status` indicate that the alert has already been processed by the automation workflow.

---

## **Operational Context**

This alert represents a detection of activity consistent with a command-and-control agent.

The executable name and file path suggest an attempt to disguise malicious activity as a legitimate process. Combined with the detection rule, this indicates behavior that warrants further investigation.

This context helps explain why the alert is escalated and tracked within the workflow.

---

## **Key Takeaway**

This document shows how alert data is structured after being processed by the automation pipeline, providing a clear and actionable format for downstream systems such as email notifications and ticketing.
