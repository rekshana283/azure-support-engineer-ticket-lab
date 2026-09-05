# Ticket-034: Azure Monitor Alert Not Triggering

## Issue
The team expected an alert when the Azure VM CPU usage increased, but no alert notification was received.

## Investigation
- Checked the VM CPU metrics in Azure Monitor and confirmed that CPU usage had crossed the expected level.
- Reviewed the alert rule configuration.
- Found that the alert threshold was configured higher than the level being monitored.
- Checked the action group and confirmed the notification configuration was working.

## Root Cause
The alert rule threshold was set too high, so the actual CPU usage did not meet the configured alert condition.

## Resolution
Updated the alert threshold to the required value and saved the alert rule.

## Verification
- Confirmed the updated alert rule was enabled.
- Monitored the VM CPU metric.
- Verified that the alert was triggered when the configured threshold was reached.

## Status
Resolved
