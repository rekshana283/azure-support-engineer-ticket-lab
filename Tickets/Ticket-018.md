# Ticket-018: Azure Storage Account Access Denied

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-018 |
| Priority | Medium |
| Service | Azure Storage Account |
| Category | Access / Permissions |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application was unable to upload files to an Azure Blob Storage container.

The application was returning an "Access Denied" error during the upload.

---

## What I Checked

I checked the Storage Account and confirmed that the service was available.

Next, I checked how the application was accessing the Storage Account. The application was using a managed identity.

I reviewed the Azure RBAC permissions assigned to the identity and found that it did not have permission to write blob data.

---

## Troubleshooting

- Confirmed the Storage Account was available.
- Checked the target Blob container.
- Verified that the application managed identity was enabled.
- Reviewed the RBAC role assignments.
- Found that the required **Storage Blob Data Contributor** role was missing.

---

## Root Cause

The application's managed identity did not have sufficient permission to upload data to the Blob Storage container.

---

## Resolution

Assigned the **Storage Blob Data Contributor** role to the application's managed identity at the required scope.

---

## Verification

- Retried the file upload.
- Confirmed the upload completed successfully.
- Verified that the blob appeared in the container.
- Checked the application logs and confirmed the access error was resolved.

---

## What I Learned

- Azure resource access and data access are not always the same.
- Managed identities can be used to securely access Azure resources.
- Azure RBAC controls permissions for accessing Azure data.
- Permissions should be given only at the required scope.

---

## Azure Services Used

- Azure Storage Account
- Azure Blob Storage
- Azure RBAC
- Managed Identity

---

## Ticket Status

**Resolved**
