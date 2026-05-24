# Ransomware Incident Investigation

## Alert Description

A high-severity alert was triggered indicating unusual file encryption activity, mass file renaming, and abnormal CPU/disk usage on an endpoint. Multiple files were observed becoming inaccessible with changed extensions.

---

## Severity

Critical

---

## Detection Source

SIEM (Splunk / Microsoft Sentinel / IBM QRadar correlation)

---

## Investigation Steps

1. Reviewed endpoint alerts indicating abnormal file modifications.
2. Identified rapid encryption of user files across multiple directories.
3. Checked process execution logs for suspicious binaries.
4. Analyzed network connections from infected host.
5. Reviewed persistence mechanisms (registry, startup folders).
6. Correlated SIEM logs for lateral movement indicators.
7. Verified ransom note creation on desktop.
8. Checked for spread across other endpoints.

---

## Logs Reviewed

- Sysmon Logs
- Windows Security Event Logs
- Endpoint Detection & Response (EDR) logs
- Firewall Logs
- SIEM Correlation Events

---

## Suspicious Activity Observed

- Mass file renaming with unknown extension `.locked`
- High CPU usage by unknown process
- Creation of ransom note: `READ_ME.txt`
- Execution from Downloads folder
- Attempted SMB network scanning behavior

---

## Indicators of Compromise (IOCs)

- File Name: encryptor.exe  
- Ransom Note: READ_ME.txt  
- File Extension: .locked  
- Hostname: WIN10-USER05  
- Suspicious IP: 185.XX.XX.77  
- SHA256 Hash: 4f9a3b8c2d1e77a90b11  

---

## MITRE ATT&CK Mapping

- T1486 – Data Encrypted for Impact  
- T1059 – Command and Scripting Interpreter  
- T1105 – Ingress Tool Transfer  
- T1047 – Windows Management Instrumentation  

---

## Root Cause

The ransomware was introduced through a malicious email attachment. Upon execution, it encrypted local and shared files and attempted to spread laterally via network shares.

---

## Containment Actions

- Isolated infected endpoint immediately
- Disabled affected user account
- Blocked malicious IP addresses
- Stopped file-sharing services temporarily
- Restored files from backup
- Initiated forensic image collection
- Blocked ransomware hash across endpoints

---

## Final Conclusion

The ransomware attack was detected early and contained before organization-wide spread. Data loss was minimized due to rapid response and backup restoration.

---

## Recommendations

- Implement offline backups
- Enable EDR ransomware protection
- Restrict SMB share access
- Improve email filtering policies
- Conduct phishing awareness training
- Enable application whitelisting
