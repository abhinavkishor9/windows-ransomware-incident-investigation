# windows-ransomware-incident-investigation
## Overview

This project demonstrates a simulated ransomware incident investigation on a Windows endpoint.

Instead of executing real ransomware, safe attack artifacts were created to emulate common ransomware behavior. The investigation focuses on collecting evidence, identifying indicators of compromise (IOCs), correlating multiple log sources, and reconstructing the attack timeline.

The lab follows a SOC analyst workflow from initial detection to incident analysis and cleanup.

---

## Objectives

- Simulate PowerShell execution
- Simulate ransomware-like file modifications
- Create a ransom note
- Create persistence using a Scheduled Task
- Investigate Sysmon events
- Investigate Microsoft Defender Operational logs
- Correlate endpoint artifacts
- Build an incident timeline
- Identify Indicators of Compromise (IOCs)

---

## Lab Environment

- Windows 10
- PowerShell
- Sysmon
- Microsoft Defender Antivirus
- Windows Event Viewer

---

## Simulated Attack Chain

PowerShell Execution

↓

Payload Execution

↓

Sample Files Renamed

↓

Ransom Note Created

↓

Scheduled Task Persistence

↓

Microsoft Defender Quick Scan

↓

SOC Investigation

---

## Investigation Workflow

### Phase 1 – Initial Execution

Executed:

```
powershell.exe -ExecutionPolicy Bypass
```

Evidence collected

- Sysmon Event ID 1
- Process Name
- Parent Process
- Command Line

MITRE ATT&CK

- T1059.001 – PowerShell

---

### Phase 2 – Simulated File Impact

Sample files were renamed to:

- *.locked

A simulated ransom note was created:

```
README_RESTORE_FILES.txt
```

Purpose

Safely emulate ransomware impact without encrypting files.

MITRE ATT&CK

- T1486 – Data Encrypted for Impact (Simulation)

---

### Phase 3 – Persistence

Created Scheduled Task

```
RansomwareLabTask
```

MITRE ATT&CK

- T1053.005 – Scheduled Task

---

### Phase 4 – Defender Investigation

Investigated:

- Event ID 1000
- Event ID 1001

Collected

- Scan Type
- User
- Scan Duration
- Scan Status

---

### Phase 5 – Timeline Reconstruction

Correlated:

- PowerShell
- File modifications
- Scheduled Task
- Microsoft Defender
- Endpoint artifacts

---

## Indicators of Compromise (IOCs)

- PowerShell execution with ExecutionPolicy Bypass
- payload.ps1
- README_RESTORE_FILES.txt
- *.locked files
- Scheduled Task: RansomwareLabTask
- Lab folder:
  - C:\RansomwareLab

---

## MITRE ATT&CK Mapping

| Activity | Technique |
|----------|-----------|
| PowerShell Execution | T1059.001 |
| Scheduled Task Persistence | T1053.005 |
| Simulated File Encryption | T1486 |
| File Download (if applicable) | T1105 |

---

## Skills Demonstrated

- Incident Response
- Threat Hunting
- Windows Endpoint Investigation
- Sysmon Analysis
- Microsoft Defender Investigation
- IOC Identification
- Timeline Reconstruction
- MITRE ATT&CK Mapping

---

## Learning Outcome

This project demonstrates how a SOC analyst investigates a suspected ransomware incident by correlating endpoint artifacts with Windows logs and Microsoft Defender events to reconstruct attacker activity and identify indicators of compromise.
