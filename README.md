# wazuh-windows-network-profile-investigation-dfir-lab

## Overview

This Digital Forensics and Incident Response (DFIR) lab demonstrates how Windows Network Profile changes can be investigated using native Windows logs and Wazuh Discover.

Unlike Sysmon-based investigations, this lab relies on the Windows **Microsoft-Windows-NetworkProfile/Operational** log, Event Viewer, PowerShell, and Wazuh Discover to reconstruct network profile changes between Private and Public networks.

The investigation also demonstrates how analysts verify endpoint evidence before correlating events within a SIEM.

---

# Executive Summary

This investigation focused on reconstructing Windows network profile changes using native Windows logging and Wazuh.

The investigation included:

- Verifying Wazuh agent connectivity
- Identifying the active network profile
- Changing the network profile from Private to Public
- Investigating NetworkProfile Operational logs
- Validating events using PowerShell
- Searching Wazuh Discover
- Correlating endpoint and SIEM evidence

The investigation demonstrates structured DFIR methodology by validating Windows events before relying solely on SIEM data.

---

# Learning Objectives

- Understand Windows Network Profile events.
- Investigate Public and Private network changes.
- Validate network profile events using Event Viewer.
- Verify network profile status using PowerShell.
- Investigate network profile activity using Wazuh Discover.
- Correlate endpoint evidence with SIEM events.
- Reconstruct a network profile change timeline.

---

# Skills Demonstrated

- Windows DFIR Investigation
- Windows NetworkProfile Log Analysis
- Event Viewer Analysis
- PowerShell Investigation
- Wazuh Discover Investigation
- Event Correlation
- Timeline Reconstruction
- Digital Evidence Documentation
- DFIR Troubleshooting
- MITRE ATT&CK Mapping

---

# Tools Used

- Wazuh Dashboard (Discover)
- Windows Event Viewer
- Windows PowerShell
- Microsoft-Windows-NetworkProfile/Operational Log
- Wazuh Agent

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh 4.12 |
| Endpoint | Windows 11 Pro |
| Server | Oracle Linux 9 |
| Investigation Type | Windows DFIR |
| Event Source | NetworkProfile Operational Log |
| Sysmon | Not Used |

---

# Investigation Scenario

A Windows workstation changed its network profile from **Private** to **Public**.

As the DFIR analyst, the objectives were to determine:

- Which network profile was active
- When the profile changed
- Whether Windows generated NetworkProfile events
- Whether Wazuh collected those events
- Whether endpoint and SIEM evidence matched

---

# Investigation Workflow

1. Verify Wazuh agent connectivity.
2. Check the active network profile.
3. Change the network profile.
4. Review NetworkProfile Operational logs.
5. Validate events using PowerShell.
6. Search Wazuh Discover.
7. Correlate endpoint evidence.
8. Document findings.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | System Network Configuration Discovery | T1016 |
| Discovery | System Information Discovery | T1082 |

### Why Network Profile Investigations Matter

Unexpected network profile changes may indicate unauthorized configuration changes, misconfigured systems, or suspicious administrative activity. Correlating endpoint logs with SIEM data helps analysts validate legitimate versus suspicious network configuration changes.

---

# Evidence Collected

- Windows NetworkProfile Operational Log
- Network Profile Events
- Event Viewer
- PowerShell validation
- Wazuh Discover

---

# Evidence Correlation

| Evidence Source | Information Obtained | Investigation Value |
|-----------------|---------------------|--------------------|
| Event Viewer | Network Profile events | Primary evidence |
| PowerShell | Current profile validation | Independent verification |
| Wazuh Discover | Collected events | SIEM validation |

---

# Investigation Findings

- The active network profile was initially Private.
- The profile was successfully changed to Public.
- Windows generated NetworkProfile Operational events.
- PowerShell confirmed the updated profile.
- Wazuh Discover collected related endpoint activity.
- Endpoint evidence and SIEM findings were successfully correlated.

---

# Key Takeaways

- Network profile changes leave valuable forensic artifacts.
- Event Viewer and PowerShell complement each other during investigations.
- Endpoint validation should precede SIEM analysis.
- Wazuh Discover enables efficient correlation of Windows events.
- Multiple evidence sources strengthen DFIR investigations.

---
