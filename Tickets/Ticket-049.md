# Ticket-049: Azure Resource Deletion Blocked

## Issue
A resource administrator was unable to delete an Azure resource even though they had the required permissions.

## Investigation
- Confirmed the administrator had sufficient RBAC permissions.
- Checked the resource status and configuration.
- Reviewed the resource group for management locks.
- Found a Delete lock applied to the resource.
- Confirmed that the lock was preventing the deletion operation.

## Root Cause
A Delete resource lock was applied to the resource.

## Resolution
Removed the Delete lock after confirming that the resource was approved for removal.

## Verification
- Retried the deletion operation.
- Confirmed the resource was deleted successfully.
- Verified that no unintended resources were affected.

## Status
Resolved
