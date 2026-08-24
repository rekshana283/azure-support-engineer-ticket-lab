# Ticket-024: Azure Virtual Network DNS Resolution Issue

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-024 |
| Priority | Medium |
| Service | Azure Virtual Network |
| Category | Network / DNS |
| Status | Resolved |

---

## Customer Issue

The customer reported that a VM in Azure could connect to some resources but was unable to resolve the hostname of another internal service.

The application was failing because the required hostname could not be resolved.

---

## What I Checked

I checked the VM network configuration and confirmed that the VM was connected to the expected Virtual Network and subnet.

I then reviewed the DNS configuration for the Virtual Network and found that the VM was using an incorrect DNS configuration.

---

## Troubleshooting

- Confirmed the VM was running.
- Checked the Virtual Network and subnet configuration.
- Reviewed the DNS settings.
- Verified the DNS server configuration.
- Updated the DNS configuration with the correct DNS server.
- Restarted the required network service and tested name resolution again.

---

## Root Cause

The VM was using an incorrect DNS configuration, so it could not resolve the hostname of the internal service.

---

## Resolution

Updated the Virtual Network DNS configuration to use the required DNS server.

---

## Verification

- Tested hostname resolution from the VM.
- Confirmed the internal service hostname resolved correctly.
- Retested the application connection.
- Confirmed that the application was communicating with the internal service normally.

---

## What I Learned

- DNS problems can appear as application or network connectivity issues.
- Virtual Network DNS settings should be checked when internal hostnames cannot be resolved.
- Testing name resolution from the affected VM helps isolate DNS-related problems.

---

## Azure Services Used

- Azure Virtual Network
- Azure Virtual Machine
- Azure Portal

---

## Ticket Status

**Resolved**
