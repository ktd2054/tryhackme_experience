# 🛡️ TryHackMe: Benign — Walkthrough

<img width="744" height="354" alt="image" src="https://github.com/user-attachments/assets/1bcc040d-9ea0-4eee-8fcc-0a8c803d2e91" />


![Platform](https://img.shields.io/badge/Platform-Splunk-blue)
![Focus](https://img.shields.io/badge/Focus-Blue%20Team%20%2F%20SIEM-red)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

![Room](https://img.shields.io/badge/Room-Benign%20(THM)-purple)
![Tooling](https://img.shields.io/badge/Tooling-SPL%20Queries-informational)
![Skill%20Level](https://img.shields.io/badge/Skill%20Level-SOC%20L1-yellowgreen)
![ATT%26CK](https://img.shields.io/badge/ATT%26CK-Mapping%20Included-important)
![Logs](https://img.shields.io/badge/Logs-Windows%20Event%20Logs%20%7C%20Sysmon-orange)
![Type](https://img.shields.io/badge/Type-Walkthrough%20%2F%20Write--up-brightgreen)


## Introduction 
We will investigate host-centric logs in this challenge room to find suspicious process execution. To learn more about Splunk and how to investigate the logs, look at the rooms splunk101 and splunk201.

### Room Machine

Before moving forward, deploy the machine. When you deploy the machine, it will be assigned an IP. Access this room via the AttackBox, or via the VPN at MACHINE_IP. The machine will take up to 3-5 minutes to start. ll the required logs are ingested in the index win_eventlogs.
