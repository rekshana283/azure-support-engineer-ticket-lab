# Ticket-007: Network Security Group (NSG) Blocking Web Traffic

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-007 |
| Priority | High |
| Service | Azure Networking |
| Category | Network Security |
| Status | Resolved |

---

## Customer Issue

The customer reported that users were unable to access their web application hosted on an Azure Virtual Machine.

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Virtual Network (VNet)
- Network Security Group (NSG)

---

## Investigation

The following checks were performed:

- Verified that the virtual machine was running.
- Confirmed that the web server service was active.
- Checked the Public IP address.
- Reviewed the Network Security Group (NSG) inbound rules.
- Identified that inbound HTTP (TCP port 80) traffic was blocked.

---

## Root Cause Analysis

The Network Security Group (NSG) did not have an inbound rule allowing HTTP traffic on TCP port 80.

---

## Resolution

Created an inbound NSG rule to allow HTTP (TCP port 80) traffic from the Internet to the virtual machine.

---

## Verification

- Verified that the NSG rule was successfully applied.
- Confirmed that the website was accessible through the public IP address.
- Customer confirmed that the issue was resolved.

---

## Lessons Learned

- Verify NSG rules before troubleshooting application issues.
- Allow only the required ports based on application requirements.
- Periodically review NSG configurations to maintain security.

---

## Azure Services Used

- Azure Virtual Machine
- Virtual Network (VNet)
- Network Security Group (NSG)

---

## Ticket Status

**Resolved**
