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

```
---

## **Repository Structure**

The repository is organized into multiple folders that document the workflow architecture, individual processing stages, setup process, example outputs, and supporting screenshots.

Each part of the repository is designed to represent a specific layer of the automation pipeline, allowing the project to be broken down into logical, understandable sections that reflect how a real SOC workflow is built and maintained.

Together, this structure ensures that the project is not only functional, but also readable, presentable, and scalable as additional automation features or integrations are added over time.


---

## **Architecture Folder**

The architecture folder provides a high-level overview of how the automation pipeline is structured and how each major component interacts within the overall SOC workflow.

Rather than focusing on individual node configurations, this section is intended to explain the design decisions behind the workflow and how data flows between systems from ingestion through alert escalation.

Together, these documents establish a clear understanding of the system before diving into the more detailed workflow and implementation-specific sections.

---

## **Workflows Folder**

The workflows folder contains detailed documentation for each major functional stage of the automation pipeline, breaking down how alert data is processed from raw ingestion to final delivery.

Each workflow focuses on a specific responsibility such as field normalization, AI-assisted alert analysis, email alerting, or ticket creation, allowing each part of the pipeline to be understood both independently and as part of the larger system.

Together, these workflow documents demonstrate how automation can be modularized while still contributing to a unified SOC alert handling process.

---

## **Setup Folder**

The setup folder documents how the automation pipeline was built, configured, and validated within the lab environment.

This section explains the reasoning behind implementation decisions, the order in which components were configured, and how each stage of the workflow was tested to ensure proper functionality.

Together, these setup details provide reproducibility and demonstrate the practical engineering effort required to move from concept to a working SOC automation pipeline.

---

## **Sample Data Folder**

The sample-data folder contains representative examples of alert data as it progresses through each stage of the workflow.

These examples illustrate how raw alert data is transformed through normalization, enriched through AI-generated analysis, and structured for delivery into notification and ticketing systems.

Together, these samples provide a concrete view of how data evolves throughout the pipeline, making the workflow easier to understand and validate.


---

## **Security Engineering Relevance**

This project reflects security engineering practices by focusing on improving the operational usability of alerts rather than only detecting malicious activity.

Each stage of the workflow is designed to reduce analyst friction, preserve critical context, and convert raw detection data into actionable intelligence that can be used within a structured response process.

Together, these design decisions demonstrate how automation can enhance SOC efficiency by bridging the gap between detection, analysis, communication, and incident tracking.

---

## **Key Skills Demonstrated**

This project demonstrates practical experience with workflow automation, alert normalization, AI-assisted triage, email-based alerting, and ticketing system integration.

Each of these skills contributes to real-world SOC and security engineering work by showing how raw telemetry can be transformed into structured outputs that analysts can consistently act upon.

Together, these capabilities highlight an understanding of how detection engineering extends into full operational workflows.

---

## **Documentation Goal**

This repository is intended to serve as both a technical reference and a portfolio project that showcases the design and implementation of a complete SOC alert automation workflow.

Each section is written to be clear, technically grounded, and detailed enough to demonstrate how the system supports real-world security operations.

Together, the documentation presents the project as more than a simple automation demo, positioning it as a practical example of security engineering that connects detection, triage, notification, and incident response.
