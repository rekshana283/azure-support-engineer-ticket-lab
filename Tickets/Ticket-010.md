# Ticket-010: Azure Virtual Network Connectivity Issue

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-010 |
| Priority | High |
| Service | Azure Virtual Network |
| Category | Network Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that two Azure Virtual Machines located in the same Azure Virtual Network were unable to communicate with each other.

---

## Environment

- Microsoft Azure
- Azure Virtual Network (VNet)
- Azure Virtual Machines
- Network Security Group (NSG)

---

## Investigation

The following checks were performed:

- Verified that both virtual machines were running.
- Confirmed that both virtual machines were connected to the same Virtual Network.
- Checked the subnet configuration of both virtual machines.
- Reviewed the Network Security Group (NSG) rules.
- Verified that the required internal traffic was being blocked by an NSG rule.
- Tested network connectivity between the two virtual machines after reviewing the configuration.

---

## Root Cause Analysis

An NSG rule was blocking the required inbound traffic between the two virtual machines, preventing network communication within the Virtual Network.

---

## Resolution

Updated the Network Security Group configuration to allow the required internal traffic between the virtual machines while restricting unnecessary network access.

---

## Verification

- Verified that the NSG rule was applied successfully.
- Tested connectivity between both virtual machines.
- Confirmed that the virtual machines could communicate successfully.
- Customer confirmed that the connectivity issue was resolved.

---

## Lessons Learned

- Verify Virtual Network and subnet configuration when troubleshooting connectivity issues.
- Review NSG rules carefully before making network changes.
- Allow only the required traffic to maintain network security.
- Test connectivity after making configuration changes.

---

## Azure Services Used

- Azure Virtual Network (VNet)
- Azure Virtual Machines
- Network Security Group (NSG)

---

## Ticket Status

**Resolved**
