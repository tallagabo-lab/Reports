# SOC Incident Report – Ubuntu Server Compromise

## Overview
This report documents a confirmed compromise of the Ubuntu server (`deceptipot-demo`).  The investigation in Splunk (`index=task5`) revealed a full attack lifecycle: SSH brute-force, valid credential access, privilege escalation, persistence via new user creation, reverse shell executionand log tampering.

---
## Log Source
- **SIEM:** Splunk
- **Index:** `task5`
- **Host:** `deceptipot-demo`  - **Logs:** auth.log/sudo logs/syslog/cron
  
---

 ## Investigation Queries

### 1.SSH Brute Force Detection
index=task5 source="auth.log" *ubuntu* process=sshd  
| search "Accepted password" OR "Failed password"

- Used to identify SSH brute-force attempts and authentication activity.

### 2.Failed Login Analysis + Authentication Events
index=task5 source="auth.log" *su*
| sort + _time

-Used to correlate failed attempts, user access, and privilege-related authentication events.

### 3.Privilege Escalation (sudo )
index=task5 source="auth.log"
("sudo" OR "session opened for user root")
| sort _time

-Detects escalation of privileges to root.

### 4.Persistence & Execution via Cron (Command Execution)
index=task5 sourcetype=syslog ("CRON" OR "cron")
| search ("python" OR "perl" OR "ruby" OR ".sh" OR "bash" OR "nc")

-Identifies scheduled task execution and potential malicious scripts (reverse shell / payload execution).

### Summary of Query Logic
-Query 1: SSH brute force + authentication attempts
->> 2: Authentication + sudo-related activity correlation
->> 3: Root privilege escalation detection
->>4: Cron-based persistence and command execution (C2 / reverse shell indicators

-----

## Key Findings

### 1.SSH Brute Force Activity
Source IP: 10.14.94.82
Target user: jack-brown
Multiple failed login attempts detected-4


### 2.Successful Authentication
User: jack-brown / ubuntu
Source IP: 10.14.94.82


### 3.Privilege Escalation
User: jack-brown
Root access via sudo


### 4.Persistence Mechanism
User created: remote-ssh
UID: 1004
Shell: /bin/sh


### 5.Command&Control
IP: 10.10.33.31
Port: 7654
Reverse shell executed via cron job

### Log Tampering
/usr/bin/truncate -s 0 /var/log/syslog

## Timeline 
TimeEvent09:49Log tampering begins (/var/log/syslog truncated)09:50SSH brute-force attempts from 10.14.94.8209:51Successful login (jack-brown)09:52:57User remote-ssh created09:53Additional login observed (ubuntu)10:00Reverse shell executed via cron (10.10.33.31:7654

------

## MITRE ATT&CK Mapping
T1110 – Brute Force
T1078 – Valid Accounts
T1068 – Privilege escalationT1136 – vcreate Account
T1053 – Scheduled Tasks / Cronjobs
T1071 – Command & Control
T1070.002 – Indicator Removal (Log Deletion)
T1021 – Remote Services (SSH)
T1059 – Command Execution

-------

## Conclusion
Conclusion: The Ubuntu server was compromised. The attackers gained initial access through an SSH brute-force attack and then escalated privileges to root. They also created a persistent backdoor by adding a user named “remote-ssh” in order to regain access to the system later. A reverse shell was used for C2 communication.


---
