# Ticket-002: Unable to Access Azure Storage Account

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-002 |
| Priority | Medium |
| Service | Azure Storage Account |
| Category | Access Issue |
| Status | Resolved |

---

## Customer Issue

The customer reported receiving an "Access Denied" error while trying to access files stored in an Azure Storage Account.

---

## Environment

- Microsoft Azure
- Azure Storage Account
- Blob Storage

---

## Investigation

The following checks were performed:

- Verified that the Storage Account was available.
- Reviewed the user's assigned permissions.
- Checked Azure Role-Based Access Control (RBAC).
- Confirmed that the user did not have the required Storage Blob Data Reader role.

---

## Root Cause Analysis

The user did not have sufficient RBAC permissions to access the Blob Storage resources.

---

## Resolution

Assigned the **Storage Blob Data Reader** role to the user through Azure Role-Based Access Control (RBAC).

---

## Verification

- Confirmed that the new role assignment was applied successfully.
- Verified that the user was able to access the required blob files.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Always verify RBAC role assignments when users report access issues.
- Grant only the minimum permissions required to follow the principle of least privilege.
- Review role assignments before troubleshooting storage service failures.

---

## Azure Services Used

- Azure Storage Account
- Azure Blob Storage
- Azure Role-Based Access Control (RBAC)

---

## Ticket Status

**Resolved**
