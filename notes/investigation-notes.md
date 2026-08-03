# Investigation Notes

## Lab Summary

This investigation focused on analyzing Windows Network Profile changes using native Windows NetworkProfile Operational logs and Wazuh Discover.

The investigation reconstructed profile changes by correlating Event Viewer, PowerShell, and Wazuh evidence.

---

## Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Verify Wazuh agent connectivity.
2. Check the active network profile.
3. Change the network profile.
4. Examine NetworkProfile Operational logs.
5. Validate changes using PowerShell.
6. Search Wazuh Discover.
7. Correlate endpoint evidence.
8. Document findings.

---

## Investigation Scenario

A Windows workstation changed its network profile from **Private** to **Public**.

The investigation aimed to determine:

- Whether Windows generated NetworkProfile events.
- Whether the profile change was successful.
- Whether Wazuh collected the activity.
- Whether endpoint and SIEM evidence matched.

---

## Evidence Collected

### Evidence 1 – Network Profile

Collected:

- Active network profile

Finding:

Established the investigation baseline.

---

### Evidence 2 – Event Viewer

Collected:

- NetworkProfile Operational events
- Event IDs including 10002, 10000, 4004

Finding:

Primary source for network profile investigation.

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

The investigation demonstrated that Windows NetworkProfile Operational logs provide valuable evidence for identifying network profile changes.

PowerShell and Event Viewer confirmed the endpoint state, while Wazuh provided centralized visibility for investigation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | System Network Configuration Discovery | T1016 |
| Discovery | System Information Discovery | T1082 |

---

## Analyst Observations

- Network profile changes generate useful Windows artifacts.
- Event Viewer remains the authoritative Windows source.
- PowerShell quickly validates current network status.
- Wazuh complements endpoint investigations.
- Correlating multiple evidence sources improves investigation confidence.

---

## Conclusion

The investigation demonstrated how Windows Network Profile changes can be investigated using native Windows logging and Wazuh Discover while following a structured DFIR methodology.
