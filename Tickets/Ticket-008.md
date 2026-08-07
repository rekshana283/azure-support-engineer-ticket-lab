# Ticket-008: Azure Blob Storage Upload Failed

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-008 |
| Priority | Medium |
| Service | Azure Blob Storage |
| Category | Storage |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were unable to upload files to an Azure Blob Storage container and received an authorization error.

---

## Environment

- Microsoft Azure
- Azure Storage Account
- Azure Blob Storage
- Azure Portal

---

## Investigation

The following checks were performed:

- Verified that the Storage Account was available.
- Confirmed that the target Blob Container existed.
- Checked the user's Microsoft Entra ID account.
- Reviewed the user's Azure RBAC role assignments.
- Identified that the user did not have permission to upload data to the container.

---

## Root Cause Analysis

The user had insufficient data-plane permissions on the Azure Blob Storage account. The assigned role allowed access to the storage resource but did not provide permission to upload blob data.

---

## Resolution

Assigned the **Storage Blob Data Contributor** role to the user at the appropriate storage account scope.

---

## Verification

- Confirmed that the role assignment was applied successfully.
- Retested the file upload operation.
- Verified that the file was successfully uploaded to the Blob Container.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Azure resource permissions and data access permissions can be different.
- Review RBAC role assignments when troubleshooting Blob Storage authorization issues.
- Follow the principle of least privilege when assigning storage permissions.

---

## Azure Services Used

- Azure Storage Account
- Azure Blob Storage
- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)

---

## Ticket Status

**Resolved**
