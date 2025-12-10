# SOC Task 2 – Security Alert Monitoring and Incident Response

## Introduction
This repository documents the execution of Security Operations Center (SOC) Task 2 as part of a cybersecurity internship. The objective of this task is to simulate real-world SOC operations including log monitoring, threat identification, incident categorization, and response planning using a SIEM platform.

The work replicates the duties of an entry-level SOC analyst and demonstrates the ability to analyze security events, identify suspicious activities, apply triage logic, and escalate incidents professionally.

## Technology Stack

| Component | Purpose |
|---|---|
| Elastic Security (Kibana) | SIEM platform for log ingestion, search, and visualization |
| Sample SOC Logs | Source events used for threat simulation |
| Google Sheets / Excel | Severity classification mapping |
| Documentation Tool | Incident report and email escalation drafting |

## Dataset Description
The sample SOC dataset contains combined security events including:
- Authentication attempts
- File access activity
- Internal connection attempts
- Malware detection alerts (Trojan indicators)

All logs were indexed into Kibana as a data view named `soc_logs` and analyzed through Elastic Discover.

## Setup & Installation

### 1. Launch Elastic Security (Cloud)
- Login to Elastic Cloud (trial or licensed)
- Navigate to Security → Discover

### 2. Import Logs
- Upload the provided SOC log file
- Create index: `soc_logs`
- Expand the time filter to last 30–90 days

### 3. Validate Fields
Ensure the imported logs have usable fields including:
- action
- user.name
- source.ip
- event.category
- threat

## Usage

### Query 1: Malware Detection

### Query 2: Unauthorized Connection Attempts

### Query 3: Successful Login Events

## Findings

### High Severity Incident
- Event: Trojan Malware Infection  
- User: bob  
- Host: 10.0.0.5  
- Indicator: `action=malware detected`  
- Classification: High

### Medium Severity Incident
- Event: Unauthorized internal connection attempts  
- Users: charlie, david  
- Classification: Medium

### Low Severity Activity
- Event: Valid user login  
- Users: bob, charlie  
- Classification: Low

## Severity Classification Matrix

| Category | Host/User | Severity | Assessment |
|---|---|---|---|
| Trojan Infection | bob / 10.0.0.5 | High | Compromised system requiring isolation |
| Internal Network Probing | charlie, david | Medium | Unapproved access or scanning attempts |
| User Login Events | bob, charlie | Low | Normal authentication unless linked to malware |

## Recommended Response Actions

### High Severity (Trojan)
- Isolate host immediately
- Perform malware scan and remediation
- Reset affected credentials
- Patch system and validate endpoint controls

### Medium Severity (Access Attempts)
- Track repeated connection failures
- Enforce network segmentation and access limits
- Monitor for brute force escalation

### Low Severity (Login Success)
- Retain for correlation with endpoint compromise
- Validate permission levels

## Screenshots
- screenshots/malware_detection.png
- screenshots/connection_attempts.png
- screenshots/login_success.png
- screenshots/security_dashboard.png

## Project Deliverables
- SIEM Investigation Screenshots  
- Severity Classification Sheet  
- Incident Response Report  
- Incident Escalation Email  

## Conclusion
This SOC assignment effectively replicates core security monitoring activities and demonstrates analytical capability in:
- Log triage and pattern recognition
- Threat severity classification
- Malware detection and containment analysis
- Structured escalation and communication

The results are aligned with industry SOC workflows and demonstrate proficiency in SIEM-based incident response.

