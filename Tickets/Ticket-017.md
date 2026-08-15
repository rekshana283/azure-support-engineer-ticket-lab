# Ticket-017: Azure VM Unable to Connect via RDP

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-017 |
| Priority | High |
| Service | Azure Virtual Machine |
| Category | Remote Access / Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that they were unable to connect to their Azure Windows Virtual Machine using Remote Desktop (RDP).

The VM was running normally, but the RDP connection was failing with a connection timeout.

---

## What I Checked

I first checked the VM status in the Azure Portal and confirmed that the VM was running.

Since the VM itself was available, I checked the network configuration next.

I reviewed the Network Security Group (NSG) attached to the VM and checked whether the required RDP traffic was allowed.

The inbound rules showed that TCP port 3389 was not allowed for the required source.

---

## Troubleshooting

### 1. Checked VM Status

- Confirmed the VM was in the Running state.
- Checked the VM for any obvious deployment or platform errors.
- Confirmed that the network interface was attached correctly.

### 2. Checked NSG Rules

- Opened the Network Security Group associated with the VM.
- Reviewed the inbound security rules.
- Found that the required RDP traffic on TCP port 3389 was being blocked.

### 3. Updated Network Access

Added an inbound rule to allow TCP port 3389 from the required source.

I avoided allowing RDP access from the entire internet and kept the rule restricted to the required source.

---

## Root Cause

The VM was running normally, but the Network Security Group was blocking inbound RDP traffic on TCP port 3389.

Because the RDP traffic was blocked at the network level, the remote desktop connection was timing out.

---

## Resolution

Updated the NSG inbound rules to allow the required RDP traffic on TCP port 3389.

The access was restricted to the required source instead of opening RDP access to the entire internet.

---

## Verification

After updating the NSG rule:

1. Retried the RDP connection.
2. Confirmed that the connection reached the VM.
3. Successfully logged in using Remote Desktop.
4. Verified that the VM and its applications were working normally.

The RDP connectivity issue was resolved.

---

## What I Learned

- A VM being in the Running state does not always mean it is reachable.
- NSG rules should be checked when RDP connectivity fails.
- TCP 3389 is the default port used for Windows RDP.
- RDP access should be restricted to trusted sources whenever possible.
- Troubleshooting network issues layer by layer helps identify the actual cause faster.

---

## Azure Services Used

- Azure Virtual Machine
- Network Security Group
- Azure Portal
- Remote Desktop (RDP)

---

## Ticket Status

**Resolved**
