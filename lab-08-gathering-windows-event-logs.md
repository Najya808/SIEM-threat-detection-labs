# Lab 08 — Gathering Windows Event Logs

## 🎯 Objectives
- Understand how Windows Event Logs are collected.
- Install and configure Winlogbeat agent.
- Specify which logs to collect.
- Verify logs inside SIEM dashboard.

---

## 🧰 Tools Used
- Winlogbeat
- Windows Event Viewer
- ELK Stack / SIEM Dashboard
- PowerShell

---

## 📋 Lab Steps

### ✅ Step 1 — Install Winlogbeat
1. Download Winlogbeat from official Elastic website.
2. Extract to:
C:\Program Files\Winlogbeat

3. Open PowerShell as Administrator:
```powershell
cd 'C:\Program Files\Winlogbeat'
.\install-service-winlogbeat.ps1
✅ Step 2 — Configure Event Logs
Open:

winlogbeat.yml
Add logs to collect:

winlogbeat.event_logs:
  - name: Application
  - name: Security
  - name: System
Save file.

✅ Step 3 — Start Service & Verify Logs
Start Winlogbeat:

Start-Service winlogbeat
Check logs:

Get-EventLog -LogName Application -Newest 5
✅ Step 4 — Verify Inside SIEM
Open SIEM Dashboard.

Search for Windows events.

Confirm:

Application logs

Security logs

System logs

🧠 What I Learned
How Windows logs are shipped to SIEM.

How to configure Winlogbeat.

Importance of Application, Security & System logs.

How SIEM helps in monitoring system activity.

✅ Conclusion
Successfully installed Winlogbeat, configured event log collection, and verified log ingestion inside SIEM for monitoring and analysis.
