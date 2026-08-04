# Ticket-005: Azure Virtual Machine High CPU Usage

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-005 |
| Priority | Medium |
| Service | Azure Virtual Machine |
| Category | Performance |
| Status | Resolved |

---

## Customer Issue

The customer reported that their Azure Virtual Machine was responding slowly, and applications were taking longer than usual to load.

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Windows Server
- Azure Monitor

---

## Investigation

The following checks were performed:

- Verified the virtual machine health status.
- Reviewed CPU utilization using Azure Monitor.
- Checked running processes on the virtual machine.
- Identified a background process consuming excessive CPU resources.

---

## Root Cause Analysis

A background application was continuously consuming high CPU resources, causing poor virtual machine performance.

---

## Resolution

Stopped the unnecessary background process and restarted the affected application. Configured Azure Monitor alerts to notify administrators when CPU utilization exceeds the defined threshold.

---

## Verification

- Confirmed that CPU utilization returned to normal levels.
- Verified that application performance improved.
- Customer confirmed that the virtual machine was functioning normally.

---

## Lessons Learned

- Monitor CPU utilization regularly using Azure Monitor.
- Configure alerts for abnormal resource usage.
- Review running processes before considering infrastructure changes.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Monitor

---

## Ticket Status

**Resolved**
