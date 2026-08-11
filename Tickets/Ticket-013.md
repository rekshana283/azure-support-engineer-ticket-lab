# Ticket-013: Azure Monitor Alert Not Triggering

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-013 |
| Priority | Medium |
| Service | Azure Monitor |
| Category | Monitoring & Alerts |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were not receiving alerts when CPU utilization on their Azure Virtual Machine exceeded the expected threshold.

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Azure Monitor
- Azure Monitor Alert Rule

---

## Investigation

The following checks were performed:

- Verified that the virtual machine was running.
- Reviewed CPU utilization metrics in Azure Monitor.
- Confirmed that CPU utilization had exceeded the expected threshold.
- Reviewed the configured Azure Monitor alert rule.
- Checked the alert condition and evaluation period.
- Verified the configured action group and notification settings.
- Identified that the alert rule threshold was configured higher than the customer's expected limit.

---

## Root Cause Analysis

The Azure Monitor alert rule was configured with an incorrect CPU threshold. As a result, the alert condition was not triggered when CPU utilization reached the customer's expected limit.

---

## Resolution

Updated the Azure Monitor alert rule with the correct CPU utilization threshold and verified that the appropriate Action Group was configured for notifications.

---

## Verification

- Generated CPU activity on the virtual machine.
- Verified that the configured threshold was reached.
- Confirmed that the Azure Monitor alert was triggered.
- Verified that the notification was delivered through the configured Action Group.

---

## Lessons Learned

- Review alert thresholds regularly to ensure they match operational requirements.
- Verify both alert conditions and Action Group configuration when troubleshooting notification issues.
- Monitor critical resources with appropriate alerts.
- Avoid setting thresholds too high or too low without considering normal resource usage patterns.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Monitor
- Azure Monitor Alerts
- Action Groups

---

## Ticket Status

**Resolved**
