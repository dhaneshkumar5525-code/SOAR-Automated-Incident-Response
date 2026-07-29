# Chapter 2: Project Overview

## 2.1 Project Overview

### This project demonstrates the development of a Security Orchestration, Automation, and Response (SOAR) solution that automates repetitive Security Operations Center (SOC) investigation tasks. The workflow integrates multiple cybersecurity platforms to enrich Indicators of Compromise (IOCs), calculate threat scores, classify alerts, and automatically create incident tickets.

### The automation pipeline simulates a real-world enterprise SOC environment where security alerts are continuously processed without manual intervention. By integrating threat intelligence platforms, workflow automation, and incident management systems, the solution significantly reduces investigation time while improving consistency and operational efficiency.

---

## 2.2 Project Workflow

### The project follows a structured workflow from alert generation to incident response.

### • Generate realistic cybersecurity alerts using Python.
### • Send alerts to the Tines SOAR platform through a webhook.
### • Extract and validate Indicators of Compromise (IOCs).
### • Query VirusTotal for IP and file hash reputation.
### • Query URLScan.io for URL reputation and analysis.
### • Calculate a threat risk score based on enrichment results.
### • Map detected activities to the MITRE ATT&CK Framework.
### • Classify alerts as malicious or benign.
### • Automatically create Jira incidents for malicious alerts.
### • Generate investigation comments and maintain standardized documentation.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/1a696001-c67f-45cc-8128-c27587490415" />

---

## 2.3 Project Components

### The SOAR solution consists of several integrated components that work together to automate the investigation process.

### • Python Alert Generator
### • Tines SOAR Platform
### • VirusTotal API
### • URLScan.io API
### • MITRE ATT&CK Framework
### • Jira Software

### Each component performs a specific role in the investigation pipeline, enabling automated threat enrichment, decision-making, and incident management.

---

## 2.4 Workflow Architecture

### The workflow begins with a generated security alert and passes through multiple automation stages before producing the final investigation outcome.

### The automation pipeline performs:

### • Alert Ingestion
### • IOC Extraction
### • Threat Intelligence Enrichment
### • Risk Score Calculation
### • MITRE ATT&CK Mapping
### • Alert Classification
### • Jira Ticket Creation
### • Investigation Comment Generation

### Every stage operates automatically, eliminating repetitive manual tasks performed by SOC analysts

---

## 2.5 Technologies Used

### The project integrates several cybersecurity tools and technologies to automate the complete investigation workflow.

### • Python
### • Tines SOAR
### • VirusTotal API
### • URLScan.io API
### • Jira Software
### • REST APIs
### • JSON
### • HTTP Webhooks
### • MITRE ATT&CK Framework

### These technologies work together to provide automated threat intelligence enrichment, orchestration, and incident response.


---

## 2.6 Key Features

### The implemented solution provides several enterprise-level SOC automation capabilities.

### • Automated alert ingestion.
### • IOC enrichment using external threat intelligence.
### • IP, URL, and file hash reputation analysis.
### • Threat risk score calculation.
### • MITRE ATT&CK technique mapping.
### • Automated alert classification.
### • Jira incident creation.
### • Automated analyst investigation comments.
### • Standardized investigation documentation.
### • Reduced manual SOC workload.



---
### 2.7 Project Outcome

### The completed SOAR solution successfully automates the end-to-end SOC investigation process. Every generated alert is enriched with threat intelligence, evaluated for risk, mapped to the MITRE ATT&CK Framework, and classified automatically. Malicious alerts generate Jira incidents with investigation comments, while benign alerts are documented without analyst intervention.

### The project demonstrates how SOAR platforms can improve SOC efficiency by reducing investigation time, minimizing human error, and providing consistent incident response across security operations.


