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
<img width="1854" height="1400" alt="row-1-column-1 (8)" src="https://github.com/user-attachments/assets/f68f0d8b-ccd6-42df-a5c5-9bb6ffd4824b" />
<img width="1854" height="1400" alt="row-2-column-1" src="https://github.com/user-attachments/assets/8c81c724-b415-4e7a-a8db-662bfe6ad368" />
<img width="1854" height="1400" alt="row-3-column-1" src="https://github.com/user-attachments/assets/b367cd46-8707-4bd6-afa4-e93dd0a101ec" />
<img width="1854" height="1400" alt="row-4-column-1" src="https://github.com/user-attachments/assets/93d55a02-93f0-4260-a40d-eca50b922155" />
<img width="1854" height="1400" alt="row-5-column-1" src="https://github.com/user-attachments/assets/dcfe028d-7cb0-4019-8635-50f0eba78983" />
<img width="1854" height="654" alt="row-6-column-1" src="https://github.com/user-attachments/assets/b53d2e79-2fac-4840-b65c-8cc3043a9813" />

### Replace the URL with the webhooks URL in the tines 
## Tines Account

### A Tines account is required to build, manage, and execute the SOAR automation workflow. Tines acts as the central orchestration platform that receives security alerts, integrates with external services, applies decision logic, and automates incident response actions throughout the project.
<img width="1871" height="832" alt="image" src="https://github.com/user-attachments/assets/a0b340be-f78f-408e-a2a3-3322cd10d900" />


### • **How to Obtain:** Create a free account on the Tines platform and access your personal workspace.
### • **Purpose:** Design, execute, and monitor the SOAR workflow.
### • **Usage:** Configure webhooks, API credentials, workflow actions, conditions, run scripts, and event transforms within the Tines interface.
### • **Integration:** Connects with Python, VirusTotal, URLScan.io, and Jira using REST APIs and webhooks.
### • **Benefit:** Centralizes the entire automation process, enabling end-to-end SOC investigation and automated incident response from a single platform.

## Jira Setup

### Jira is used as the incident management platform in this project to automatically create, track, and manage security incidents generated by the SOAR workflow. Once a malicious alert is detected, Tines communicates with the Jira REST API to create an incident ticket and add investigation details automatically.
<img width="1915" height="745" alt="image" src="https://github.com/user-attachments/assets/e46f7e79-cde1-43bf-84ff-6abdd3298341" />

### • **How to Obtain:** Create a Jira Cloud account and set up a project to store security incidents.
### • **API Configuration:** Generate an API token from your Atlassian account and use it with your Jira email address for authentication.
### • **Project Setup:** Create a Jira project, obtain the Project Key, and identify the Issue Type (such as Task or Incident) that will be created by the workflow.
### • **Integration:** Configure the Jira URL, email address, API token, and Project Key as credentials within the Tines SOAR platform.
### • **Purpose:** Automatically create incident tickets, update investigation details, and add analyst comments for malicious alerts.
### • **Benefit:** Centralizes incident management, standardizes documentation, improves collaboration, and provides complete tracking of security investigations.

# Python Alert Generator

## Overview

### The Python Alert Generator is the starting point of the SOAR automation workflow. It was developed to simulate a Security Information and Event Management (SIEM) system by generating realistic cybersecurity alerts. Instead of requiring a production SIEM solution, the script creates structured security events containing Indicators of Compromise (IOCs) such as IP addresses, file hashes, URLs, timestamps, attack types, severity levels, and MITRE ATT&CK information.

### The generated alerts are transmitted to the Tines SOAR platform through a Webhook, where the automated investigation workflow begins. This allows the complete incident response pipeline to be tested using simulated alerts while closely replicating how enterprise SOC environments process security events.

### • **Purpose:** Simulate realistic cybersecurity alerts.

### • **Platform:** Python 3.

### • **Output:** JSON formatted security alerts.

### • **Communication:** HTTP POST requests using Webhooks.

### • **Destination:** Tines SOAR Platform.

### • **Benefit:** Provides a lightweight alternative to deploying a full SIEM solution for testing and demonstration purposes.

---

## Project Structure

### The Python Alert Generator is implemented using a single Python script named **multi_log_pusher.py**. Although compact, the script contains multiple logical sections responsible for configuration, indicator generation, attack simulation, payload creation, and communication with the SOAR platform.

```text
Python Alert Generator
│
└── multi_log_pusher.py
```

### The script is organized into the following sections:

### • Configuration

### • IOC Pools

### • Alert Generator

### • MITRE ATT&CK Mapping

### • JSON Payload Creation

### • Sending Alerts to Tines

### • Error Handling

### • Main Function

---

## Configuration

### The configuration section stores variables that control how the application communicates with external services. Keeping configuration values separate from the program logic improves readability, simplifies maintenance, and allows administrators to update settings without modifying the rest of the source code.

```python
# ==========================================
# ⚙️ CONFIGURATION
# ==========================================

TINES_WEBHOOK_URL = "https://your-webhook-url"
```

### In this project, the only configuration variable is the **Tines Webhook URL**. This URL acts as the entry point for the SOAR workflow. Whenever the Python script generates an alert, it sends the JSON payload to this webhook, automatically triggering the Tines automation pipeline.

### • Stores the destination Webhook URL.

### • Defines where generated alerts will be transmitted.

### • Connects the Python application with the Tines SOAR workflow.

### • Allows configuration changes without modifying the application logic.

---

## Importing Required Libraries

### Before generating alerts, the script imports several Python libraries. Each library provides specific functionality required for generating security events, formatting JSON data, creating timestamps, selecting randomized indicators, and sending HTTP requests to the SOAR platform.

 ```python
import requests
import json
import time
import random
from datetime import datetime, UTC
``` 

---

## requests Library

### The **requests** library is used to communicate with external web services through HTTP requests. In this project, it is responsible for sending the generated JSON alert to the Tines Webhook using an HTTP POST request.

### • Sends HTTP POST requests.

### • Transfers alert data to the SOAR platform.

### • Receives HTTP response codes.

### • Handles communication with external APIs.

---

## json Library

### The **json** library is used to convert Python dictionaries into JSON format. Since Tines and REST APIs exchange information using JSON, this library ensures the generated alerts follow a standardized structure.

### • Converts Python objects into JSON.

### • Formats payloads for readability.

### • Supports standardized API communication.

---

## time Library

### The **time** library is primarily used to generate unique alert identifiers. The current Unix timestamp is appended to each alert ID, ensuring that every generated alert has a unique value.

### • Generates Unix timestamps.

### • Creates unique alert identifiers.

### • Prevents duplicate alerts.

---

## random Library

### The **random** library is responsible for simulating realistic cybersecurity activity. Every execution randomly selects attack types, IOC values, severity levels, and alert statuses, allowing the workflow to process different security scenarios.

### • Randomly selects attack types.

### • Chooses random IP addresses.

### • Chooses random file hashes.

### • Chooses random URLs.

### • Simulates real-world SOC alerts.

---

## datetime Library

### The **datetime** module generates the exact date and time when an alert is created. The script uses **UTC (Coordinated Universal Time)** to ensure timestamps remain standardized across all systems, regardless of local time zones.

### Using UTC is considered a best practice in cybersecurity because it enables accurate event correlation between multiple security tools and geographically distributed environments.

### • Generates ISO 8601 timestamps.

### • Uses Coordinated Universal Time (UTC).

### • Provides accurate event timing.

### • Supports standardized log correlation.

---

## Why These Libraries Are Used

### Each imported library performs a dedicated function within the application. Together, they provide all the capabilities required to generate realistic cybersecurity alerts and communicate with the SOAR platform efficiently.

### • **requests** → Sends alerts to Tines.

## Alert Generator

### The Alert Generator is the core component of the Python application. Its responsibility is to create realistic cybersecurity alerts by combining attack information, Indicators of Compromise (IOCs), severity levels, timestamps, and MITRE ATT&CK mappings into a structured JSON payload. Each time the script executes, a new alert is generated with randomized values, closely simulating how enterprise SIEM platforms produce security events.

### Instead of generating static alerts, the script randomly selects attack types and corresponding IOCs. This allows the SOAR workflow to process different security scenarios during every execution, making the testing environment more realistic and comprehensive.

### • **Purpose:** Generate realistic cybersecurity alerts.

### • **Input:** IOC Pools and MITRE ATT&CK Mapping.

### • **Output:** JSON formatted security alert.

### • **Benefit:** Simulates real SOC security events for automated investigation.

---

## MITRE ATT&CK Mapping

