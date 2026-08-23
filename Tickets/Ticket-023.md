# Ticket-023: Azure Storage Blob Upload Failed

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-023 |
| Priority | Medium |
| Service | Azure Storage Account |
| Category | Storage / Access |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application was unable to upload files to an Azure Blob Storage container.

The upload operation was failing even though the Storage Account was available.

---

## What I Checked

I checked the Storage Account and confirmed that the service was available.

I then reviewed the application identity and its assigned permissions.

The application was using a managed identity, but the identity did not have the required permission to upload blob data.

---

## Troubleshooting

- Confirmed the Storage Account was available.
- Checked the target Blob container.
- Verified the application managed identity.
- Reviewed the assigned RBAC roles.
- Found that the required Blob Storage data access role was missing.

---

## Root Cause

The application's managed identity did not have sufficient permission to write data to the Blob Storage container.

---

## Resolution

Assigned the **Storage Blob Data Contributor** role to the application identity at the required scope.

---

## Verification

- Retried the file upload.
- Confirmed the upload completed successfully.
- Verified that the file appeared in the Blob container.
- Checked the application logs for further access errors.

The upload functionality was restored.

---

## What I Learned

- Storage Account access and Blob data access are different permission areas.
- Managed identities can provide secure access without storing credentials in application code.
- RBAC permissions should be checked when Blob operations return access errors.
- Access should be granted only at the required scope.

---

## Azure Services Used

- Azure Storage Account
- Azure Blob Storage
- Azure RBAC
- Managed Identity

---

## Ticket Status

**Resolved**
