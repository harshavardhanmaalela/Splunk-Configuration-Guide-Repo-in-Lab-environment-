# Splunk-Configuration-Guide-Repo-in-Lab-environment-

Splunk-Setup-Guide
Comprehensive step-by-step tutorial for deploying Splunk Enterprise (v10.0.2) on Ubuntu, with Universal Forwarders on Windows Server 2022 and Windows 11 Pro, including AD domain setup and log monitoring.

This repo documents a full Splunk lab environment for SOC analysts, covering installation, configuration, forwarding, and monitoring Windows security events (e.g., logons 4624/4625, user creation 4720).

Key Features
Splunk Enterprise install on Ubuntu (extract tgz, move to /opt, start with license accept).

Windows Server 2022: AD DS domain setup (rajubhai.com), static IP config, firewall rule for port 9997.

Windows 11 Pro: Domain join, static IP with server DNS, forwarder deployment.

Forwarders configured to send logs (Application/Security/System, AD monitoring) to Enterprise at port 9997.

Verified log ingestion: Hosts "harxha" (server), "vardhan" (Win11); events like logins, failures, brute-force sims.

Table of Contents
Section	Description
Splunk Enterprise Setup	Ubuntu download, extract, /opt install, web UI config (http://localhost:8000). 
Receiving Port	Configure port 9997 in Splunk UI for forwarders. 
Windows Server Prep	AD DS install, promote to DC, IP/static config (192.168.169.133). 
Forwarder Install	MSI deploy, local system account, logs/AD monitor, indexer to Ubuntu IP:9997. 
Log Monitoring	Search examples for 4624 (success), 4625 (fail), 4720 (user create), file events. 
Usage
Clone repo: git clone https://github.com/yourusername/Splunk-Setup-Guide.git

Follow PDF screenshots/commands for lab replication.

Customize IPs/domains for your env; test with brute-force sims or user creates.

Extend for SOC: Add SPL queries for alerts (e.g., index=main EventCode=4625 | stats count by src_ip). 

Tech Stack
OS: Ubuntu, Win Server 2022, Win 11 Pro

Tools: Splunk Enterprise 10.0.2, Universal Forwarder 10.0.2

Monitored: WinEventLog:Security, file changes, AD events
