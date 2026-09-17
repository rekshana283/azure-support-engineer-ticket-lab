# Ticket-050: Azure Budget Alert Not Triggering

## Issue
The team expected an Azure budget alert when monthly spending reached the configured threshold, but no notification was received.

## Investigation
- Checked the budget configuration in Cost Management.
- Confirmed that the budget was active.
- Reviewed the configured alert threshold.
- Found that the notification was configured for a higher percentage than the expected spending level.
- Checked the notification recipients and confirmed they were configured correctly.

## Root Cause
The budget alert threshold was configured higher than the level the team expected to be notified at.

## Resolution
Updated the budget notification threshold to the required percentage and saved the configuration.

## Verification
- Confirmed the updated budget alert was active.
- Reviewed the notification configuration.
- Verified that the alert would trigger when the configured threshold was reached.

## Status
Resolved
