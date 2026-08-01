# Ticket-001: Unable to Connect to Azure Virtual Machine

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-001 |
| Priority | High |
| Service | Azure Virtual Machine |
| Category | Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were unable to connect to their Azure Virtual Machine using Remote Desktop Protocol (RDP).

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Windows Server
- Remote Desktop (RDP)

---

## Investigation

The following checks were performed:

- Verified that the virtual machine was running.
- Checked whether a Public IP address was assigned.
- Reviewed the Network Security Group (NSG) inbound rules.
- Confirmed that TCP port 3389 was blocked.

---

## Root Cause Analysis

The Network Security Group (NSG) did not allow inbound traffic on TCP port 3389, preventing Remote Desktop connections.

---

## Resolution

Created an inbound NSG rule to allow TCP port 3389 from the required source IP address.

---

## Verification

- Successfully connected to the virtual machine using Remote Desktop.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Always verify NSG inbound rules when troubleshooting VM connectivity.
- Ensure only required ports are opened.
- Follow the principle of least privilege to maintain security.

---

## Azure Services Used

- Azure Virtual Machine
- Network Security Group (NSG)
- Public IP Address

---

## Ticket Status

**Resolved**
