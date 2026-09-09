# Ticket-037: Azure Blob Files Not Moving to Cool Tier

## Issue
Older files in an Azure Blob Storage container were expected to move to the Cool access tier automatically, but they were still stored in the Hot tier.

## Investigation
- Checked the affected blobs and confirmed they were still in the Hot tier.
- Reviewed the Storage Account lifecycle management rules.
- Found that the rule was targeting a different container path.
- Checked the blob prefix and confirmed it did not match the configured filter.

## Root Cause
The lifecycle management rule had an incorrect blob path filter, so the affected files were not included.

## Resolution
Updated the rule with the correct container/blob prefix and saved the lifecycle policy.

## Verification
- Confirmed the affected blobs matched the updated rule.
- Reviewed the lifecycle policy configuration.
- Verified that eligible blobs were processed according to the policy.

## Status
Resolved
