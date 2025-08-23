# Threat-Detection-Engineering
This project focuses on developing advanced threat detection capabilities aligned with the MITRE ATT&CK framework by implementing Sigma rules within SIEM platforms. The goal is to enhance security monitoring by translating high-level adversary behaviors into actionable detection logic that can be deployed across multiple SIEM solutions.

Threat detection is critical in modern cybersecurity operations. The MITRE ATT&CK framework provides a comprehensive matrix of adversary tactics, techniques, and procedures (TTPs) used by attackers. Sigma is an open standard for writing detection rules in a generic format that can be converted into SIEM-specific query languages.

This project demonstrates how to engineer, implement, and test Sigma-based detection rules targeting ATT&CK techniques within popular SIEM environments, improving the accuracy and coverage of threat monitoring.

# Features

- Develop Sigma detection rules mapped to relevant MITRE ATT&CK techniques
- Convert Sigma rules to SIEM-specific queries for platforms such as Splunk, Elastic, and others
- Validate and test detection logic with simulated threat data or historical logs
- Integrate detection rules into SIEM alerting workflows for real-time monitoring
- Document best practices for writing and maintaining scalable Sigma rulesets

# Prerequisites
- SIEM platform access (e.g., Splunk, Elastic, QRadar, Sentinel)
- Sigma CLI tool (https://github.com/SigmaHQ/sigma)
- Sample log datasets or simulated attack logs
- Basic knowledge of MITRE ATT&CK framework and SIEM query languages
- Python 3.x (optional, for automation scripts)

# Installation
1. Clone this repository:
``
PLACEHOLDER
``
2. Install Sigma CLI tool (https://github.com/SigmaHQ/sigma).
3. Configure your SIEM environment to accept custom detection queries.

# Usage
- Browse Sigma rules in the rules/ directory organized by ATT&CK tactic.
- Use the Sigma CLI to convert rules to your SIEM format:
``sigma convert -t splunk PLACEHOLDER``
- Import generated queries into your SIEM for testing and deployment.
- Simulate attacks or replay logs to validate detection efficacy.

# Walkthrough

## Lab Environment Setup
- systems to simulate (AD Controller, endpoints, linux server, etc)
- Choose attack simulation scope, common TTPs (lateral movement, privilege escalationm, etc)
- Configure Active Directory and Endpoint
- Deploy SIEM (Splunk or ELastic) and configure log collection

## Mapping MITRE ATT&CK Techniques
- Selecting techniques
  - Inital Access: Brute Force
  - Execution: CLI
  - Lateral Movement: RDP, pass-the-hash
  - Privilege Escalation: Token Impersonation, etc
- Document each technique (name, MITRE ID, expected log source/event, detection logic (what event pattern indicate this technique))

## Create Sigma Rules
- Sigma rules = YAML files describing generic detection logic
  - included fields: title, id, desc, status, logsource, detection, level, tags, etc
- Write the Rules
- Create Additional rules for additional techniques (prioritize privilege escalation and lateral movement out of them all)

## Implement Sigma Rules in Splunk
- Convert Sigma to Splunk Queries (sigmac)
- Load queries into SIEM
- Test rule accuracy (small simulate attack)

## Simulate Attack
- Run Controlled Scenarios
- Log results
  - Document triggered alerts
  - Record MTTD for each scenario

## Automate Triage and Response
- Identify Response Action
  - isolate endpoints (EDR + Shuffle?)
- Implement Automation
  - Use Splunk Alert + Scripts (Or SOAR?) to trigger automated response
- Measure Metrics
  - MTTD
  - MTTR
  - False Positve/negatives

## Reporting
- Create Dashboard
  - Show coverageby MITRE ATT&CK Category
  - Include alert count, MTTD, MTTR
- Document Lesson Learned
  - List which Sigma Rules are performing
  - Identify gaps in detection coverage
  - Sugget real-world improvement
  
- 
