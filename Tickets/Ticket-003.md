# Ticket-003: Azure Virtual Machine Failed to Start

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-003 |
| Priority | High |
| Service | Azure Virtual Machine |
| Category | Compute |
| Status | Resolved |

---

## Customer Issue

The customer reported that their Azure Virtual Machine failed to start after a scheduled maintenance window.

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Windows Server

---

## Investigation

The following checks were performed:

- Verified the virtual machine status in the Azure portal.
- Reviewed Azure Activity Logs for recent operations.
- Checked Boot Diagnostics for startup errors.
- Confirmed that the virtual machine had been stopped (deallocated).

---

## Root Cause Analysis

The virtual machine was in a **Stopped (Deallocated)** state and required a manual start before it could become available.

---

## Resolution

Started the virtual machine from the Azure portal and verified that all services were running successfully.

---

## Verification

- Confirmed that the virtual machine entered the Running state.
- Verified successful Remote Desktop (RDP) connectivity.
- Customer confirmed that applications were accessible.

---

## Lessons Learned

- Verify the VM power state before performing advanced troubleshooting.
- Review Azure Activity Logs to identify recent changes.
- Enable monitoring and alerts for critical virtual machines.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Activity Log
- Boot Diagnostics

---

## Ticket Status

**Resolved**
