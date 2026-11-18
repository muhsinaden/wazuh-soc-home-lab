# Wazuh SOC Home Lab | Security Monitoring & Threat Detection

![Platform](https://img.shields.io/badge/Platform-Wazuh-blue)
![SIEM](https://img.shields.io/badge/Technology-SIEM-orange)
![OS](https://img.shields.io/badge/Endpoint-Windows%2011-blue)
![Status](https://img.shields.io/badge/Project-Completed-success)

## About This Project

I built this SOC home lab to develop practical cybersecurity skills and gain hands-on experience with Security Information and Event Management (SIEM).

Rather than relying only on theoretical learning, I configured the environment, generated controlled security events, developed custom detection rules, investigated alerts, and documented the results.

This project represents my practical learning journey toward a career in Security Operations and Blue Team cybersecurity.

## Project Overview

This project demonstrates the design, deployment, and configuration of a Security Operations Center (SOC) home lab using **Wazuh SIEM**.

The lab integrates an Ubuntu-based Wazuh server with a Windows 11 endpoint to collect security telemetry, monitor endpoint activity, develop custom detection rules, and investigate security events.

The objective was to gain practical experience with SIEM operations, endpoint security monitoring, threat detection, and SOC investigation workflows.

## Lab Architecture

| Component | Configuration |
|---|---|
| SIEM Platform | Wazuh 4.14.10 |
| Server OS | Ubuntu 26.04.1 LTS |
| Endpoint OS | Windows 11 |
| Virtualization | Oracle VirtualBox |
| Endpoint Integration | Wazuh Agent |
| Detection Engine | Wazuh Rules |
| Monitoring Dashboard | Wazuh Dashboard |

## Practical Exercises

### 1. SIEM Deployment and Endpoint Integration
- Installed Wazuh Manager, Indexer, and Dashboard.
- Integrated a Windows 11 endpoint using Wazuh Agent.
- Verified endpoint connectivity and agent status.

### 2. Windows Authentication Monitoring
- Monitored Windows Security Event ID 4625.
- Detected controlled failed login attempts.
- Investigated authentication failure events.

### 3. Brute-Force Detection
- Developed custom Wazuh rule `100100`.
- Configured detection for five failed logons within 120 seconds.
- Tested the detection using controlled authentication failures.

### 4. File Integrity Monitoring (FIM)
- Configured real-time monitoring of a Windows test directory.
- Detected file creation, modification, and deletion.
- Investigated Wazuh FIM events.

### 5. PowerShell Monitoring
- Enabled PowerShell Operational event collection.
- Monitored script-block logging (Event ID 4104).
- Developed custom rule `100200` to detect `Get-LocalUser`.
- Mapped the detection to MITRE ATT&CK T1087.001.

### 6. Windows Process Creation Monitoring
- Enabled Windows process creation auditing (Event ID 4688).
- Enabled process command-line logging.
- Developed custom rule `100300`.
- Investigated process execution telemetry.

### 7. Safe Malware Indicator Simulation
- Created a harmless command-line simulation marker.
- Developed custom rule `100400`.
- Verified that Wazuh generated an alert when the marker was executed.

**Note:** No actual malware was downloaded or executed.

### 8. SOC Dashboard Development
Created a centralized security monitoring dashboard containing:
- Total security alerts
- Failed Windows logons
- High-severity alerts
- Brute-force detection
- PowerShell account discovery
- Process execution
- File Integrity Monitoring events

### 9. Windows Firewall Log Collection
- Enabled Windows Firewall logging.
- Configured the Wazuh Agent to collect `pfirewall.log`.
- Verified firewall records in the Wazuh Manager JSON archive.

**Note:** Firewall collection was verified at the raw archive level; the records were not confirmed as indexed Threat Hunting alerts.

## Custom Detection Rules

| Rule ID | Detection | Severity |
|---|---|---|
| 100100 | Repeated Windows failed logons | Level 10 |
| 100200 | PowerShell local account discovery | Level 10 |
| 100300 | Controlled process execution test | Level 8 |
| 100400 | Simulated malware indicator | Level 10 |

The custom rules were tested using controlled lab activity.

## Technical Skills Demonstrated

- Wazuh SIEM deployment and administration
- Windows endpoint monitoring
- Security event collection and analysis
- Custom detection rule development
- Authentication monitoring
- Brute-force detection logic
- File Integrity Monitoring
- PowerShell security monitoring
- Windows process auditing
- MITRE ATT&CK mapping
- Threat hunting and alert investigation
- Firewall log collection
- SOC dashboard development

## Project Evidence

Screenshots and supporting documentation will be organized in the repository:

- `screenshots/` — Lab configuration, detection results, and dashboard evidence
- `rules/` — Custom Wazuh detection rules
- `configuration/` — Sanitized configuration examples
- `docs/` — Technical documentation and project report
- `evidence/` — Test results and investigation notes

## Lessons Learned

Through this project, I gained practical experience deploying a SIEM platform, integrating endpoints, collecting Windows security telemetry, writing and testing custom detection rules, investigating alerts, and building a centralized SOC dashboard.

This project was completed as an independent cybersecurity home lab for practical learning and skills development.

**Project classification:** Personal hands-on cybersecurity lab — not commercial SOC employment experience.
