# wazuh-windows-network-profile-investigation-dfir-lab

## Overview

In this DFIR lab, we investigated Network Profile changes using Windows logs and Wazuh Discover.

This lab uses Windows **Microsoft-Windows-NetworkProfile/Operational** log, Event Viewer, PowerShell, and Wazuh Discover to reconstruct network profile changes between Private and Public networks.


---

# Executive Summary

This investigation focused on reconstructing Windows network profile changes using native Windows logging and Wazuh.

The investigation included the following:

- Verifying whether Wazuh Agent is active
- Identifying the active network profile
- Changing the network profile status from Private to Public
- Investigating NetworkProfile Operational logs
- Validating the events using PowerShell
- Searching in Wazuh Discover


The investigation demonstrates structured DFIR methodology by validating Windows events before relying solely on SIEM data.

---

# Learning Objectives

- Understanding Windows Network Profile events.
- Public and Private network changes.
- Validate network profile events using Event Viewer.
- Validate network profile status using PowerShell.
- Investigate network profile activity using Wazuh Discover.

---

# Tools Used

- Wazuh Dashboard (Discover)
- Event Viewer
- PowerShell
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

---

# Investigation Scenario

A Windows workstation changed its network profile from **Private** to **Public**.

As the DFIR analyst, we had to determine:

- Which network profile was active
- When the profile changed from Public to Private
- Whether NetworkProfileEvents were generated.
- Whether Wazuh collected those events or not.

---

# Investigation Workflow

1. Verify Wazuh agent is active.
2. Check the active network profile.
3. Change network profile from Public to Private
4. Review NetworkProfile Operational logs.
5. Validate events using PowerShell.
6. Search Wazuh Discover.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | System Network Configuration Discovery | T1016 |
| Discovery | System Information Discovery | T1082 |

---

# Evidence Collected

- NetworkProfile Operational Log
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

- The active network profile was initially Private. It was successfully changed to Public.
- Windows generated NetworkProfile Operational events.
- PowerShell confirmed the updated profile.
- Wazuh Discover collected related endpoint activity.


---

