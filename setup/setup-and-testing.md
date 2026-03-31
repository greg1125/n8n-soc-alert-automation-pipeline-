# Setup and Testing

---

## **Overview**

This section documents how the SOC alert automation pipeline was built, configured, and validated within the lab environment.

Rather than only showing the final working state, this section explains the steps required to get each component running and connected, along with how the workflow was tested to confirm that it behaves as expected.

The goal is to demonstrate not just what the system does, but how it was actually implemented and verified.

For more information about how I built this, visit - https://github.com/greg1125/SOC-Detection-Engineering-lab

---

## **Purpose**

The purpose of this section is to make the project reproducible and to show the engineering process behind the workflow.

A working demo alone does not explain how the system was assembled or what challenges were encountered along the way. By documenting setup and testing, this section provides insight into how each part of the pipeline was configured and how the full workflow was validated.

This helps reinforce that the project reflects real hands-on work rather than a conceptual design.

---

## **Environment Setup**

The environment consists of multiple interconnected systems that were configured to support detection, automation, and incident tracking.

This includes Elasticsearch and Kibana for the SIEM layer, Elastic Agents for telemetry collection, n8n for workflow automation, Gmail for notifications, and osTicket for case management.

Each system was configured individually and then connected through APIs and workflow logic to create a complete pipeline.

---

## **Elasticsearch and Kibana Setup**

The SIEM layer was configured first to ensure that alert data could be generated and retrieved.

Elasticsearch was set up to receive and index logs from endpoint systems, while Kibana was used to create detection rules and monitor alerts. Proper configuration of indices and data ingestion was necessary to ensure that alerts could be queried by the automation workflow.

This step established the foundation for the rest of the pipeline.

---

## **Elastic Agent and Fleet Configuration**

Elastic Agents were deployed on endpoint systems and enrolled into Fleet for centralized management.

Fleet policies were configured to collect relevant telemetry such as security logs, authentication events, and process activity. This ensured that sufficient data was being generated for detection rules to trigger alerts.

Correct agent configuration was critical for producing meaningful alert data.

---

## **Detection Rule Validation**

Detection rules were created and tested within Kibana to ensure that alerts would be generated under expected conditions.

Test scenarios such as brute force attempts or suspicious activity were simulated to trigger these rules. The resulting alerts were verified in Kibana to confirm that they contained the expected fields and values.

This step ensured that the pipeline had valid input data before integrating automation.

---

## **n8n Workflow Setup**

The automation workflow was built inside n8n using a series of connected nodes.

Each node was configured to perform a specific task, including retrieving alert data, normalizing fields, generating AI analysis, sending emails, and creating tickets. Proper configuration of credentials, API endpoints, and data mappings was required to ensure that each step functioned correctly.

The workflow was tested incrementally to confirm that each node behaved as expected before connecting the full pipeline.

---

## **API Integration Configuration**

External integrations were configured to allow n8n to communicate with Elasticsearch, Gmail, and osTicket.

This included setting up authentication credentials, verifying API endpoints, and ensuring that requests were properly formatted. Each integration was tested individually to confirm connectivity before being used in the full workflow.

Reliable API communication was necessary for the pipeline to function end-to-end.

---

## **Email Configuration (Gmail)**

Gmail integration was configured to allow the workflow to send alert notifications.

This involved setting up authentication, defining the email format, and testing message delivery. The email content was validated to ensure that all fields and AI-generated analysis were displayed correctly.

This step confirmed that alerts could be successfully communicated outside of the automation platform.

---

## **Ticketing Configuration (osTicket)**

The osTicket system was configured to receive ticket creation requests from n8n.

This included setting up the API endpoint, verifying authentication, and defining the expected payload structure. Test tickets were created to ensure that the system correctly received and displayed alert data.

This step ensured that alerts could be tracked as formal cases.

---

## **End-to-End Workflow Testing**

Once all components were configured, the full workflow was tested from start to finish.

Test alerts were generated in Elasticsearch, retrieved by n8n, processed through normalization and analysis, sent via email, and submitted to osTicket. Each stage was monitored to confirm that data flowed correctly and that outputs matched expectations.

This end-to-end validation confirmed that the entire pipeline was functioning as intended.

---

## **Validation of Outputs**

The outputs of the workflow were reviewed to ensure accuracy and consistency.

Emails were checked for correct formatting and readability, while tickets were verified to contain all necessary information. Any discrepancies were identified and corrected to improve the reliability of the system.

This step ensured that the final outputs met the intended design goals.

---

## **Troubleshooting and Iteration**

During setup and testing, issues were identified and resolved through iterative adjustments.

This included fixing field mappings, correcting API configurations, and refining workflow logic. Each issue was addressed systematically to improve stability and consistency across the pipeline.

This iterative process reflects the practical nature of building and refining automation systems.

---

## **Operational Readiness**

After testing was complete, the workflow was configured to run on a schedule to simulate continuous operation.

This ensured that alerts would be processed automatically without manual intervention. The system was monitored to confirm that it continued to function reliably over time.

This step demonstrated that the pipeline could operate as a repeatable process rather than a one-time execution.

---

## **Security Engineering Perspective**

From a security engineering perspective, the setup and testing process highlights the importance of validation and reliability.

It shows that building an automation pipeline involves not only connecting components, but also ensuring that each part functions correctly and that the system behaves as expected under real conditions.

This reflects real-world practices where thorough testing is essential before deploying automation into production environments.

---

## **Documentation Goal**

The goal of this document is to provide a clear and detailed explanation of how the system was built and tested.

It is intended to help others understand the setup process, reproduce the environment if needed, and see the practical steps required to create a working SOC automation pipeline.

Together, this section demonstrates the full engineering process behind the project, from initial configuration to final validation.
