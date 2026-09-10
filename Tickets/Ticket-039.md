# Ticket-039: Azure App Service Slow Response

## Issue
Users reported that an application hosted on Azure App Service was taking longer than usual to respond.

## Investigation
- Checked the App Service availability and confirmed it was running.
- Reviewed CPU and memory metrics in Azure Monitor.
- Found that memory usage had increased significantly during the reported period.
- Checked recent application activity and confirmed increased workload.
- No deployment or configuration changes were found.

## Root Cause
The App Service was experiencing high memory usage due to increased application workload.

## Resolution
Restarted the App Service to clear the temporary resource pressure and monitored the application after the restart.

## Verification
- Response time returned to normal.
- Memory usage decreased to the expected level.
- Continued monitoring to confirm the issue did not immediately return.

## Status
Resolved