```python
ATTACK_MAPPING = {
    "Brute-Force Attack": {
        "technique": "T1110",
        "tactic": "Credential Access"
    },
    "Phishing Email Detected": {
        "technique": "T1566",
        "tactic": "Initial Access"
    },
    "Malware Execution": {
        "technique": "T1204",
        "tactic": "Execution"
    },
    "Ransomware Activity": {
        "technique": "T1486",
        "tactic": "Impact"
    },
    "Command and Control": {
        "technique": "T1071",
        "tactic": "Command and Control"
    },
    "DNS Tunneling": {
        "technique": "T1071.004",
        "tactic": "Command and Control"
    },
    "Privilege Escalation": {
        "technique": "T1068",
        "tactic": "Privilege Escalation"
    },
    "Lateral Movement": {
        "technique": "T1021",
        "tactic": "Lateral Movement"
    },
    "Data Exfiltration": {
        "technique": "T1041",
        "tactic": "Exfiltration"
    },
    "PowerShell Execution": {
        "technique": "T1059.001",
        "tactic": "Execution"
    }
}
```

### The **ATTACK_MAPPING** dictionary maps each simulated attack to its corresponding **MITRE ATT&CK Technique ID** and **Tactic**. This provides standardized threat classification, making the generated alerts more realistic and easier to understand during investigation.

### Rather than using generic attack names, every event is associated with the globally recognized MITRE ATT&CK Framework. This enables analysts to understand the attacker's behavior, objectives, and techniques while ensuring compatibility with enterprise SOC processes.

### • **Purpose:** Standardize attack classification.

### • **Framework Used:** MITRE ATT&CK.

### • **Contains:** Attack Name, Technique ID, and Tactic.

### • **Benefit:** Improves threat analysis and investigation consistency.

---

## Selecting a Random Attack

```python
event_type = random.choice(list(ATTACK_MAPPING.keys()))
attack = ATTACK_MAPPING[event_type]
```

### The script begins by randomly selecting one attack type from the **ATTACK_MAPPING** dictionary. Since the attack names are stored as dictionary keys, the `random.choice()` function first converts them into a list before selecting one randomly.

### After selecting the attack, the corresponding MITRE Technique ID and Tactic are retrieved and stored for inclusion in the final alert payload.

### • Retrieves all available attack types.

### • Randomly selects one attack scenario.

### • Retrieves the corresponding MITRE information.

### • Creates different attack scenarios during every execution.

---

## Selecting Alert Status

```python
status = random.choice(["malicious", "benign"])

# For testing you can temporarily force:
# status = "malicious"
```

### After selecting an attack type, the script determines whether the generated alert should represent malicious activity or normal system behavior. This decision controls which IOC pool will be used and ultimately determines how the SOAR workflow responds.

### During development and testing, the status can be manually forced to **malicious**. This allows developers to repeatedly test the malicious investigation path without waiting for random selection.

### • Randomly selects Malicious or Benign.

### • Controls IOC selection.

### • Determines workflow execution path.

### • Supports manual testing by forcing malicious alerts.

---

## Severity Assignment

```python
severity = "Critical" if status == "malicious" else "Low"
```

### Once the alert status has been determined, the script automatically assigns a severity level. Malicious alerts are marked as **Critical**, while benign alerts receive a **Low** severity classification.

### Although this project uses only two severity levels, the same logic can easily be extended to include additional levels such as Informational, Medium, High, or Critical in enterprise environments.

### • Malicious → Critical.

### • Benign → Low.

### • Simplifies alert prioritization.

### • Enables automated incident handling.

---

## Alert ID Generation

```python
"alert_id": f"ALERT-{event_type[:4].upper()}-{int(time.time())}"
```

### Every generated alert requires a unique identifier so that it can be tracked throughout the investigation lifecycle. The alert ID combines three different components:

### • A fixed prefix (**ALERT**).

### • The first four characters of the selected attack name.

### • The current Unix timestamp.

### For example:

```text
ALERT-BRUT-1753952084
```

### Using the Unix timestamp guarantees uniqueness, even when multiple alerts are generated within a short period.

### • Generates unique alert identifiers.

### • Prevents duplicate alerts.

### • Supports incident tracking.

---

## Timestamp Generation

```python
"timestamp": datetime.now(UTC).isoformat()
```

### Every alert includes the exact date and time at which it was generated. The timestamp is recorded using **Coordinated Universal Time (UTC)** and formatted according to the **ISO 8601** international standard.

### Using UTC ensures that alerts generated from different geographic locations can be accurately correlated during forensic investigations.

### Example:

```text
2026-07-31T06:45:22.514873+00:00
```

### • Uses Coordinated Universal Time (UTC).

### • Follows ISO 8601 format.

### • Provides standardized timestamps.

### • Supports event correlation across multiple systems.

---

## Building the MITRE Section

```python
"mitre": {
    "technique": attack["technique"],
    "tactic": attack["tactic"]
}
```

### After selecting the attack type, the script inserts the corresponding MITRE ATT&CK Technique ID and Tactic into the alert payload. This enrichment allows downstream systems to understand the nature of the simulated attack without performing additional lookups.

### During the SOAR investigation, this information helps analysts quickly identify attacker objectives and categorize incidents according to the MITRE ATT&CK Framework.

### • Adds MITRE Technique ID.

### • Adds MITRE Tactic.

### • Standardizes threat classification.

### • Improves investigation quality.

---

## Building the Details Section

```python
"details": {
    "source_ip": random.choice(IP_POOL[status]),
    "file_hash": random.choice(HASH_POOL[status]),
    "destination_url": random.choice(URL_POOL[status]),
    "status": "Flagged Malicious" if status == "malicious" else "Approved Benign"
}
```

### The **details** section contains the primary Indicators of Compromise (IOCs) associated with the generated alert. These values are dynamically selected from the IOC Pools based on whether the alert is malicious or benign.

### All indicators within a single alert belong to the same category, ensuring consistency during enrichment and investigation. The workflow later sends these indicators to VirusTotal and URLScan.io for reputation analysis.

### The status field provides a human-readable description of the alert classification.

### • Randomly selects the source IP address.

### • Randomly selects the file hash.

### • Randomly selects the destination URL.

### • Assigns the alert status.

### • Creates a complete IOC package for investigation.

---

## Final Alert Payload

### After all fields have been generated, the script combines them into a single Python dictionary. This dictionary represents the complete security alert and serves as the payload transmitted to the Tines SOAR platform.

### The payload contains all information required for the automated investigation workflow, including the alert identifier, timestamp, attack information, severity, MITRE ATT&CK mapping, and Indicators of Compromise.

### • Alert ID.

### • Timestamp.

### • Event Type.

### • Severity.

### • MITRE ATT&CK Mapping.

### • Source IP Address.

### • File Hash.

### • Destination URL.

### • Alert Status.

### The completed payload is then forwarded to the **Sending Alerts** component, where it is transmitted to the Tines Webhook and the automated SOAR investigation begins.

### • **json** → Formats alert data.

### • **time** → Generates unique alert IDs.

### • **random** → Creates randomized attack scenarios.

### • **datetime** → Generates standardized UTC timestamps.

## IOC Pools

### Indicators of Compromise (IOCs) are digital artifacts that provide evidence of suspicious or malicious activity within a system or network. In this project, IOC Pools are used to simulate realistic cybersecurity alerts by storing predefined IP addresses, file hashes, and URLs. Instead of using fixed values, the script randomly selects indicators from these pools to generate diverse security events during each execution.

### The IOC pools are divided into two categories: **malicious** and **benign**. This allows the alert generator to simulate both genuine security threats and normal network activity, enabling the SOAR workflow to accurately classify alerts and validate its decision-making process.

### • **Purpose:** Store predefined Indicators of Compromise (IOCs).

### • **Categories:** Malicious and Benign indicators.

### • **Components:** IP addresses, File Hashes, and URLs.

### • **Selection Method:** Randomly chosen during alert generation.

### • **Benefit:** Simulates realistic SOC alerts without requiring live threat data.

---

## IP Pool

```python
IP_POOL = {
    "malicious": [
        "185.220.101.5",
        "45.142.195.34",
        "193.56.28.14",
        "91.240.118.174"
    ],
    "benign": [
        "8.8.8.8",
        "1.1.1.1",
        "142.250.190.46",
        "13.107.4.50",
        "8.8.4.4",
        "1.0.0.1",
        "9.9.9.9",
        "149.112.112.112",
        "208.67.222.222",
        "208.67.220.220",
        "20.190.160.1",
        "172.217.160.110",
        "140.82.114.3"
    ]
}
```

### The IP Pool contains a collection of source IP addresses used to simulate network traffic. The script randomly selects an IP address based on whether the generated alert is classified as **malicious** or **benign**. These IP addresses are later submitted to VirusTotal for reputation analysis during the SOAR investigation.

### The malicious IP addresses represent known suspicious infrastructure, while the benign IP addresses belong to trusted services such as Google DNS, Cloudflare DNS, Quad9, OpenDNS, Microsoft, and GitHub. This allows the workflow to produce realistic enrichment results and test both positive and negative detection scenarios.

### • **Purpose:** Simulate network source IP addresses.

### • **Malicious Pool:** Represents suspicious attacker infrastructure.

