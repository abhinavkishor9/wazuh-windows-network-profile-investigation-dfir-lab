# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 07:30 | Verified Wazuh agent connectivity | agent_control |
| 07:35 | Checked active network profile | PowerShell |
| 07:40 | Changed network profile to Public | Windows Settings |
| 07:43 | Reviewed NetworkProfile Operational log | Event Viewer |
| 07:45 | Validated profile using PowerShell | Get-NetConnectionProfile |
| 07:50 | Investigated Wazuh Discover | Discover |
| 07:55 | Correlated endpoint and SIEM evidence | Documentation |

---

# Investigation Flow

Investigation Started

↓

Verified Agent Health

↓

Checked Current Network Profile

↓

Changed Network Profile

↓

Reviewed Event Viewer

↓

Validated Using PowerShell

↓

Investigated Wazuh Discover

↓

Correlated Evidence

↓

Investigation Completed

---

# Summary

The investigation reconstructed Windows Network Profile changes using native Windows NetworkProfile Operational logs, PowerShell, Event Viewer, and Wazuh Discover. The lab demonstrated structured DFIR methodology by validating endpoint evidence first and then correlating SIEM findings to confirm successful network profile changes.
