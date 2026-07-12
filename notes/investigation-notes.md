# Investigation Notes

## Incident Summary

A Windows endpoint generated multiple suspicious activities resembling a ransomware attack.

The objective was to determine:

- Initial execution
- Persistence mechanism
- File impact
- Defender response
- Indicators of Compromise

---

# Investigation Timeline

## Step 1

PowerShell payload created.

Location

```
C:\RansomwareLab\payload.ps1
```

---

## Step 2

PowerShell executed.

Observed

Sysmon Event ID 1

Command

```
powershell.exe -ExecutionPolicy Bypass -File C:\RansomwareLab\payload.ps1
```

MITRE

T1059.001

---

## Step 3

Sample files renamed.

Examples

```
Invoice.docx.locked

Budget.xlsx.locked

Notes.txt.locked
```

Purpose

Simulate ransomware impact.

---

## Step 4

Ransom note created.

Observed

```
README_RESTORE_FILES.txt
```

Purpose

Simulate attacker communication.

---

## Step 5

Persistence established.

Method

Scheduled Task

Task Name

```
RansomwareLabTask
```

MITRE

T1053.005

---

## Step 6

Microsoft Defender Quick Scan executed.

Observed

Event ID

1000

Scan Started

Event ID

1001

Scan Finished

---

# Timeline Reconstruction

PowerShell Executed

↓

Payload Executed

↓

Files Renamed

↓

Ransom Note Created

↓

Scheduled Task Created

↓

Microsoft Defender Scan Started

↓

Microsoft Defender Scan Completed

---

# Indicators of Compromise

PowerShell

```
powershell.exe
```

Payload

```
payload.ps1
```

Ransom Note

```
README_RESTORE_FILES.txt
```

Extension

```
.locked
```

Scheduled Task

```
RansomwareLabTask
```

---

# Conclusion

No real ransomware was executed.

The investigation safely demonstrated how a SOC analyst reconstructs ransomware activity by correlating endpoint artifacts, Sysmon logs, and Microsoft Defender Operational events into a complete attack timeline.