### • **Benign Pool:** Contains trusted public service IP addresses.

### • **Used By:** VirusTotal IP Address Report.

### • **Benefit:** Enables realistic IP reputation analysis during IOC enrichment.

---

## Hash Pool

```python
HASH_POOL = {
    "malicious": [
        "275a021bbfb6489e54d471899f7db9d1663fc695ec2fe2a2c4538aabf651fd0f",
        "3a92d35eec0d5dae290886b6256157f9202773b06de5b8e4e9cf0a1c6a66b96e"
    ],
    "benign": [
        "7ee7c1ed1e696d25813d5afb6f98d8b15282dd588bd2812339919fab429fd129",
        "a591a6d40bf420404a011733cfb7b190d62c65bfbc5cd3a5f2546a4c033017c3",
        "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
        "ba7816bf8f01cfea414140de5dae2223b00361a396177a9cb410ff61f20015ad",
        "2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824"
    ]
}
```

### The Hash Pool stores SHA-256 file hashes representing files that may be either malicious or benign. During alert generation, the script randomly selects a file hash based on the alert status and includes it in the JSON payload. The selected hash is later submitted to VirusTotal to determine its reputation and malware detection statistics.

### Using predefined hashes allows the workflow to consistently demonstrate file reputation analysis without requiring actual malware samples. This provides a safe and repeatable testing environment for the SOAR automation pipeline.

### • **Purpose:** Simulate suspicious and legitimate files.

### • **Hash Type:** SHA-256.

### • **Used By:** VirusTotal File Report.

### • **Function:** Determines whether a file is malicious or safe.

### • **Benefit:** Enables secure malware reputation testing without handling real malware.

---

## URL Pool

```python
URL_POOL = {
    "malicious": [
        "https://testsafebrowsing.appspot.com/s/malware.html",
        "http://91.240.118.174",
        "https://example.com"
    ],
    "benign": [
        "https://google.com",
        "https://github.com",
        "https://amazon.com"
    ]
}
```

### The URL Pool contains a collection of web addresses used to simulate user browsing activity. Similar to the IP and Hash pools, URLs are separated into malicious and benign categories. During alert generation, the script randomly selects a URL that matches the alert status and includes it in the payload.

### The selected URL is submitted to URLScan.io, where it is analyzed for reputation, website behavior, and malicious activity. This allows the workflow to automatically determine whether a website should be considered safe or suspicious.

### • **Purpose:** Simulate web traffic and destination URLs.

### • **Malicious URLs:** Used to test threat detection and URL reputation analysis.

### • **Benign URLs:** Represent trusted and commonly accessed websites.

### • **Used By:** URLScan.io Integration.

### • **Benefit:** Enables automated website reputation analysis within the SOAR workflow.

---

## How Random IOC Selection Works

### Instead of using fixed indicators, the script dynamically selects values from each IOC pool using Python's `random.choice()` function. The selected values depend on whether the alert is classified as **malicious** or **benign**, ensuring that all indicators within a single alert belong to the same category.

```python
random.choice(IP_POOL[status])
random.choice(HASH_POOL[status])
random.choice(URL_POOL[status])
```

### If the alert status is **malicious**, the script selects indicators from the malicious pools. Likewise, if the alert status is **benign**, indicators are selected from the benign pools. This approach generates realistic and consistent security events while allowing the SOAR workflow to test both malicious and non-malicious investigation paths.

### • **Selection Function:** `random.choice()`.

### • **Selection Basis:** Alert status (Malicious or Benign).

### • **Ensures:** Consistent IOC selection within each alert.

### • **Creates:** Dynamic and realistic security events.

### • **Improves:** Testing accuracy for the complete SOAR automation workflow.

## Alert Generator

### The Alert Generator is the core component of the Python application. Its responsibility is to create realistic cybersecurity alerts by combining attack information, Indicators of Compromise (IOCs), severity levels, timestamps, and MITRE ATT&CK mappings into a structured JSON payload. Each time the script executes, a new alert is generated with randomized values, closely simulating how enterprise SIEM platforms produce security events.

### Instead of generating static alerts, the script randomly selects attack types and corresponding IOCs. This allows the SOAR workflow to process different security scenarios during every execution, making the testing environment more realistic and comprehensive.

### • **Purpose:** Generate realistic cybersecurity alerts.

### • **Input:** IOC Pools and MITRE ATT&CK Mapping.

### • **Output:** JSON formatted security alert.

### • **Benefit:** Simulates real SOC security events for automated investigation.

---

## MITRE ATT&CK Mapping

```python
ATTACK_MAPPING = {
    "Brute-Force Attack": {
        "technique": "T1110",
        "tactic": "Credential Access"
    },
    "Phishing Email Detected": {
        "technique": "T1566",
        "tactic": "Initial Access"
    },
    "Malware Execution": {
        "technique": "T1204",
        "tactic": "Execution"
    },
    "Ransomware Activity": {
        "technique": "T1486",
        "tactic": "Impact"
    },
    "Command and Control": {
        "technique": "T1071",
        "tactic": "Command and Control"
    },
    "DNS Tunneling": {
        "technique": "T1071.004",
        "tactic": "Command and Control"
    },
    "Privilege Escalation": {
        "technique": "T1068",
        "tactic": "Privilege Escalation"
    },
    "Lateral Movement": {
        "technique": "T1021",
        "tactic": "Lateral Movement"
    },
    "Data Exfiltration": {
        "technique": "T1041",
        "tactic": "Exfiltration"
    },
    "PowerShell Execution": {
        "technique": "T1059.001",
        "tactic": "Execution"
    }
}
```

### The **ATTACK_MAPPING** dictionary maps each simulated attack to its corresponding **MITRE ATT&CK Technique ID** and **Tactic**. This provides standardized threat classification, making the generated alerts more realistic and easier to understand during investigation.

### Rather than using generic attack names, every event is associated with the globally recognized MITRE ATT&CK Framework. This enables analysts to understand the attacker's behavior, objectives, and techniques while ensuring compatibility with enterprise SOC processes.

### • **Purpose:** Standardize attack classification.

### • **Framework Used:** MITRE ATT&CK.

### • **Contains:** Attack Name, Technique ID, and Tactic.

### • **Benefit:** Improves threat analysis and investigation consistency.

---

## Selecting a Random Attack

```python
event_type = random.choice(list(ATTACK_MAPPING.keys()))
attack = ATTACK_MAPPING[event_type]
```

### The script begins by randomly selecting one attack type from the **ATTACK_MAPPING** dictionary. Since the attack names are stored as dictionary keys, the `random.choice()` function first converts them into a list before selecting one randomly.

### After selecting the attack, the corresponding MITRE Technique ID and Tactic are retrieved and stored for inclusion in the final alert payload.

### • Retrieves all available attack types.

### • Randomly selects one attack scenario.

### • Retrieves the corresponding MITRE information.

### • Creates different attack scenarios during every execution.

---

## Selecting Alert Status

```python
status = random.choice(["malicious", "benign"])

# For testing you can temporarily force:
# status = "malicious"
```

### After selecting an attack type, the script determines whether the generated alert should represent malicious activity or normal system behavior. This decision controls which IOC pool will be used and ultimately determines how the SOAR workflow responds.

### During development and testing, the status can be manually forced to **malicious**. This allows developers to repeatedly test the malicious investigation path without waiting for random selection.

### • Randomly selects Malicious or Benign.

### • Controls IOC selection.

### • Determines workflow execution path.

### • Supports manual testing by forcing malicious alerts.

---

## Severity Assignment

```python
severity = "Critical" if status == "malicious" else "Low"
```

### Once the alert status has been determined, the script automatically assigns a severity level. Malicious alerts are marked as **Critical**, while benign alerts receive a **Low** severity classification.

### Although this project uses only two severity levels, the same logic can easily be extended to include additional levels such as Informational, Medium, High, or Critical in enterprise environments.

### • Malicious → Critical.

### • Benign → Low.

### • Simplifies alert prioritization.

### • Enables automated incident handling.

---

## Alert ID Generation

```python
"alert_id": f"ALERT-{event_type[:4].upper()}-{int(time.time())}"
```

### Every generated alert requires a unique identifier so that it can be tracked throughout the investigation lifecycle. The alert ID combines three different components:

### • A fixed prefix (**ALERT**).

### • The first four characters of the selected attack name.

### • The current Unix timestamp.

### For example:

```text
ALERT-BRUT-1753952084
```

### Using the Unix timestamp guarantees uniqueness, even when multiple alerts are generated within a short period.

### • Generates unique alert identifiers.

### • Prevents duplicate alerts.

### • Supports incident tracking.

---

## Timestamp Generation

```python
"timestamp": datetime.now(UTC).isoformat()
```

### Every alert includes the exact date and time at which it was generated. The timestamp is recorded using **Coordinated Universal Time (UTC)** and formatted according to the **ISO 8601** international standard.

