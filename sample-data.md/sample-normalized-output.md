# Sample Normalized Output

---

## **Overview**

This file shows the alert after it has passed through the field normalization stage.

The data has been simplified and restructured into a clean format that is easier to work with in the rest of the workflow.

---

## **What This Represents**

This output represents the standardized version of the alert that is used throughout the automation pipeline.

All unnecessary fields have been removed, nested structures have been flattened, and key values have been renamed into consistent, readable field names.

---

## **Why It Matters**

Normalization ensures that all downstream processes, including AI analysis, email formatting, and ticket creation, operate on consistent and predictable data.

Without this step, each stage of the workflow would require additional logic to handle variations in alert structure.

---

## **Example Normalized Output**

```json
{
  "rule_name": "MyDFIR-Mythic-C2-Apollo-Agent-Detected",
  "alert_type": "Mythic / Apollo Agent Detected",
  "host_name": "host-redacted",
  "host_hostname": "HOST-REDACTED",
  "command_line": "\"C:\\Users\\Public\\Downloads\\windows-update.exe\"",
  "image": "C:\\Users\\Public\\Downloads\\windows-update.exe",
  "original_file_name": "Apollo.exe",
  "event_time": "2026-03-29T18:08:33.750Z",
  "kibana_link": "http://<kibana-instance>/app/security/...",
  "instructions": "Please investigate immediately."
}

---

## **Key Transformations**

The normalization process restructures the alert into a more usable format.

Nested fields are flattened into a single level, field names are standardized, and only the most relevant values are retained. This makes the data easier to reference within n8n and improves readability for downstream outputs.

---

## **Key Takeaway**

This normalized output serves as the foundation for the rest of the workflow, enabling consistent processing, analysis, and delivery of alert data.
