# Ticket-012: Azure Storage Account Access from Application Failed

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-012 |
| Priority | High |
| Service | Azure Storage Account |
| Category | Application Access |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application hosted on Azure App Service was unable to upload files to an Azure Storage Account.

The application returned an authorization error when attempting to write files to Blob Storage.

---

## Environment

- Microsoft Azure
- Azure App Service
- Azure Storage Account
- Azure Blob Storage
- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)

---

## Investigation

The following checks were performed:

- Verified that the Storage Account was available.
- Confirmed that the Blob Container existed.
- Verified that the App Service application was running.
- Reviewed the application's identity configuration.
- Checked Azure RBAC role assignments on the Storage Account.
- Confirmed that the application identity did not have permission to write blob data.

---

## Root Cause Analysis

The App Service application was using a managed identity to access the Storage Account, but the identity did not have the required data-plane permissions on the Blob Storage resource.

---

## Resolution

Assigned the **Storage Blob Data Contributor** role to the App Service managed identity at the appropriate Storage Account scope.

No storage account keys or connection strings were exposed or added to the application configuration.

---

## Verification

- Confirmed that the RBAC role assignment was applied successfully.
- Retested the application file upload operation.
- Verified that the file was successfully uploaded to the Blob Container.
- Confirmed that the application continued to operate normally.

---

## Lessons Learned

- Applications should use managed identities when supported instead of storing credentials in application code.
- Azure RBAC permissions should be reviewed when applications receive authorization errors.
- Resource access permissions and data access permissions should be considered separately.
- Follow the principle of least privilege when assigning roles.

---

## Azure Services Used

- Azure App Service
- Azure Storage Account
- Azure Blob Storage
- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)

---

## Ticket Status

**Resolved**