### Using UTC ensures that alerts generated from different geographic locations can be accurately correlated during forensic investigations.

### Example:

```text
2026-07-31T06:45:22.514873+00:00
```

### • Uses Coordinated Universal Time (UTC).

### • Follows ISO 8601 format.

### • Provides standardized timestamps.

### • Supports event correlation across multiple systems.

---

## Building the MITRE Section

```python
"mitre": {
    "technique": attack["technique"],
    "tactic": attack["tactic"]
}
```

### After selecting the attack type, the script inserts the corresponding MITRE ATT&CK Technique ID and Tactic into the alert payload. This enrichment allows downstream systems to understand the nature of the simulated attack without performing additional lookups.

### During the SOAR investigation, this information helps analysts quickly identify attacker objectives and categorize incidents according to the MITRE ATT&CK Framework.

### • Adds MITRE Technique ID.

### • Adds MITRE Tactic.

### • Standardizes threat classification.

### • Improves investigation quality.

---

## Building the Details Section

```python
"details": {
    "source_ip": random.choice(IP_POOL[status]),
    "file_hash": random.choice(HASH_POOL[status]),
    "destination_url": random.choice(URL_POOL[status]),
    "status": "Flagged Malicious" if status == "malicious" else "Approved Benign"
}
```

### The **details** section contains the primary Indicators of Compromise (IOCs) associated with the generated alert. These values are dynamically selected from the IOC Pools based on whether the alert is malicious or benign.

### All indicators within a single alert belong to the same category, ensuring consistency during enrichment and investigation. The workflow later sends these indicators to VirusTotal and URLScan.io for reputation analysis.

### The status field provides a human-readable description of the alert classification.

### • Randomly selects the source IP address.

### • Randomly selects the file hash.

### • Randomly selects the destination URL.

### • Assigns the alert status.

### • Creates a complete IOC package for investigation.

---

## Final Alert Payload

### After all fields have been generated, the script combines them into a single Python dictionary. This dictionary represents the complete security alert and serves as the payload transmitted to the Tines SOAR platform.

### The payload contains all information required for the automated investigation workflow, including the alert identifier, timestamp, attack information, severity, MITRE ATT&CK mapping, and Indicators of Compromise.

### • Alert ID.

### • Timestamp.

### • Event Type.

### • Severity.

### • MITRE ATT&CK Mapping.

### • Source IP Address.

### • File Hash.

### • Destination URL.

### • Alert Status.

### The completed payload is then forwarded to the **Sending Alerts** component, where it is transmitted to the Tines Webhook and the automated SOAR investigation begins.

## Sending Alerts

### Once the alert payload has been successfully generated, the final step is to transmit it to the Tines SOAR platform. This is handled by the `send_to_soar_pipeline()` function, which sends the JSON payload to the configured Tines Webhook using an HTTP POST request. The function also validates the response received from Tines and displays useful debugging information, making it easier to monitor and troubleshoot the communication process.

### This function acts as the bridge between the Python Alert Generator and the SOAR platform. Every alert generated by the script passes through this function before entering the automated investigation workflow.

### • Generates the alert payload.

### • Sends the payload to the Tines Webhook.

### • Displays the generated payload.

### • Validates the server response.

### • Handles communication errors gracefully.

---

## send_to_soar_pipeline() Function

```python
def send_to_soar_pipeline():
```

### This function contains the complete logic responsible for transmitting alerts to the SOAR platform. It first generates a new alert, prints the payload for verification, sends it to Tines, processes the response, and handles any communication errors that may occur.

### Every time this function is executed, a completely new security alert is created and transmitted to the configured Webhook.

### • Main communication function.

### • Controls the alert transmission process.

### • Initiates communication with Tines.

---

## Generating the Alert Payload

```python
alert_payload = generate_log()
```

### The first step inside the function is calling the `generate_log()` function. This function returns a fully populated Python dictionary containing all alert information, including the alert ID, timestamp, attack type, severity, MITRE ATT&CK mapping, and Indicators of Compromise (IOCs).

### This dictionary becomes the payload that will later be transmitted to the SOAR platform.

### • Calls the Alert Generator.

### • Creates a complete security alert.

### • Stores the generated alert in `alert_payload`.

---

## Displaying the Generated Payload

```python
print("=" * 60)
print("[*] Generated Payload:")
print(json.dumps(alert_payload, indent=4))
print("=" * 60)
```

### Before sending the alert, the script prints the generated payload to the console. This provides visibility into the exact data being transmitted and helps verify that all fields have been generated correctly.

### The `json.dumps()` function converts the Python dictionary into a neatly formatted JSON object using indentation, making it easier to read during testing and debugging.

### Example Output

```json
{
    "alert_id": "ALERT-BRUT-1753952084",
    "timestamp": "2026-07-31T10:15:25.114Z",
    "event_type": "Brute-Force Attack",
    "severity": "Critical",
    "mitre": {
        "technique": "T1110",
        "tactic": "Credential Access"
    },
    "details": {
        "source_ip": "45.142.195.34",
        "file_hash": "...",
        "destination_url": "http://91.240.118.174",
        "status": "Flagged Malicious"
    }
}
```

### • Displays the generated alert.

### • Converts the payload into readable JSON.

### • Simplifies testing and debugging.

---

## HTTP POST Request

```python
response = requests.post(
    TINES_WEBHOOK_URL,
    json=alert_payload,
    timeout=15
)
```

### The generated alert is transmitted to the Tines SOAR platform using an HTTP POST request. The `requests.post()` method sends the JSON payload directly to the configured Webhook URL, where it is received by the Tines Webhook action and immediately triggers the automation workflow.

### The payload is automatically serialized into JSON and included in the request body. Once the request reaches Tines, the workflow begins processing the alert through the remaining actions such as VirusTotal, URLScan.io, Event Transforms, Conditions, and Jira.

### • Sends an HTTP POST request.

### • Transfers the JSON payload.

### • Triggers the Tines SOAR workflow.

### • Waits for the server response.

---

## Understanding the Request Parameters

### The HTTP POST request contains three important parameters that define how the communication is performed.

### **TINES_WEBHOOK_URL**

### Specifies the destination URL where the alert will be transmitted. This URL is generated automatically by Tines when a Webhook Action is created.

### **json=alert_payload**

### Sends the generated Python dictionary as a JSON request body. The Requests library automatically converts the dictionary into JSON format and sets the appropriate `Content-Type: application/json` header.

### **timeout=15**

### Specifies that the request should wait a maximum of **15 seconds** for a server response. If no response is received within this period, the request is cancelled automatically.

### • Webhook URL → Destination.

### • JSON Payload → Alert Data.

### • Timeout → Prevents indefinite waiting.

---

## Why Timeout Is Used

### Network communication is not always reliable. Servers may become unavailable, internet connectivity may be interrupted, or API services may respond slowly. Without a timeout, the Python script could wait indefinitely for a response, causing the application to hang.

### Setting a timeout improves reliability by ensuring that failed requests terminate after a reasonable period and allowing the program to handle the failure gracefully.

### • Prevents application freezing.

### • Detects network failures.

### • Improves reliability.

### • Enables graceful error handling.

---

## Receiving the HTTP Response

```python
print(f"[+] HTTP Status: {response.status_code}")
```

### After transmitting the alert, the server responds with an HTTP status code indicating whether the request was processed successfully. The script displays this status code, allowing the user to quickly verify whether the alert reached the SOAR platform.

### Common HTTP Status Codes

| **Status Code** | **Meaning** |
|-----------------|-------------|
| **200** | Request processed successfully. |
| **201** | Resource created successfully. |
| **400** | Bad request or invalid payload. |
| **401** | Authentication failed. |
| **404** | Resource not found. |
| **422** | Request format is correct, but cannot be processed. |
| **500** | Internal server error. |

### • Displays the server response.

### • Helps identify communication issues.

### • Simplifies troubleshooting.

---

## Reading the Response JSON

```python
print("[+] Response JSON:")
print(json.dumps(response.json(), indent=4))
```

### If the server returns a JSON response, the script converts it into a formatted JSON object and displays it on the console. This allows developers to inspect the response data returned by Tines and verify whether the workflow accepted the alert successfully.

### JSON responses commonly include status messages, identifiers, or additional processing information.

### • Reads the server response.

### • Displays formatted JSON.

### • Confirms successful processing.

---

## Reading the Response Text

```python
print("[+] Response Text:")
print(response.text)
```

### Some servers return plain text instead of JSON. If JSON parsing fails, the script automatically falls back to displaying the raw response text. This ensures that useful debugging information is still available regardless of the response format.

### • Handles non-JSON responses.

### • Displays raw server output.

### • Improves debugging.

---

## Exception Handling

```python
except requests.exceptions.RequestException as e:
    print(f"[-] Request Failed: {e}")
```

### Communication with external services can fail for various reasons, including internet connectivity issues, invalid Webhook URLs, DNS failures, server outages, or request timeouts. To prevent the application from crashing, the HTTP request is wrapped inside a `try-except` block.

