# Ticket-028: Azure Blob Storage File Not Found

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-028 |
| Priority | Medium |
| Service | Azure Blob Storage |
| Category | Storage / Application |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application was unable to retrieve a file from an Azure Blob Storage container.

The application returned a "Blob Not Found" error.

---

## What I Checked

I checked the Storage Account and confirmed that the container was available.

I then verified the blob name and path used by the application and found that the application was requesting an incorrect blob path.

---

## Troubleshooting

- Confirmed the Storage Account was available.
- Checked the target container.
- Verified that the required blob existed.
- Compared the blob name with the path used by the application.
- Corrected the application configuration with the correct blob path.

---

## Root Cause

The application was using an incorrect blob name/path, so the requested file could not be found.

---

## Resolution

Updated the application configuration to use the correct blob path.

---

## Verification

- Retried the file request.
- Confirmed that the blob was retrieved successfully.
- Verified that the application displayed the file correctly.
- Checked the application logs for further errors.

---

## What I Learned

- A "Blob Not Found" error does not always mean the file was deleted.
- Blob names and paths should be checked carefully when troubleshooting storage access.
- Application configuration should be verified when the expected blob exists but cannot be retrieved.

---

## Azure Services Used

- Azure Storage Account
- Azure Blob Storage
- Azure Portal

---

## Ticket Status

**Resolved**
