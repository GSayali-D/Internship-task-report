# Internship-task-report
Day 3
Vulnerability Assessment Report

Tool Used: Nessus (Tenable)
Date: June 26, 2025


---

🔷 1. Executive Summary

This report presents the results of a vulnerability scan performed on a simulated internal enterprise network using the Nessus Vulnerability Scanner. The purpose of the assessment was to identify potential security risks, evaluate system configurations, and recommend remediation steps


Scan Type: Full and Fast Scan

Scope: 3 hosts (internal IP range)

Findings Summary:

🔴 Critical: 3

🔶 High: 9

🟠 Medium: 17

🟡 Low: 13

⚪ Info: 6




---

🔷 2. Scanned Hosts

Host IP	Operating System	Open Ports

10.0.0.5	Windows Server 2016	445, 3389, 135
10.0.0.10	Ubuntu 20.04	22, 80, 443
10.0.0.15	CentOS 7	22, 25, 3306



---

🔷 3. Vulnerability Overview

IP Address	Critical	High	Medium	Low	Total

10.0.0.5	2	5	7	4	18
10.0.0.10	1	2	5	4	12
10.0.0.15	0	2	5	5	12



---

🔷 4. Top Findings

IP Address	Vulnerability Title	CVE ID	Severity	Port	Plugin ID

10.0.0.5	SMBv1 Enabled	CVE-2017-0144	Critical	445/tcp	100000
10.0.0.10	Apache Path Traversal	CVE-2021-41773	High	80/tcp	112200
10.0.0.5	Remote Desktop Protocol (RDP) Weak Encryption	N/A	High	3389/tcp	104500
10.0.0.15	MySQL Anonymous Access	CVE-2012-2122	Medium	3306/tcp	120000



---

🔷 5. Sample Vulnerability Detail

Vulnerability: SMBv1 Protocol Detection
Host: 10.0.0.5
Port: 445/tcp
Severity: 🔴 Critical
CVE: CVE-2017-0144
Plugin ID: 100000
Description:
The target host supports the obsolete and insecure SMBv1 protocol, which is vulnerable to multiple remote code execution exploits including EternalBlue.
Risk Impact: Unauthorized attackers can exploit this to gain full control.
Remediation: Disable SMBv1 via system configuration. Apply Microsoft patch KB4012598.


---

🔷 6. Risk Distribution

Severity	Count	Percentage

Critical	3	11%
High	9	32%
Medium	17	40%
Low	13	17%



---

🔷 7. Remediation Plan

Severity	Action	Timeframe

Critical	Immediate patching and service shutdown	0–3 days
High	Patch/update or harden within 7 days	4–7 days
Medium	Fix during next maintenance cycle	7–14 days
Low	Optional; fix as resources permit	15+ days



---

🔷 8. Conclusion

This vulnerability scan identified several critical and high-severity weaknesses across all systems. The most urgent issues involve outdated protocols (SMBv1), insecure services (RDP, MySQL), and unpatched web servers. Proper patch management, service hardening, and routine vulnerability assessments are recommended.
