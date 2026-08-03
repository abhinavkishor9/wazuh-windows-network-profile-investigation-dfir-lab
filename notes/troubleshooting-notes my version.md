# Troubleshooting Notes

## Issue 1 — No NetworkProfile Events Found

### Cause

In Event Viewer, you may not have refreshed Operational log after changing the network profile.

### Resolution

Refresh Event Viewer and verify the **Microsoft-Windows-NetworkProfile/Operational** log.

---

## Issue 2 — Network Profile Did Not Change

### Cause

The network profile may not have been applied.

### Resolution

Verify the current profile using:

```powershell
Get-NetConnectionProfile
```

---

## Issue 3 — No Results in Wazuh Discover

### Cause

Search filters or indexing delays may prevent events from appearing immediately.

### Resolution

Confirm the event exists on the Windows endpoint before troubleshooting Wazuh.

---

## Issue 4 — Wazuh Agent Health

### Cause

Potential communication interruption between the endpoint and Wazuh Manager.

### Resolution

Verify agent status using:

```bash
sudo /var/ossec/bin/agent_control -i 001
```