### If any communication error occurs, the exception is caught and displayed as a user-friendly error message instead of terminating the application unexpectedly.

### • Prevents unexpected program crashes.

### • Handles communication failures.

### • Displays meaningful error messages.

### • Improves application reliability.

---

## Overall Workflow

### The `send_to_soar_pipeline()` function completes the final stage of the Python Alert Generator. It receives the generated alert, validates it, transmits it to the Tines Webhook, receives the server response, and handles any communication errors. Once the alert reaches the Webhook, the automated SOAR workflow begins processing the security event.

### Workflow Sequence

```text
Generate Alert
      │
      ▼
Display JSON Payload
      │
      ▼
HTTP POST Request
      │
      ▼
Tines Webhook
      │
      ▼
Receive HTTP Response
      │
      ▼
Display Response / Handle Errors
```

### • Generates the alert.

### • Displays the payload.

### • Sends the alert to Tines.

### • Receives the server response.

### • Handles errors gracefully.

### • Successfully initiates the automated SOAR investigation workflow.

# Complete Python Script

## Overview

### The complete Python script combines all the components discussed in the previous sections into a single application. It generates realistic cybersecurity alerts, enriches them with MITRE ATT&CK information, selects Indicators of Compromise (IOCs), constructs a structured JSON payload, and transmits the alert to the Tines SOAR platform through a Webhook. Once the alert reaches Tines, the automated investigation workflow begins, integrating VirusTotal, URLScan.io, Event Transforms, Run Scripts, Conditions, and Jira to complete the incident response process.

### • Generates realistic cybersecurity alerts.

### • Simulates both malicious and benign security events.

### • Selects randomized Indicators of Compromise (IOCs).

### • Maps attacks to the MITRE ATT&CK Framework.

### • Creates structured JSON payloads.

### • Sends alerts to the Tines SOAR platform.

### • Initiates the complete automated SOAR investigation pipeline.

---

## Complete Python Script

> **Insert the complete `multi_log_pusher.py` source code here.**

---

## End-to-End Workflow

### The following sequence illustrates how the Python Alert Generator interacts with the remaining components of the SOAR platform.

```text
Python Alert Generator
        │
        ▼
Generate Security Alert
        │
        ▼
Select MITRE ATT&CK Mapping
        │
        ▼
Select IOC Values
(IP, Hash, URL)
        │
        ▼
Create JSON Payload
        │
        ▼
HTTP POST Request
        │
        ▼
Tines Webhook
        │
        ▼
VirusTotal
(IP & File Hash Analysis)
        │
        ▼
URLScan.io
(URL Reputation Analysis)
        │
        ▼
Run Script
(Threat Score Calculation)
        │
        ▼
Event Transform
(Standardize Data)
        │
        ▼
Condition
(Malicious / Benign Decision)
        │
        ├───────────────┐
        ▼               ▼
Malicious         Benign
        │               │
        ▼               ▼
Create Jira      Close Alert
Incident         Add Comment
        │
        ▼
Workflow Complete
```

---

## Complete Workflow Explanation

### The workflow begins when the Python Alert Generator creates a randomized cybersecurity alert containing an attack type, severity level, timestamp, MITRE ATT&CK mapping, and Indicators of Compromise (IOCs). The generated payload is transmitted to the Tines Webhook using an HTTP POST request.

### After receiving the alert, Tines triggers the automation workflow and performs threat intelligence enrichment by querying VirusTotal for IP address and file hash reputation, while URLScan.io analyzes the destination URL.

### The collected intelligence is processed using Run Script actions to calculate threat scores and Event Transform actions to normalize the response data into a consistent format. Condition actions then evaluate the enrichment results and determine whether the alert should be classified as malicious or benign.

### If the alert is identified as malicious, Jira automatically creates an incident ticket containing the investigation details. If the alert is benign, the workflow closes the alert and records the investigation outcome without creating an incident.

### This fully automated pipeline eliminates repetitive manual investigation tasks while ensuring every alert is analyzed consistently using multiple threat intelligence sources.

---

## Advantages

### • Lightweight implementation without requiring an enterprise SIEM.

### • Generates realistic security alerts.

### • Automates IOC enrichment.

### • Integrates multiple threat intelligence platforms.

### • Automatically maps attacks to MITRE ATT&CK.

### • Creates Jira incidents automatically.

### • Standardizes the investigation process.

### • Reduces analyst workload and response time.

---

## Future Enhancements

### • Integrate additional threat intelligence platforms.

### • Support real-time SIEM log ingestion.

### • Implement machine learning-based threat scoring.

### • Add email and Microsoft Teams notifications.

### • Integrate Slack for analyst collaboration.

### • Generate automated investigation reports.

### • Deploy using Docker containers.

### • Extend support for additional SOAR platforms.

# Tines SOAR Workflow

## Story Overview

### The Tines SOAR workflow is the core automation component of this project. It is responsible for receiving security alerts generated by the Python Alert Generator, orchestrating the investigation process, enriching Indicators of Compromise (IOCs), calculating threat scores, applying decision logic, and automating incident response. Rather than requiring a SOC analyst to manually investigate every alert, the workflow performs these repetitive tasks automatically, significantly reducing investigation time and improving consistency.

### The workflow begins when the Python application sends a security alert to the Tines Webhook. This alert contains important information such as the alert ID, timestamp, event type, severity level, MITRE ATT&CK mapping, source IP address, file hash, destination URL, and alert status. The Webhook serves as the entry point of the automation pipeline and immediately triggers the remaining workflow actions.

### Once the alert is received, the workflow extracts the relevant Indicators of Compromise (IOCs) and sends them to multiple external threat intelligence platforms. The source IP address and file hash are submitted to VirusTotal for reputation analysis, while the destination URL is submitted to URLScan.io to determine whether the website is malicious or safe. These integrations provide real-time threat intelligence that forms the foundation of the automated investigation.

### After receiving responses from the external services, the workflow processes the returned data using Event Transform and Run Script actions. These actions normalize API responses, extract important attributes, calculate threat scores, and prepare the data for decision making. By converting different API responses into a standardized format, the workflow ensures that all subsequent actions operate on consistent data regardless of the source.

### The workflow then evaluates the enriched data using Condition actions. The decision logic checks the reputation results from VirusTotal and URLScan.io together with the calculated threat score to determine whether the alert represents malicious or benign activity. This automated decision-making process replaces the repetitive manual analysis typically performed by SOC analysts.

### If the investigation identifies malicious activity, the workflow automatically creates an incident in Jira, records investigation comments, maps the attack to the MITRE ATT&CK Framework, and stores the investigation results for future reference. If the alert is determined to be benign, the workflow closes the investigation without creating an incident while still documenting the analysis performed during the automation process.

### By combining multiple security tools into a single automated workflow, the Tines Story demonstrates how enterprise Security Operations Centers use SOAR platforms to reduce manual effort, improve investigation consistency, accelerate incident response, and allow analysts to focus on high-priority security incidents instead of repetitive investigative tasks.

### • Receives alerts through a Webhook.

### • Initiates the automated SOAR investigation.

### • Integrates with VirusTotal for IP and file hash reputation analysis.

### • Integrates with URLScan.io for URL reputation analysis.

### • Processes API responses using Event Transform actions.

### • Calculates threat scores using Run Script actions.

### • Applies automated decision logic using Condition actions.

### • Maps attacks to the MITRE ATT&CK Framework.

### • Automatically creates Jira incidents for malicious alerts.

### • Closes benign alerts after successful validation.

### • Eliminates repetitive manual investigation tasks.

### • Demonstrates a complete end-to-end enterprise SOC automation workflow.

---

## Complete Story Architecture

### The figure below illustrates the complete Tines SOAR workflow implemented in this project. It shows how alerts generated by the Python Alert Generator flow through the Webhook, threat intelligence integrations, data transformation, threat scoring, decision-making process, and finally the automated incident response actions. This architecture represents the complete automation pipeline developed for the project.

**Complete Tines SOAR Story Architecture**
<img width="1541" height="920" alt="image" src="https://github.com/user-attachments/assets/11f14b4d-20de-43a9-a108-f8b807a3ce1c" />

## Tines Objects
## Webhook

### Purpose

### The Webhook is the entry point of the Tines SOAR workflow. It receives security alerts from the Python Alert Generator through an HTTP POST request and automatically triggers the investigation workflow.

### • Receives alerts from Python.

### • Starts the SOAR workflow.

### • Passes alert data to downstream actions.

---

## Configuration

### **Name**

```text
Webhook
```

### Identifies the action as the starting point of the Tines workflow.

---

### **Description**

```text
Receives security alerts from the Python Alert Generator and initiates the automated SOAR investigation workflow.
```

### Describes the purpose of the Webhook and its role in initiating the automation.

---

### **Webhook URL**

```text
https://hidden-heather-3488.tines.com/webhook/your-first-story/
```

