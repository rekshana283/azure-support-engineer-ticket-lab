# Ticket-004: User Unable to Sign in to Azure Portal

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-004 |
| Priority | High |
| Service | Microsoft Entra ID |
| Category | Authentication |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were unable to sign in to the Azure portal using their organizational account.

---

## Environment

- Microsoft Azure
- Microsoft Entra ID
- Azure Portal

---

## Investigation

The following checks were performed:

- Verified that the username was correct.
- Confirmed that the user account was active.
- Reviewed Microsoft Entra ID sign-in logs.
- Checked whether Multi-Factor Authentication (MFA) was required.

---

## Root Cause Analysis

The user had not completed the required Multi-Factor Authentication (MFA) verification, preventing successful sign-in.

---

## Resolution

Guided the user through the MFA verification process and confirmed that authentication was completed successfully.

---

## Verification

- Verified that the user successfully signed in to the Azure portal.
- Confirmed that Azure resources were accessible.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Review sign-in logs before troubleshooting authentication issues.
- Verify Microsoft Entra ID account status.
- Ensure users complete MFA registration and verification.

---

## Azure Services Used

- Microsoft Entra ID
- Azure Portal
- Multi-Factor Authentication (MFA)

---

## Ticket Status

**Resolved**
