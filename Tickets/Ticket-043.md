# Ticket-043: Azure VM Run Command Failed

## Issue
A support engineer was unable to execute a troubleshooting command on an Azure VM using Run Command.

## Investigation
- Confirmed the VM was running and reachable from the Azure portal.
- Checked the VM Agent status.
- Found that the Azure VM Agent was not responding correctly.
- Reviewed the extension and agent status for errors.
- Restarted the VM Agent and retried the command.

## Root Cause
The Azure VM Agent was not responding correctly, preventing Run Command from executing.

## Resolution
Restarted the VM Agent and waited for its status to return to Ready before running the command again.

## Verification
- Confirmed the VM Agent was reporting Ready.
- Executed the Run Command successfully.
- Verified that the command output was returned correctly.

## Status
Resolved
