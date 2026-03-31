# Field Normalization

---

## **Overview**

The field normalization stage is responsible for transforming raw alert data into a structured format that can be consistently used throughout the automation pipeline.

When alert data is retrieved from Elasticsearch, it typically contains deeply nested fields, inconsistent naming conventions, and additional metadata that may not be useful during initial triage. This stage focuses on extracting only the most relevant information and reshaping it into a clean, predictable structure.

By doing this early in the workflow, all downstream processes operate on standardized data, which improves reliability and readability.

---

## **Purpose**

The purpose of field normalization is to reduce noise and ensure that only meaningful data is passed forward.

Raw alerts often contain far more information than is needed for notification or ticket creation. If this data is left unfiltered, it can make emails harder to read, increase the complexity of automation logic, and introduce inconsistencies across different alert types.

Normalization solves this by selecting key fields and presenting them in a uniform way that can be reused across multiple stages of the workflow.

---

## **Role in the Workflow**

Field normalization occurs immediately after the alert data is retrieved from Elasticsearch.

At this point in the workflow, the alert exists as a raw document. The normalization stage acts as a filter and transformer, preparing the alert for AI analysis, email formatting, and ticket creation.

Because all later steps depend on these normalized values, this stage acts as a foundation for the rest of the pipeline.

---

## **Key Fields Extracted**

The normalization process focuses on extracting the fields that are most useful during triage and investigation.

These fields typically include the rule name, the affected host, the source IP address, the associated username, the number of events that triggered the alert, and a link back to Kibana for deeper investigation.

By isolating these values, the workflow ensures that the most important context is always available without requiring an analyst to parse a full raw alert document.

---

## **Example Field Mapping**

The transformation performed during this stage can be represented as a mapping between raw alert fields and normalized output fields.

The raw alert may contain nested JSON values, while the normalized output presents those values in a simplified structure that is easier to use.

```text
Raw Field                                      → Normalized Field
---------------------------------------------------------------
_source.kibana.alert.rule.name                 → rule_name
_source.host.name                              → host_name
_source.source.ip                              → source_ip
_source.user.name                              → username
_source.kibana.alert.threshold_result.count    → event_count
_source.kibana.alert.url                       → kibana_link

```

---

## **Data Simplification**

One of the main goals of this stage is to simplify the structure of the alert data.

Instead of passing nested objects and arrays through the workflow, the normalization process flattens the data into a set of key-value pairs. This makes it easier to reference fields in n8n expressions and reduces the likelihood of errors caused by missing or incorrectly structured data.

This simplification also makes the data more readable when it is later included in emails or tickets.

---

## **Handling Missing Data**

Not all alerts contain every field, so the normalization process must account for missing or undefined values.

In these cases, default values such as "N/A" are used to ensure that the workflow does not break and that the output remains consistent.

This approach prevents errors in downstream nodes and ensures that all generated notifications and tickets maintain a uniform format.

---

## **Impact on AI Analysis**

Field normalization directly improves the quality of AI-assisted analysis.

By providing a clean and structured input, the model receives only the most relevant information, which leads to clearer and more focused summaries. If raw data were passed directly into the model, unnecessary fields could reduce the quality of the generated output.

This stage therefore plays an important role in ensuring that AI analysis is both accurate and useful.

---

## **Impact on Email Formatting**

Normalized fields are used to build the structure of the email notification.

Because the data is already simplified, the email can be constructed in a clean and organized way without requiring complex parsing logic. Each field can be inserted directly into the email template, making the final output easier to read and understand.

This improves the overall effectiveness of the alert notification process.

---

## **Impact on Ticket Creation**

The same normalized data is also used when creating tickets in osTicket.

By using a consistent structure, the ticket payload can be generated reliably for every alert. This ensures that all tickets contain the same key pieces of information, which makes them easier to review and track.

Consistency at this stage is important for maintaining a structured incident response process.

---

## **Operational Value**

From an operational standpoint, field normalization reduces the cognitive load on analysts.

Instead of working with raw JSON data, analysts receive alerts that already highlight the most important details. This allows them to quickly understand what happened and decide on next steps without spending time parsing unnecessary information.

This improvement in clarity and efficiency is one of the main benefits of the automation pipeline.

---

## **Security Engineering Perspective**

From a security engineering perspective, field normalization is a critical step in building reliable automation.

It ensures that data flowing through the system is predictable and consistent, which reduces the likelihood of errors and simplifies integration between different components.

This reflects real-world practices where data transformation and standardization are essential for scalable and maintainable systems.

---

## **Documentation Goal**

The goal of this document is to explain how raw alert data is transformed into a structured format that supports the rest of the workflow.

It provides insight into what fields are selected, how they are mapped, and why normalization is necessary for effective automation.

Together, this section helps demonstrate that the workflow is designed not just to process alerts, but to improve their usability at every stage.
