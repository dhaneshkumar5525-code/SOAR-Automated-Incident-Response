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

## Tines SOAR Workflow