### The unique endpoint used by the Python Alert Generator to send alert data to Tines.

---

### **Path**

```text
your-first-story
```

### Defines the Webhook endpoint within the Tines Story.

---

### **Allowed Verbs**

```text
GET, POST
```

### Allows GET requests for testing and POST requests to receive alert payloads.

---

### **Access Control**

```text
Anyone with the path
```

### Allows any application with the Webhook URL to send requests. Suitable for development and testing environments.

---

### **Webhook Configuration**
<img width="748" height="965" alt="image" src="https://github.com/user-attachments/assets/c184f775-a960-4346-a615-bb7530c431f8" />

## URLScan Submit

### Purpose

### The **URLScan Submit** action sends the destination URL received from the Python Alert Generator to the URLScan.io API for analysis. URLScan.io scans the website and returns a unique scan UUID, which is later used to retrieve the complete scan results.

### • Submits URLs for analysis.

### • Initiates a new URLScan.io scan.

### • Returns a unique Scan UUID.

### • Starts URL reputation analysis.

### Add API Key from the url scan
### Create a account in the urlscan.io and navigate to the profile then security and api key section, copy paste in the configuration settings
<img width="1471" height="940" alt="image" src="https://github.com/user-attachments/assets/5de9c6f9-428d-44e6-bbe3-6cd0b21b877b" />


---

## Configuration

### **Name**

```text
URLScan.io
```

### Identifies the integration used for URL reputation analysis.

---

### **Action**

```text
Submit a URL to be scanned
```

### Specifies that this action submits a URL to URLScan.io for scanning.

---

### **Description**

```text
The submission API allows you to submit a URL to be scanned and returns a unique Scan UUID used to retrieve the scan results.
```

### Explains the purpose of the action and the information returned after submission.

---

### **Documentation**

```text
https://urlscan.io/docs/api/
```

### Official URLScan.io API documentation used for configuring the integration.

---

### **Input URL**

```text
webhook.body.details.destination_url
```

### Retrieves the destination URL from the incoming Webhook payload and sends it to URLScan.io for analysis.

---

### **Visibility**

```text
public
```

### Sets the submitted scan visibility to **Public**, allowing URLScan.io to process and store the scan publicly.

---

## API Request Configuration

### **URL**

```text
https://urlscan.io/api/v1/scan/
```

### The API endpoint used to submit URLs for scanning.

---

### **Content Type**

```text
JSON
```

### Sends the request body in JSON format.

---

### **Method**

```text
POST
```

### Uses the HTTP POST method to submit the URL for analysis.

---

### **Headers**

```text
API-KEY : CREDENTIAL.urlscan_io
```

### Authenticates the request using the stored URLScan.io API credential.

---

### **Payload**

```text
=LOCAL.final_payload
```

### Sends the generated JSON payload containing the destination URL and scan options to the URLScan.io API.

---

### **Local Values**

### The Local Values section dynamically builds the final JSON payload before sending the request. It extracts the destination URL, applies optional scan parameters, removes empty values, and generates a clean payload that is transmitted to URLScan.io.

### • Builds the JSON request.

### • Inserts the destination URL.

### • Removes empty parameters.

### • Generates the final payload automatically.

---
### **URLScan Submit Configuration**
<img width="732" height="877" alt="image" src="https://github.com/user-attachments/assets/33e513d4-3b6f-44c8-92bd-bc10211f1c9a" />

### Inside page 
<img width="728" height="745" alt="image" src="https://github.com/user-attachments/assets/4043b27b-528e-4a84-8393-103ac1efc772" />

<img width="735" height="822" alt="image" src="https://github.com/user-attachments/assets/017222df-7877-4494-9627-32dc49cf5e10" />

## Event Transform (Delay)

### Purpose

### The **Event Transform (Delay)** action pauses the workflow for **10 seconds** before continuing. Since URLScan.io requires a short amount of time to complete scanning and generate results, this delay ensures that the scan has finished before the workflow attempts to retrieve the analysis.

### • Waits for URLScan.io to complete the scan.

### • Prevents retrieving incomplete scan results.

### • Ensures accurate URL reputation analysis.

---

## Configuration

### **Name**

```text
Event Transform
```

### Identifies the action responsible for delaying the workflow.

---

### **Description**

```text
Delays the workflow to allow URLScan.io to complete the scan before retrieving the results.
```

### Explains that the action introduces a delay so the next step retrieves completed scan results.

---

### **Mode**

```text
Delay
```

### Configures the Event Transform action to pause the workflow for a specified duration.

---

### **Delay**

```text
10 Seconds
```

### Pauses the workflow for **10 seconds**, giving URLScan.io enough time to finish scanning before the next API request retrieves the scan results.

---

**Event Transform (Delay) Configuration**
<img width="736" height="884" alt="image" src="https://github.com/user-attachments/assets/c63a4e12-9a34-4ae0-8e1f-d91e7927d4a1" />

## Retrieve Results

### Purpose

### The **Retrieve Results** action retrieves the completed scan results from URLScan.io using the **Scan UUID** returned by the previous **Submit URL** action. Since URLScan.io needs time to analyze the submitted URL, this action is executed after the **10-second Event Transform delay** to ensure the scan has completed successfully.

### • Retrieves completed URLScan.io results.

### • Uses the Scan UUID from the previous action.

### • Obtains URL reputation and scan details.

### • Continues the automated investigation workflow.

### Add the same API key from here and connect the template 
<img width="1471" height="940" alt="image" src="https://github.com/user-attachments/assets/d907feb9-a1f3-436d-9686-29a316661d8f" />


---

## Configuration

### **Name**

```text
URLScan.io
```

### Identifies the integration used to retrieve the completed scan results.

---

### **Action**

```text
Retrieve result of scan
```

### Retrieves the analysis results of the previously submitted URL.

---

### **Description**

```text
Retrieves the completed scan results from URLScan.io using the Scan UUID returned by the Submit URL action.
```

### Explains that this action polls URLScan.io using the Scan UUID to obtain the final scan results after the scan is complete.

---

### **Documentation**

```text
https://urlscan.io/docs/api/
```

### Official URLScan.io API documentation used for configuring the Result API.

---

### **Scan UUID**

```text
submit_a_url_to_be_scanned.body.uuid
```

### Retrieves the unique Scan UUID generated by the **Submit URL** action. This UUID uniquely identifies the submitted scan and is required to fetch its results.

---

### **API URL**

```text
https://urlscan.io/api/v1/result/{Scan UUID}/
```

### The Result API endpoint uses the Scan UUID to retrieve the completed scan report from URLScan.io.

---

### **Method**

```text
GET
```

### Uses the HTTP GET method to retrieve the completed scan results.

---

### **Headers**

```text
API-Key : INPUT.urlscan_credential
```

### Authenticates the request using the configured URLScan.io API credential.

---

### **Log Error on Status**

```text
400–403
405–409
411–500
```

### These HTTP status codes are logged as errors if the API request fails, allowing easier troubleshooting and workflow monitoring.

### Common Response Codes

| **Status Code** | **Description** |
|-----------------|-----------------|
| **200** | Scan completed successfully and results are returned. |
| **404** | Scan is still in progress or the Scan UUID was not found. |
| **410** | Scan results have been deleted. |

---

### **URLScan Retrieve Results Configuration**
<img width="709" height="794" alt="image" src="https://github.com/user-attachments/assets/4d48deb5-eecd-4fdf-b0b8-e35e4574991e" />

<img width="715" height="741" alt="image" src="https://github.com/user-attachments/assets/e52c4145-94ae-409d-86a4-9fd2a55ff218" />

## Run Script (URL Score)

### Purpose

### The **Run Script** action extracts the overall **URL Score** from the URLScan.io scan results. Instead of passing the complete API response to subsequent actions, this script retrieves only the required score value, making it easier to use in later workflow steps such as threat score calculation and decision-making.

### • Extracts the URLScan overall score.

### • Simplifies the API response.

### • Passes only the required value to downstream actions.

### • Supports automated threat assessment.

---

## Configuration

### **Name**

```text
Run Script
```

### Identifies the action responsible for processing the URLScan.io response.

---

### **Description**

```text
Extracts the URLScan overall score from the scan results for use in threat score calculation and workflow decision-making.
```

### Explains that the script retrieves the overall URL score from the URLScan.io response.

---

### **Runtime Environment**

```text
Python 3.13
```

### Executes the script using the Python 3.13 runtime environment provided by Tines.

---

### **Script**

```python
def main(input):
    return {
        "url_score": input["url_score"]
    }
```

### This script receives the URL score as input and returns it as a simplified output object. The extracted value can then be referenced by other workflow actions without navigating the complete URLScan API response.

### • Receives the input value.

### • Extracts the URL score.

### • Returns a simplified output.

### • Makes downstream processing easier.

---

### **Emit Failure Event**

```text
Always
```

