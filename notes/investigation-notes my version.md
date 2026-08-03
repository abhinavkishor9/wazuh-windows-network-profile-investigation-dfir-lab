# Investigation Notes

## Lab Summary

In this investigation, we analyzed Windows Network Profile changes using  NetworkProfile Operational logs and Wazuh Discover.


---

## Analyst Methodology


1. Verify Wazuh agent is active or not.
2. Check the active network profile.
3. Change the network profile from Public to Private
4. Analyze NetworkProfile Operational logs in Event Viewer.
5. Validate changes using PowerShell.
6. Search Wazuh Discover.

---

## Investigation Scenario

A Windows workstation changed its network profile from **Private** to **Public**.

As a DFIR analyst, we need to investigate:

- Whether Windows generated NetworkProfile events.
- Whether profile change occurred successfully.
- Whether Wazuh collected the activity.

---

## Evidence Collected

### Evidence 1 – Network Profile

Collected:

- Active network profile

Finding:

This established the baseline.

---

### Evidence 2 – Event Viewer

Collected:

- NetworkProfile Operational events
- Event IDs including 10002, 10000, 4004

Finding:

Main source for network profile investigation.

---

### Evidence 3 – PowerShell Validation

Command Used

```powershell
Get-NetConnectionProfile
```

Finding:

Verified the profile transitioned from Private to Public.

---

### Evidence 4 – Wazuh Discover

Collected:

- Endpoint activity
- Agent logs

Finding:

Validated successful endpoint communication and SIEM visibility.

---

## DFIR Analysis

The investigation showed that Windows NetworkProfile Operational logs provide evidence for identifying any change in network profile, correlated with Event Viewer and Wazuh Discover.



---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | System Network Configuration Discovery | T1016 |
| Discovery | System Information Discovery | T1082 |

---


