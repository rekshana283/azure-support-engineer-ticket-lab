# Ticket-009: Azure RBAC Access Denied

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-009 |
| Priority | High |
| Service | Azure Role-Based Access Control (RBAC) |
| Category | Authorization |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were unable to view and manage a specific Azure resource even though they had access to the Azure portal.

---

## Environment

- Microsoft Azure
- Azure Portal
- Azure Role-Based Access Control (RBAC)
- Azure Virtual Machine

---

## Investigation

The following checks were performed:

- Verified that the user could successfully sign in to the Azure portal.
- Confirmed that the Azure resource was available.
- Reviewed the user's RBAC role assignments.
- Checked the scope at which the roles were assigned.
- Identified that the user did not have sufficient permissions at the required resource scope.

---

## Root Cause Analysis

The user had successfully authenticated to Azure but did not have the required authorization to access the specific resource.

The assigned RBAC role was applied at an incorrect scope and did not provide the required permissions for the target resource.

---

## Resolution

Assigned the appropriate RBAC role to the user at the required resource scope while following the principle of least privilege.

---

## Verification

- Confirmed that the new role assignment was applied successfully.
- Verified that the user could access the required Azure resource.
- Confirmed that the user could perform only the actions permitted by the assigned role.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Authentication and authorization are different processes.
- Always verify both the assigned RBAC role and its scope.
- Grant only the minimum permissions required.
- Review role assignments regularly to reduce unnecessary access.

---

## Azure Services Used

- Azure Role-Based Access Control (RBAC)
- Azure Portal
- Azure Virtual Machine

---

## Ticket Status

**Resolved**
