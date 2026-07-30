# SOAR-Automated-Incident-Response
<img width="1484" height="464" alt="image" src="https://github.com/user-attachments/assets/c2be9ed8-b931-4323-bace-de4c2efa6dd8" />

## Table of Contents

### • Project Overview
### • Project Architecture
### • Features
### • Technologies Used
### • Prerequisites
### • Project Workflow
### • Environment Setup
### • Python Alert Generator
### • Tines SOAR Workflow
### • VirusTotal Integration
### • URLScan.io Integration
### • Threat Score Calculation
### • MITRE ATT&CK Mapping
### • Jira Automation
### • Benign Workflow
### • Malicious Workflow
### • Testing the Pipeline
### • Sample Outputs
### • Challenges Faced
### • Troubleshooting
### • Future Enhancements
### • Conclusion
### • References

# 1. Project Overview

## Introduction

### This project demonstrates an automated SOAR workflow that streamlines incident response from alert generation to ticket creation. It integrates multiple security tools to enrich alerts, assess threats, and automate response actions with minimal manual intervention.
<img width="971" height="696" alt="image" src="https://github.com/user-attachments/assets/332b15a6-2b9f-46f9-ae58-2e6c3b0a465e" />

### • **Purpose:** Automate the incident response process and reduce manual investigation.
### • **Workflow:** Generate alerts, enrich with threat intelligence, calculate threat score, map to MITRE ATT&CK, and create Jira tickets.
### • **Key Components:** Python, Tines, VirusTotal, URLScan.io, MITRE ATT&CK, and Jira.
### • **Benefits:** Faster response, consistent investigations, reduced analyst workload, and improved efficiency.

---

## What is SOAR?

### SOAR (Security Orchestration, Automation, and Response) is a platform that integrates multiple security tools and automates incident response workflows. It helps SOC teams investigate and respond to threats faster by reducing repetitive manual tasks.
<img width="1120" height="666" alt="image" src="https://github.com/user-attachments/assets/e81b00c6-f57a-462f-a3bd-4a6045222568" />


### • **Purpose:** Automate and orchestrate security operations.
### • **How it Works:** Collects alerts, enriches data, applies decision logic, and performs automated actions.
### • **Common Integrations:** SIEM, EDR, Threat Intelligence, Firewalls, and Ticketing Systems.
### • **Advantages:** Faster response, improved consistency, reduced manual effort, and better analyst productivity.

---

## What Problem Does SOAR Solve?

### Security teams receive a large volume of alerts every day, making manual investigation slow and inefficient. SOAR automates repetitive tasks, enriches alerts with threat intelligence, and prioritizes incidents for faster response.
<img width="739" height="475" alt="image" src="https://github.com/user-attachments/assets/25b68eca-d08d-483b-b04d-f9407534d4b3" />

### • **Challenges:** Alert fatigue, manual investigations, and delayed response.
### • **Automation:** Performs IOC validation, enrichment, and predefined response actions.
### • **Impact:** Reduces Mean Time to Detect (MTTD) and Mean Time to Respond (MTTR).
### • **Benefit:** Allows analysts to focus on genuine security threats.

---

## Why Security Automation is Important

### Security automation reduces the time and effort required to investigate and respond to cyber threats. It improves consistency, minimizes human error, and enables security teams to handle more incidents efficiently.
<img width="766" height="400" alt="image" src="https://github.com/user-attachments/assets/86b9f74b-9f3f-42d2-acd2-53c96a1b95c0" />

### • **Efficiency:** Automates repetitive security tasks.
### • **Accuracy:** Reduces human errors during investigations.
### • **Speed:** Responds to incidents much faster than manual processes.
### • **Scalability:** Helps SOC teams manage a growing number of security alerts.

---

## Why This Project Was Built

### This project was built to demonstrate a practical SOAR implementation using real-world security tools and workflows. It showcases how automation can improve incident response while providing hands-on experience with enterprise SOC operations.
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/9ffb0f9a-38c9-45b7-b0b2-bf7b5e3beac7" />

### • **Learning Goal:** Gain practical experience with SOAR automation.
### • **Implementation:** Integrates Python, Tines, VirusTotal, URLScan.io, MITRE ATT&CK, and Jira.
### • **SOC Simulation:** Replicates a real-world incident response workflow.
### • **Outcome:** Demonstrates automation and incident response skills for cybersecurity portfolios and interviews.


## Project Description

### This project demonstrates an end-to-end Security Orchestration, Automation, and Response (SOAR) workflow that automates the Security Operations Center (SOC) investigation process. It integrates Python, Tines, VirusTotal, URLScan.io, MITRE ATT&CK, and Jira to enrich alerts, classify threats, and automate incident response.
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/dfff8ba7-aae9-4615-a175-1a5f5ac75328" />


### • Generates and processes realistic cybersecurity alerts.
### • Enriches IOCs, calculates threat scores, and maps attacks to MITRE ATT&CK.
### • Automatically classifies alerts and creates Jira incidents for malicious activity.

---

