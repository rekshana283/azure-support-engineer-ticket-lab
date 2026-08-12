# Ticket-014: Azure Virtual Machine Unable to Reach Internet

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-014 |
| Priority | High |
| Service | Azure Virtual Network |
| Category | Network Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that an Azure Virtual Machine could not access external websites or connect to required internet-based services.

---

## Environment

- Microsoft Azure
- Azure Virtual Machine
- Azure Virtual Network (VNet)
- Subnet
- Network Security Group (NSG)
- Route Table

---

## Investigation

The following checks were performed:

- Verified that the virtual machine was running.
- Confirmed that the network interface was connected to the correct subnet.
- Reviewed the Network Security Group (NSG) rules.
- Confirmed that outbound internet traffic was allowed by the NSG.
- Reviewed the subnet route table.
- Identified that the subnet was associated with a custom route table containing an incorrect default route.

---

## Root Cause Analysis

The subnet had a custom route table with an incorrect default route for internet-bound traffic. This caused outbound traffic from the virtual machine to be directed incorrectly, preventing internet connectivity.

---

## Resolution

Corrected the route table configuration and removed the incorrect default route so that internet-bound traffic could use the appropriate Azure network path.

---

## Verification

- Tested outbound connectivity from the virtual machine.
- Confirmed that external websites and required internet services were reachable.
- Verified that the updated route table was being applied to the subnet.
- Customer confirmed that internet connectivity was restored.

---

## Lessons Learned

- Review NSG rules and route tables when troubleshooting outbound connectivity.
- Understand how custom routes can affect traffic flow.
- Avoid unnecessary custom routing configurations.
- Test network connectivity after making routing changes.

---

## Azure Services Used

- Azure Virtual Network (VNet)
- Azure Virtual Machine
- Subnet
- Network Security Group (NSG)
- Route Table

---

## Ticket Status

**Resolved**
