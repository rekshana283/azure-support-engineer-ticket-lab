# Ticket-027: Azure VM Network Connectivity Lost

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-027 |
| Priority | High |
| Service | Azure Virtual Machine |
| Category | Network Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that an Azure VM could no longer communicate with another VM in the same Virtual Network.

The affected application was unable to reach an internal service.

---

## What I Checked

I confirmed that both VMs were running and were connected to the expected Virtual Network.

I then reviewed the Network Security Group rules and found that the required internal traffic was being blocked.

---

## Troubleshooting

- Checked the status of both VMs.
- Verified the VNet and subnet configuration.
- Reviewed the NSG rules.
- Identified a rule blocking the required internal traffic.
- Updated the NSG rule.
- Tested connectivity between the VMs again.

---

## Root Cause

An NSG rule was blocking the required network traffic between the two VMs.

---

## Resolution

Updated the NSG configuration to allow the required internal traffic between the VMs.

---

## Verification

- Tested connectivity between both VMs.
- Confirmed the internal service was reachable.
- Retested the affected application.
- Verified that the application was communicating normally.

---

## What I Learned

- NSG rules can affect communication between resources inside the same VNet.
- Internal connectivity issues should be checked at the subnet and NSG level.
- Testing connectivity from the affected VM helps narrow down network problems.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Virtual Network
- Network Security Group
- Azure Portal

---

## Ticket Status

**Resolved**