## Project Objective

### The primary objective of this project is to automate repetitive SOC investigation tasks and demonstrate how multiple security technologies can be integrated into a single enterprise SOAR workflow. The automation reduces manual effort while improving investigation speed, accuracy, and consistency.

### • Automate alert investigation and threat intelligence enrichment.
### • Integrate multiple security platforms into a unified workflow.
### • Improve SOC efficiency and reduce analyst workload.

---

## End Goal

### The end goal of this project is to build a complete enterprise-style SOAR automation pipeline that processes security alerts from generation to incident response. The solution standardizes investigations, accelerates response times, and minimizes manual intervention.
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/07affadb-b548-46eb-adae-895cefe617f5" />


### • Automatically investigate, classify, and respond to security alerts.
### • Create standardized Jira incidents and investigation documentation.
### • Enhance SOC efficiency, scalability, and incident response capabilities.

### Key Features
### Automated Alert Generation
### IOC Enrichment
### VirusTotal Integration
### URLScan Integration
### Threat Score Calculation
### MITRE ATT&CK Mapping
### Automatic Classification
### Jira Incident Creation
### Automated Analyst Comments
### Complete SOAR Workflow

# Project Architecture

## High-Level Architecture

### The project architecture follows an end-to-end SOAR workflow where security alerts are generated, enriched with threat intelligence, analyzed, classified, and automatically converted into Jira incidents. Each component performs a specific task within the investigation pipeline, enabling a fully automated Security Operations Center (SOC) workflow.

<img width="981" height="887" alt="image" src="https://github.com/user-attachments/assets/a8b8c214-38cc-43e5-aff2-b8578b6939b4" />


---

<img width="640" height="360" alt="image" src="https://github.com/user-attachments/assets/e4cf73d5-df85-4f64-8e35-6973760e61aa" />


## Webhook

### The Webhook serves as the entry point of the workflow. It receives security alerts generated by the Python Alert Generator in JSON format and triggers the automation process within the Tines SOAR platform.

### • Receives incoming security alerts.
### • Parses the JSON alert payload.
### • Initiates the SOAR workflow.

---

## URLScan.io Integration

### URLScan.io analyzes the destination URL contained in the alert to determine whether the website is malicious or suspicious. The workflow first submits the URL for scanning and then retrieves the completed scan results.

### • Submits suspicious URLs for analysis.
### • Retrieves scan results and threat verdicts.
### • Identifies malicious or suspicious websites.

---

## VirusTotal File Report

### VirusTotal analyzes the file hash included in the alert and checks its reputation against multiple antivirus engines. This helps determine whether the associated file has previously been identified as malicious.

### • Validates suspicious file hashes.
### • Retrieves malware detection results.
### • Provides file reputation information.

---

## VirusTotal IP Address Report

### VirusTotal also analyzes the source IP address associated with the alert to determine whether it has been reported as malicious or involved in previous malicious activities.

### • Performs IP reputation analysis.
### • Retrieves threat intelligence data.
### • Identifies malicious IP addresses.

---

## Run Script Components

### Multiple Python scripts process the API responses returned by VirusTotal and URLScan.io. These scripts extract relevant threat intelligence, calculate threat scores, and prepare the data for the next stages of the workflow.

### • Process API responses.
### • Extract relevant IOC information.
### • Calculate threat scores.
### • Prepare data for automation.

---

## Event Transform

### Event Transform actions restructure and format the collected data into a standardized format that can be consumed by downstream workflow components.

### • Format API responses.
### • Normalize investigation data.
### • Prepare output for decision making.

---

## Condition

### The Condition block acts as the decision engine of the workflow. It evaluates the threat intelligence collected from VirusTotal and URLScan.io and determines whether the alert should be treated as malicious or benign.

### • Evaluates enrichment results.
### • Applies predefined decision logic.
### • Routes alerts based on severity.

---

## Jira Integration

### Based on the decision outcome, the workflow automatically creates a Jira incident containing all investigation details. After creating the issue, additional investigation comments are automatically added for documentation and analyst reference.

### • Automatically creates Jira incidents.
### • Adds investigation comments.
### • Maintains standardized incident documentation.

---

## Complete Workflow

### The complete architecture integrates Python, Tines, VirusTotal, URLScan.io, and Jira into a single automated investigation pipeline. From receiving an alert to generating an incident ticket, every stage is performed automatically, significantly reducing manual investigation effort while improving SOC efficiency and consistency.

### • Automated alert ingestion.
### • Threat intelligence enrichment.
### • IOC validation and analysis.
### • Threat classification.
### • Automated Jira incident creation.
### • Standardized investigation documentation.

# Technologies Used

### The project integrates multiple cybersecurity tools and technologies to automate the Security Operations Center (SOC) investigation workflow. Each tool and workflow component performs a specific function, enabling automated threat intelligence enrichment, workflow orchestration, and incident response.

