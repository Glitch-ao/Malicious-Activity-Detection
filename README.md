# Techniques to Determine Malicious Activity

In this project, I focused on identifying and preventing malicious login activity across Windows and Linux environments. I used PowerShell scripting to monitor Windows Event Logs and reviewed Linux login event data to detect suspicious behavior like brute-force attacks.

## Tags
`Windows Event Log` `Login Events` `PowerShell ISE` `Brute Force Attack`

---

### 1. Enabled Audit Logon Events on Windows
- Enabled **Audit Logon Events** through the Local Security Policy (`secpol.msc`) to capture successful and failed login attempts.
- Verified audit policy changes using `auditpol /get /category:*`.

### 2. Generated and Collected Logs for Evaluation
- Intentionally triggered multiple failed login attempts to simulate a brute force attack.
- Viewed and analyzed log entries in **Windows Event Viewer** (Event ID 4625 for failed logons, 4624 for successful ones).

### 3. PowerShell Script for Logon Event Monitoring
- Used **PowerShell ISE** to write a script that:
  - Queries recent login events from the Event Log
  - Filters failed logon attempts
  - Highlights accounts or IP addresses with repeated failures
- Ran the script to continuously monitor the system for malicious behavior.

### 4. Linux Login Event Monitoring
- On a Linux VM, accessed login records using `journalctl`, `last`, and `auth.log`.
- Detected brute force patterns using `grep` and `fail2ban`.
- Configured fail2ban to automatically block repeated failed SSH login attempts.

---

## Learning Outcomes

By the end of this project, I was able to:

- Enable and interpret Windows audit logon events
- Write a PowerShell script to parse login data from the Windows Event Log
- Recognize signs of brute-force attacks through log analysis
- Monitor and evaluate login events on a Linux system
- Set up a basic defense mechanism against brute-force login attempts

---

## Tools & Commands Used

- **PowerShell ISE**  
- **Event Viewer** (Windows)  
- **auditpol**, `Get-WinEvent`, `Get-EventLog`  
- **Linux Commands:** `journalctl`, `last`, `grep`, `fail2ban`  
- **Windows Security Event IDs:** 4624 (Successful), 4625 (Failed)

---

## Screenshots
*(Add screenshots of PowerShell script output, Event Viewer logs, and Linux terminal commands)*


