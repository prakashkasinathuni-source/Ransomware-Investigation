# Ransomware Investigation

This folder contains a SOC investigation of a ransomware incident detected in an enterprise environment.

---

## Overview

A ransomware attack was detected after multiple endpoints began showing encrypted files and ransom notes. The SIEM and EDR systems triggered high-severity alerts due to abnormal file system activity and process behavior.

---

## What was analyzed

- Endpoint detection alerts
- File system changes
- Process execution logs
- Network traffic analysis
- SIEM correlation events
- Ransomware behavior patterns

---

## Key Findings

- Files encrypted with `.locked` extension
- Ransom note created on system
- Malicious executable identified
- Possible lateral movement attempts detected
- Attack contained before full propagation

---

## Skills Demonstrated

- Ransomware investigation
- Endpoint security analysis
- SIEM correlation and detection
- Incident response workflow
- Malware behavior analysis
- Threat containment strategies
- MITRE ATT&CK mapping

---

## MITRE ATT&CK

- T1486 – Data Encrypted for Impact  
- T1059 – Command and Scripting Interpreter  
- T1105 – Ingress Tool Transfer  
- T1047 – WMI Execution  

---

## Outcome

The ransomware attack was successfully contained, and affected systems were restored using backups. No organization-wide impact occurred.

---

## Disclaimer

All data used in this investigation is fictional and created for educational portfolio purposes only.
