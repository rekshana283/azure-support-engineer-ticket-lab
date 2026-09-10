# Ticket-040: Azure VM Backup Failed

## Issue
The scheduled backup for an Azure VM failed, and the latest recovery point was not created.

## Investigation
- Checked the VM status and confirmed the VM was running.
- Reviewed the Recovery Services vault backup jobs.
- Found that the backup job had failed during the snapshot operation.
- Checked the VM disk configuration and found that one disk had recently been changed.
- The backup configuration had not been updated to include the new disk.

## Root Cause
The newly attached VM disk was not included in the existing backup configuration.

## Resolution
Updated the backup configuration to include the required disk and triggered a backup manually.

## Verification
- Confirmed the backup job completed successfully.
- Verified that a new recovery point was created.
- Confirmed the required VM disks were included in the backup.

## Status
Resolved