### Configured to always emit a failure event if the script encounters an error, allowing the workflow to log and troubleshoot execution issues.

---

### **Input**

```json
{
  "url_score": "<<retrieve_result_of_scan.body.verdicts.overall.score>>"
}
```

### Retrieves the **overall URL score** from the **Retrieve Result of Scan** action and passes it as the input to the Python script.

---

### **Timeout**

```text
10 Seconds
```

### Allows the script a maximum of **10 seconds** to complete execution before timing out.

---

### **Requirements**

```text
requests==2.34.2
```

### Specifies the required Python package available during script execution. Although this script does not directly use the library, it is included as part of the runtime environment configuration.

---

## **Run Script (URL Score) Configuration**
<img width="717" height="820" alt="image" src="https://github.com/user-attachments/assets/00d77ea8-6244-4f1c-bf36-b94efefb7e5d" />

<img width="716" height="756" alt="image" src="https://github.com/user-attachments/assets/6f036d23-e2e0-4351-8349-9db9a48458a1" />

## VirusTotal – Get an IP Address Report

### Purpose

### The **Get an IP Address Report** action queries the VirusTotal API using the source IP address received from the Python Alert Generator. VirusTotal analyzes the IP address against its threat intelligence database and returns information such as reputation, malicious detections, community votes, and analysis statistics. These results help determine whether the IP address is associated with malicious activity.

### • Retrieves IP reputation from VirusTotal.

### • Uses the source IP address as the search identifier.

### • Returns detection statistics and reputation information.

### • Supports automated IOC enrichment.

###  Add API key from the virus total and navigate to the profile and API section 
<img width="1919" height="926" alt="image" src="https://github.com/user-attachments/assets/a0d29af3-b2c8-4eb5-9fca-bb7138f3b19a" />

---

## Configuration

### **Name**

```text
VirusTotal
```

### Identifies the integration used to retrieve IP reputation information.

---

### **Action**

```text
Get an IP address report
```

### Retrieves the analysis report for the specified IP address from VirusTotal.

---

### **Description**

```text
Retrieves the VirusTotal analysis report for an IP address to determine its reputation and detection statistics.
```

### Explains that the action queries VirusTotal using the supplied IP address and returns its associated threat intelligence information.

---

### **Documentation**

```text
https://docs.virustotal.com/reference/ip-info
```

### Official VirusTotal API documentation used to configure the IP Address Report API.

---

### **IP**

```text
webhook.body.details.source_ip
```

### Retrieves the source IP address from the incoming Webhook payload. This IP address is submitted to VirusTotal for reputation analysis.

---

### **API URL**

```text
https://www.virustotal.com/api/v3/ip_addresses/{source_ip}
```

### The API endpoint used to retrieve the reputation and analysis report for the specified IP address.

---

### **Content Type**

```text
Custom (JSON)
```

### Configures the request to communicate using JSON.

---

### **Method**

```text
GET
```

### Uses the HTTP GET method to retrieve the IP address report from VirusTotal.

---

### **Headers**

```text
x-apikey : CREDENTIAL.virustotal
```

### Authenticates the request using the VirusTotal API key securely stored in the Tines Credentials vault.

---

### **Payload**

```json
{}
```

### No request body is required because the source IP address is included directly in the API URL.

---

## **VirusTotal IP Address Report Configuration**

<img width="729" height="708" alt="image" src="https://github.com/user-attachments/assets/7239a667-b221-47c0-8937-bf4b626be002" />

<img width="730" height="813" alt="image" src="https://github.com/user-attachments/assets/e4750fe4-8fb9-420c-ad9d-30da62a38a72" />

## Run Script 2 (IP Score)

### Purpose

### The **Run Script 2** action extracts the **malicious detection count** from the VirusTotal IP Address Report. Instead of passing the complete VirusTotal response to later actions, the script returns only the IP score, making it easier to calculate the overall threat score and evaluate the alert.

### • Extracts the VirusTotal IP score.

### • Simplifies the API response.

### • Passes only the required value to downstream actions.

### • Supports threat score calculation and workflow decisions.

---

## Configuration

### **Name**

```text
Run Script 2
```

### Identifies the action responsible for extracting the VirusTotal IP score.

---

### **Description**

```text
Extracts the malicious detection count from the VirusTotal IP Address Report for use in threat score calculation and workflow decision-making.
```

### Explains that the script retrieves the IP reputation score from the VirusTotal response.

---

### **Runtime Environment**

```text
Python 3.13
```

### Executes the script using the Python 3.13 runtime environment provided by Tines.

---

### **Script**

```python
def main(input):
    return {
        "ip_score": input["ip_score"]
    }
```

### This script receives the IP score as input and returns it as a simplified output object. The extracted value is then used by later workflow actions to calculate the overall threat score.

### • Receives the input value.

### • Extracts the IP score.

### • Returns a simplified output.

### • Simplifies downstream processing.

---

### **Emit Failure Event**

```text
Always
```

### Configured to always emit a failure event if the script encounters an error, allowing failures to be logged and monitored.

---

### **Input**

```json
{
  "ip_score": "<<get_an_ip_address_report.body.data.attributes.last_analysis_stats.malicious>>"
}
```

### Retrieves the **malicious detection count** from the VirusTotal IP Address Report and passes it to the Python script.

---

### **Timeout**

```text
10 Seconds
```

### Allows the script a maximum of **10 seconds** to complete execution before timing out.

---

### **Requirements**

```text
requests==2.34.2
```

### Specifies the required Python package available during script execution. Although this script does not directly use the library, it is included as part of the runtime environment configuration.

---

## **Run Script 2 (IP Score) Configuration**
<img width="730" height="818" alt="image" src="https://github.com/user-attachments/assets/523c8912-cd4b-453e-9523-a2abbebfc1ad" />

<img width="726" height="758" alt="image" src="https://github.com/user-attachments/assets/07a81c96-7e65-4f24-ad31-a996c354fe4e" />


## VirusTotal – Get a File Report

### Purpose

### The **Get a File Report** action queries the VirusTotal API using the file hash received from the Python Alert Generator. VirusTotal searches its threat intelligence database and returns detailed information about the file, including detection statistics, reputation, scan results, and other security attributes. These results are later used by the workflow to determine whether the file is malicious or benign.

### • Retrieves file reputation from VirusTotal.

### • Uses the file hash as the search identifier.

### • Returns malware detection statistics.

### • Supports automated threat analysis.

### Add API key from the virus total and navigate to the profile and API section 
<img width="1919" height="926" alt="image" src="https://github.com/user-attachments/assets/a0d29af3-b2c8-4eb5-9fca-bb7138f3b19a" />


---

## Configuration

### **Name**

```text
VirusTotal
```

### Identifies the integration used to retrieve file reputation information.

---

### **Action**

```text
Get a file report
```

### Retrieves the analysis report for the specified file hash from VirusTotal.

---

### **Description**

```text
Retrieves the VirusTotal analysis report for a file using its SHA-256 hash to determine its reputation and detection statistics.
```

### Explains that the action queries VirusTotal using the supplied file hash and returns the associated analysis report.

---

### **Documentation**

```text
https://docs.virustotal.com/reference/file-info
```

### Official VirusTotal API documentation used to configure the File Report API.

---

### **ID**

```text
webhook.body.details.file_hash
```

### Retrieves the file hash from the incoming Webhook payload. This hash uniquely identifies the file that will be searched in VirusTotal.

---

### **API URL**

```text
https://www.virustotal.com/api/v3/files/{file_hash}
```

### The File Report API endpoint used to retrieve the reputation and analysis results for the specified file hash.

---

### **Content Type**

```text
JSON
```

### The API exchanges data in JSON format.

---

### **Method**

```text
GET
```

### Uses the HTTP GET method to retrieve the file report from VirusTotal.

---

### **Headers**

```text
x-apikey : CREDENTIAL.virustotal
```

### Authenticates the request using the VirusTotal API key stored securely in the Tines Credentials vault.

---

### **Payload**

```json
{}
```

### No request body is required because the file hash is included in the API URL.

---

### **VirusTotal File Report Configuration**
<img width="733" height="653" alt="image" src="https://github.com/user-attachments/assets/a4f8a8d6-4e4c-4c7d-be78-7b238932759a" />

<img width="733" height="669" alt="image" src="https://github.com/user-attachments/assets/78e50e40-7ea3-4ba2-8d6d-9990ddb9e192" />

<img width="732" height="137" alt="image" src="https://github.com/user-attachments/assets/7a52ffad-7bf9-44f5-99f2-672588ed398d" />

## Run Script 3 (Hash Score)

### Purpose

### The **Run Script 3** action extracts the **malicious detection count** from the VirusTotal File Report. Instead of passing the complete VirusTotal response to subsequent workflow actions, the script returns only the hash score, making it easier to calculate the overall threat score and determine whether the file is malicious.

### • Extracts the VirusTotal file hash score.

### • Simplifies the API response.

### • Passes only the required value to downstream actions.

