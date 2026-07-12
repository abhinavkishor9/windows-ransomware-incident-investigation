# Troubleshooting Notes

## Issue

PowerShell script failed to execute.

### Resolution

Verify the file exists.

```
C:\RansomwareLab\payload.ps1
```

---

## Issue

Scheduled Task not created.

### Resolution

Run PowerShell as Administrator.

Verify

```
schtasks /query
```

---

## Issue

Sysmon Event ID 1 not generated.

### Resolution

Verify Sysmon service.

```
Get-Service Sysmon64
```

Expected

Running

---

## Issue

Microsoft Defender events missing.

### Resolution

Complete the Quick Scan before checking Event Viewer.

Navigate to

Applications and Services Logs

↓

Microsoft

↓

Windows

↓

Windows Defender

↓

Operational

---

## Issue

Event IDs not appearing.

Refresh Event Viewer.

Press

```
F5
```

---

## Issue

Lab folder not deleted.

Resolution

```
Remove-Item C:\RansomwareLab -Recurse -Force
```

---

## Issue

Scheduled Task still exists.

Delete

```
schtasks /delete /tn RansomwareLabTask /f
```

Verify

```
schtasks /query
```

---

## Lessons Learned

- Ransomware investigations require correlating multiple evidence sources rather than relying on a single log.
- Sysmon, Microsoft Defender, and endpoint artifacts together provide the context needed to reconstruct attacker activity.
- Building a timeline and identifying IOCs are essential steps in incident response.
