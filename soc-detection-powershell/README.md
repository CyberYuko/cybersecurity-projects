# SOC Detection Project — Suspicious PowerShell Activity

## 🧠 Overview
This project simulates a real SOC investigation involving suspicious PowerShell execution. The goal is to analyze logs, identify malicious behavior, and create detection logic that could be used in a SIEM.

## 🎯 Objectives
- Analyze PowerShell command-line logs
- Identify indicators of malicious activity
- Document findings using SOC-style methodology
- Create detection rules for SIEM platforms
- Strengthen blue-team investigation skills

---

## 🛠️ Tools Used
- Windows Event Logs (Security + PowerShell)
- PowerShell command-line auditing
- Sigma rule format (for detection logic)
- MITRE ATT&CK mapping

---

## 📂 Dataset
Simulated PowerShell logs containing:
- Encoded commands
- Suspicious flags (`-nop`, `-w hidden`, `-enc`)
- Network callbacks
- Fileless execution patterns

Example log entry:
