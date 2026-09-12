# Ticket-041: Azure Application Gateway Returns 502 Error

## Issue
Users received a 502 Bad Gateway error when accessing the application through Azure Application Gateway.

## Investigation
- Confirmed the Application Gateway was running.
- Checked the backend pool and found the backend VM was marked unhealthy.
- Reviewed the health probe configuration.
- Found that the probe was checking the wrong backend port.
- Tested the application directly on the VM and confirmed it was running normally.

## Root Cause
The Application Gateway health probe was configured with an incorrect backend port.

## Resolution
Updated the health probe to use the correct application port.

## Verification
- Confirmed the backend VM changed to a healthy state.
- Tested the application through the Application Gateway.
- Verified that the 502 error was no longer occurring.

## Status
Resolved
