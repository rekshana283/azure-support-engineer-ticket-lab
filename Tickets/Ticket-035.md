# Ticket-035: Azure Key Vault Access Denied

## Issue
An application was unable to retrieve a secret from Azure Key Vault and returned an access denied error.

## Investigation
- Confirmed the application was running normally.
- Checked the Key Vault secret and confirmed it existed.
- Verified that the application was using a managed identity.
- Reviewed the Key Vault permissions assigned to the identity.
- Found that the managed identity did not have permission to read secrets.

## Root Cause
The application's managed identity was missing the required Key Vault secret access permission.

## Resolution
Granted the managed identity the required permission to read secrets from the Key Vault.

## Verification
- Restarted the application to refresh the identity access.
- Tested the application again.
- Confirmed that the secret was retrieved successfully.

## Status
Resolved
