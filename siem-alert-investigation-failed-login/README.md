# SIEM Alert Investigation — Suspicious Failed Logins

## 🧠 Overview
This project simulates a SIEM-style alert investigation involving multiple failed login attempts followed by a successful login. The goal is to analyze authentication logs, identify potential brute-force or credential-stuffing behavior, and document findings using a SOC-style investigation approach.

---

## 🎯 Objectives

- Review authentication-related logs as if received from a SIEM alert
- Identify suspicious patterns in failed and successful logins
- Correlate events by user, IP address, and time window
- Assess risk and determine whether escalation is needed
- Propose basic detection logic and response recommendations

---

## 🛠️ Tools & Concepts

- **Log Source:** Windows Security Logs / Linux auth logs (simulated)
- **Concepts:** SIEM alerts, correlation, brute-force detection, account compromise
- **Frameworks:** MITRE ATT&CK (Initial Access, Credential Access)
- **Optional:** Python for basic log parsing and filtering

---

## 📂 Sample Dataset (Conceptual)

Example log fields (CSV or log format):

- `Timestamp`
- `Username`
- `Source_IP`
- `Event_Type` (e.g., Failed_Login, Successful_Login)
- `Authentication_Method` (e.g., RDP, SSH, Web)
- `Location` (if available)

Example (simplified):

```text
2025-01-10 10:01:23, jdoe, 192.168.1.50, Failed_Login, RDP
2025-01-10 10:01:45, jdoe, 192.168.1.50, Failed_Login, RDP
2025-01-10 10:02:10, jdoe, 192.168.1.50, Failed_Login, RDP
2025-01-10 10:03:01, jdoe, 192.168.1.50, Successful_Login, RDP
IF
  count(Failed_Login where Username = X and Source_IP = Y within 5 minutes) >= 5
AND
  Successful_Login where Username = X and Source_IP = Y within same 5 minutes
THEN
  Raise Alert: Possible brute-force / credential compromise

---

### 3. Commit it

After you paste that into `siem-alert-investigation-failed-logins/README.md`:

- Save the file
- Commit with a message like:

```text
Add SIEM-style alert investigation for suspicious failed logins