| **Tool / Component** | **Purpose** |
|----------------------|-------------|
| **Python** | Generates realistic cybersecurity alerts and sends them to the Tines SOAR platform through webhooks. |
| **Tines** | Acts as the central SOAR platform that orchestrates the entire automation workflow. |
| **Webhook** | Receives incoming security alerts and triggers the automation pipeline. |
| **VirusTotal** | Performs IP address and file hash reputation analysis for IOC enrichment. |
| **URLScan.io** | Analyzes suspicious URLs and retrieves website reputation information. |
| **Run Script** | Processes API responses, extracts required fields, calculates threat scores, and prepares data for subsequent workflow actions. |
| **Event Transform** | Transforms and formats API responses into a standardized JSON structure for downstream processing. |
| **Condition** | Evaluates the enrichment results and classifies alerts as malicious or benign using predefined logic. |
| **Jira Software** | Automatically creates incident tickets and investigation comments for malicious alerts. |
| **MITRE ATT&CK Framework** | Maps detected threats to attacker tactics and techniques for standardized threat classification. |
| **REST APIs** | Enables communication between Python, Tines, VirusTotal, URLScan.io, and Jira. |
| **HTTP Webhooks** | Transfers alert data into the SOAR workflow. |
| **JSON** | Standard data format used for exchanging alerts and API responses between all components. |

# Prerequisites

## Software

### Before setting up and running this project, ensure the following software, accounts, and API services are installed and configured correctly.

| **Requirement** | **Purpose** |
|-----------------|-------------|
| **Python** | Used to generate and send simulated cybersecurity alerts to the SOAR workflow. |
| **Visual Studio Code (VS Code)** | Code editor used to develop, modify, and execute the Python scripts. |
| **Git** | Used for version control and cloning the project repository. |
| **Tines Account** | Hosts and executes the SOAR automation workflow. |
| **VirusTotal API Key** | Enables IP address and file hash reputation analysis. |
| **URLScan.io API Key** | Allows automated URL scanning and reputation analysis. |
| **Jira Account** | Used to automatically create and manage incident tickets generated by the workflow. |


## API Keys

### API keys are unique authentication tokens used to securely access external services and APIs. In this project, API keys are required to authenticate requests made to VirusTotal, URLScan.io, and Jira, allowing the SOAR workflow to automatically retrieve threat intelligence and create incident tickets without requiring manual authentication.

### • **How to Obtain:** Create an account on the required platform (VirusTotal, URLScan.io, or Jira). Navigate to the **API**, **Developer**, or **Account Settings** section, generate an API key or API token, and securely copy it for later use.
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/39a3d67d-fc2c-403b-b65b-48431ef8f5e8" />


### • **How to Use:** Configure the API key or token as a credential within the Tines SOAR platform or include it in the HTTP request header. Tines automatically attaches the appropriate credential whenever it communicates with the external service.

### • **How It Works:** When the workflow sends an API request, the authentication key is included in the request header. The external service verifies the key, authenticates the request, and returns the requested information or performs the requested action if the credentials are valid.

### • **VirusTotal API Key:** Used to query the VirusTotal API for IP address and file hash reputation. It retrieves threat intelligence, detection statistics, and malware analysis results to determine whether an Indicator of Compromise (IOC) is malicious.

### • **URLScan.io API Key:** Used to submit suspicious URLs for analysis and retrieve scan results. It provides website reputation, behavioral analysis, and threat verdicts that help identify malicious or phishing websites.

### • **Jira API Token:** Used to authenticate with Jira Software and automatically create incident tickets, add investigation comments, and manage incident records directly from the SOAR workflow.

### • **Why API Keys Are Required:** API keys provide secure and authorized access to external platforms, prevent unauthorized usage, enable automated communication between multiple security tools, and ensure the entire SOAR workflow operates without manual intervention.

## Python

### Python is the core programming language used in this project to simulate security alerts and trigger the SOAR workflow. It generates realistic cybersecurity events containing Indicators of Compromise (IOCs) and sends them to the Tines Webhook using HTTP requests, enabling automated testing of the complete incident response pipeline.
<img width="1601" height="1032" alt="image" src="https://github.com/user-attachments/assets/e0ffeb66-00e9-4600-8f89-6bf0529bf96b" />

### Download the latest windows version
### • **Programming Language:** Python 3.13.14 (or the latest stable version).
### • **Purpose:** Generate and transmit simulated cybersecurity alerts.
### • **Libraries Used:** `requests`, `json`, `random`, `time`, `datetime`, and `uuid`.
### • **Functionality:** Creates randomized alerts containing IP addresses, URLs, file hashes, timestamps, and severity levels.
### • **Communication:** Sends alerts to the Tines SOAR platform through HTTP POST requests.
### • **Benefit:** Provides a lightweight, flexible, and resource-efficient method for testing the complete SOAR automation workflow without requiring a full SIEM deployment.

### Here is the script used to forward logs to the webhooks from the windows machine
<img width="2348" height="8960" alt="BoilerplateHub-code-snippet" src="https://github.com/user-attachments/assets/d60116f3-0dd6-41cd-9f60-47184670f0da" />
