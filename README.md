🛡️ SOC Home Lab: Threat Detection & Analysis with Splunk & Sysmon
📌 Project Overview

This project demonstrates the creation of a SOC Home Lab environment designed to simulate a real-world cyberattack and perform threat detection and analysis using Sysmon and Splunk SIEM.

The primary objective is to gain hands-on experience in threat detection engineering, endpoint telemetry collection, log analysis, and adversary activity mapping within a controlled and isolated environment.

🎯 Objectives

Simulate a realistic attack scenario

Collect detailed endpoint telemetry using Sysmon

Centralize and analyze logs with Splunk SIEM

Detect malicious activity and extract Indicators of Compromise (IoCs)

Practice blue-team detection and investigation workflows

🧰 Technical Stack
Virtualization

Hypervisor: Oracle VirtualBox

Operating Systems

Victim Machine: Windows 10

Attacker Machine: Kali Linux

Security & Monitoring Tools

Splunk Enterprise

Sysmon (System Monitor)

Attack Tools

Metasploit Framework

msfvenom

msfconsole

🏗️ Lab Architecture & Workflow
1️⃣ Environment Setup

Provisioned an isolated NAT network (10.0.2.0/24)

Ensured malware execution occurs safely without exposing the host system or external network

2️⃣ Telemetry Configuration

Installed and configured Sysmon on the Windows 10 victim machine

Enabled advanced event logging for:

Process creation

File creation

Network connections

Forwarded Sysmon logs to a centralized Splunk instance for analysis

3️⃣ Adversary Simulation

Generated a custom reverse shell payload (Resume.pdf.exe) on Kali Linux using msfvenom

Hosted the payload via a Python HTTP server

Executed the payload on the victim machine

Successfully established a Command & Control (C2) connection

4️⃣ Log Analysis & Detection

Used Splunk Search Processing Language (SPL) to hunt for suspicious activity

Investigated:

Malicious process execution

File creation events

Download sources and file hashes

🔍 Key Results & Evidence

This lab highlights the visibility gap filled by Sysmon and Splunk in endpoint detection:

✅ Process Identification

Detected the malicious process Resume.pdf.exe running in system memory

✅ Log Correlation

Captured Sysmon Event ID 15 (FileCreateStreamHash)

Extracted:

Original download source URL

Unique file hashes (MD5 / SHA256) for forensic analysis

📈 Skills Demonstrated

SOC analyst workflow

Endpoint telemetry collection

SIEM log ingestion and querying

Threat hunting using SPL

Malware execution tracing

Digital forensics fundamentals

🚀 Future Improvements (Optional)

Add detection rules and alerts in Splunk

Map activity to MITRE ATT&CK

Include screenshots of Splunk dashboards

Simulate additional attack techniques (lateral movement, persistence)