### • Supports threat score calculation and workflow decision-making.

---

## Configuration

### **Name**

```text
Run Script 3
```

### Identifies the action responsible for extracting the VirusTotal file hash score.

---

### **Description**

```text
Extracts the malicious detection count from the VirusTotal File Report for use in threat score calculation and workflow decision-making.
```

### Explains that the script retrieves the file hash reputation score from the VirusTotal response.

---

### **Runtime Environment**

```text
Python 3.13
```

### Executes the script using the Python 3.13 runtime environment provided by Tines.

---

### **Script**

```python
def main(input):
    return {
        "hash_score": input["hash_score"]
    }
```

### This script receives the hash score as input and returns it as a simplified output object. The extracted value is then used by later workflow actions during threat score calculation and alert classification.

### • Receives the input value.

### • Extracts the hash score.

### • Returns a simplified output.

### • Simplifies downstream processing.

---

### **Emit Failure Event**

```text
Always
```

### Configured to always emit a failure event if the script encounters an error, allowing workflow failures to be logged and monitored.

---

### **Input**

```json
{
  "hash_score": "<<get_a_file_report.body.data.attributes.last_analysis_stats.malicious>>"
}
```

### Retrieves the **malicious detection count** from the VirusTotal File Report and passes it to the Python script.

---

### **Timeout**

```text
10 Seconds
```

### Allows the script a maximum of **10 seconds** to complete execution before timing out.

---

### **Requirements**

```text
requests==2.34.2
```

### Specifies the required Python package available during script execution. Although this script does not directly use the library, it is included as part of the runtime environment configuration.

---

### **Run Script 3 (Hash Score) Configuration**
<img width="736" height="822" alt="image" src="https://github.com/user-attachments/assets/c140e769-8e5c-42fa-9c36-3b436111400c" />

<img width="735" height="835" alt="image" src="https://github.com/user-attachments/assets/6d4bf7c5-602d-4743-a4dc-da40dcbf5580" />

## Event Transform (Message Builder)

### Purpose

### The **Event Transform (Message Only)** action combines data collected from previous workflow actions into a single structured message. It gathers the original alert information together with the reputation scores extracted from VirusTotal and URLScan.io, creating a standardized payload that is passed to the next stage of the workflow.

### • Combines data from multiple actions.

### • Creates a standardized message.

### • Includes IOC reputation scores.

### • Passes structured data to downstream actions.

---

## Configuration

### **Name**

```text
Event Transform
```

### Identifies the action responsible for combining and formatting workflow data.

---

### **Description**

```text
Builds a structured payload containing the original alert details and threat intelligence scores for downstream processing.
```

### Explains that the action consolidates data from multiple workflow steps into a single message.

---

### **Mode**

```text
Message Only
```

### Configures the Event Transform to create a new message without modifying or delaying workflow execution.

---

### **Payload**

```json
{
  "records": [
    {
      "fields": {
        "alert_id": "<<webhook.body.alert_id>>",
        "source_ip": "<<webhook.body.details.source_ip>>",
        "destination_url": "<<webhook.body.details.destination_url>>",
        "file_hash": "<<webhook.body.details.file_hash>>",
        "ip_score": "<<run_script_2.output.ip_score>>",
        "hash_score": "<<run_script_3.output.hash_score>>",
        "url_score": "<<run_script_1.output.url_score>>",
        "average": 0,
        "processed": false
      }
    }
  ]
}
```

### The payload combines the original alert details received from the Webhook with the reputation scores extracted by the three Run Script actions. It also initializes the **average** score to **0** and the **processed** status to **false**, which are updated later in the workflow.

### **Payload Fields**

| **Field** | **Description** |
|-----------|-----------------|
| **alert_id** | Unique identifier of the generated alert. |
| **source_ip** | Source IP address received from the Webhook. |
| **destination_url** | Destination URL to be analyzed. |
| **file_hash** | SHA-256 file hash received from the alert. |
| **ip_score** | Malicious detection count from the VirusTotal IP Report. |
| **hash_score** | Malicious detection count from the VirusTotal File Report. |
| **url_score** | Reputation score returned by URLScan.io. |
| **average** | Placeholder value initialized to **0** for later threat score calculation. |
| **processed** | Processing flag initialized to **false** until the workflow completes. |

---

### **Event Transform (Message Builder) Configuration**
<img width="728" height="575" alt="image" src="https://github.com/user-attachments/assets/217d9456-68ff-4fea-b9b4-ca35b019bf07" />

<img width="726" height="619" alt="image" src="https://github.com/user-attachments/assets/611df32c-406d-48a9-a2e0-6290d1651b20" />

## Run Script (Threat Score Calculation)

### Purpose

### The **Run Script** action calculates the **overall threat score** by combining the reputation scores obtained from VirusTotal IP analysis, VirusTotal File analysis, and URLScan.io URL analysis. It computes the average of these three values and returns both the individual scores and the final average, which is later used to classify alerts as malicious or benign.

### • Collects all IOC reputation scores.

### • Calculates the overall threat score.

### • Returns the individual and average scores.

### • Supports automated alert classification.

---

## Configuration

### **Name**

```text
Run Script
```

### Identifies the action responsible for calculating the overall threat score.

---

### **Description**

```text
Calculates the overall threat score by averaging the IP, file hash, and URL reputation scores collected from VirusTotal and URLScan.io.
```

### Explains that this action combines the three IOC scores into a single threat score used for decision-making.

---

### **Runtime Environment**

```text
Python 3.13
```

### Executes the script using the Python 3.13 runtime environment provided by Tines.

---

### **Script**

```python
def main(input):
    ip = int(input.get("ip_score") or 0)
    hash_score = int(input.get("hash_score") or 0)
    url_score = int(input.get("url_score") or 0)

    average = (ip + hash_score + url_score) / 3

    return {
        "ip_score": ip,
        "hash_score": hash_score,
        "url_score": url_score,
        "average": round(average, 2)
    }
```

### The script retrieves the IP score, file hash score, and URL score from previous Run Script actions. It converts each value into an integer, calculates the average threat score, rounds it to two decimal places, and returns both the individual scores and the final average.

### • Reads the three IOC scores.

### • Converts values to integers.

### • Calculates the average threat score.

### • Returns the calculated results.

---

### **Emit Failure Event**

```text
Always
```

### Configured to always emit a failure event if the script encounters an error, allowing workflow failures to be logged and monitored.

---

### **Input**

```json
{
  "ip_score": "<<run_script_2.output.ip_score>>",
  "hash_score": "<<run_script_3.output.hash_score>>",
  "url_score": "<<run_script_1.output.url_score>>"
}
```

### Retrieves the reputation scores generated by the previous Run Script actions and passes them to the Python script for threat score calculation.

---

### **Timeout**

```text
10 Seconds
```

### Allows the script a maximum of **10 seconds** to complete execution before timing out.

---

### **Requirements**

```text
requests==2.34.2
```

### Specifies the required Python package available during script execution. Although this script does not directly use the library, it is included as part of the runtime environment configuration.

---

### **Run Script (Threat Score Calculation) Configuration**
<img width="738" height="496" alt="image" src="https://github.com/user-attachments/assets/f6608ea6-20df-4220-9e7b-b004b7b55ab0" />

<img width="729" height="539" alt="image" src="https://github.com/user-attachments/assets/5112ba26-7464-46a0-874a-df442d4da3ab" />

<img width="724" height="776" alt="image" src="https://github.com/user-attachments/assets/2c34dee0-9605-45e3-880a-262f1e0a02db" />

## Condition

### Purpose

### The **Condition** action evaluates the calculated threat score and determines whether the alert should be classified as **malicious** or **benign**. It checks the average threat score generated by the previous Run Script action and routes the workflow to the appropriate response path.

### • Evaluates the calculated threat score.

### • Applies the workflow decision logic.

### • Routes alerts to the appropriate response path.

### • Determines whether an alert is malicious or benign.

---

## Configuration

### **Name**

```text
Condition
```

### Identifies the action responsible for evaluating the calculated threat score.

---

### **Description**

```text
Evaluates the calculated average threat score and determines whether the alert should follow the malicious or benign workflow.
```

### Explains that the action uses the calculated threat score to decide the next step in the automation process.

---

### **Rules**

```text
run_script.output.average
is greater than
0
```

### The condition checks whether the **average threat score** calculated by the previous Run Script is greater than **0**. If the condition evaluates to **True**, the alert is treated as **malicious** and the workflow proceeds to create a Jira incident. If the result is **False**, the alert follows the benign workflow.

### • Retrieves the calculated average threat score.

### • Compares the score against the defined threshold.

### • Routes malicious alerts to the incident response workflow.

### • Routes benign alerts to the non-malicious workflow.

### **Condition Configuration**
<img width="727" height="883" alt="image" src="https://github.com/user-attachments/assets/0cdb56ed-87a4-4569-b7aa-291776256b00" />

















