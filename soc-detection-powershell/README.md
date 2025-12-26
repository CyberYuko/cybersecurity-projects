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

---

## 🔍 Investigation Steps

### **1. Identify Suspicious Indicators**
Common red flags:
- Base64 encoded commands (`-enc`)
- No profile (`-nop`)
- Hidden window (`-w hidden`)
- Download cradle (`IEX (New-Object Net.WebClient).DownloadString(...)`)
- Execution from unusual directories

### **2. Decode the Base64 Command**
Decoded output:
(Example — your dataset may vary)

### **3. Map to MITRE ATT&CK**
- **T1059.001 — PowerShell**
- **T1086 — Script Execution**
- **T1027 — Obfuscated/Encoded Commands**

### **4. Determine Severity**
**High** — encoded PowerShell + hidden window + no profile = strong malicious pattern.

---

## 🛡️ Detection Logic (Sigma Rule)

---

## 📝 Final Summary
This investigation identified suspicious PowerShell activity involving encoded commands and hidden execution. These behaviors are commonly associated with malware, fileless attacks, and initial access payloads. A Sigma detection rule was created to help identify similar activity in a SIEM environment.

---

## 🚀 Next Steps
- Build a second detection for **failed RDP brute-force attempts**
- Add a log parser script (Python)
- Expand to a full “SOC Analyst Playbook” project

