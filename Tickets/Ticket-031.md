# Ticket-031: Azure Storage Account Access from VM Failed

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-031 |
| Priority | Medium |
| Service | Azure Storage Account |
| Category | Network Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that an application running on an Azure VM could not access an Azure Storage Account.

The application was returning a network connection error.

---

## What I Checked

I confirmed that the VM and Storage Account were available.

I then checked the Storage Account networking configuration and found that public network access was restricted and the VM was not coming from an allowed network.

---

## Troubleshooting

- Confirmed the VM was running.
- Checked the Storage Account status.
- Reviewed Storage Account network settings.
- Verified the VM's Virtual Network and subnet.
- Found that the required network access was not allowed.
- Updated the Storage Account network configuration.

---

## Root Cause

The Storage Account network configuration was blocking access from the VM's network.

---

## Resolution

Updated the Storage Account network settings to allow access from the required Virtual Network.

---

## Verification

- Retested the connection from the VM.
- Confirmed the application could access the Storage Account.
- Verified that the required storage operation completed successfully.
- Checked the application logs for further connection errors.

---

## What I Learned

- Storage Account networking can restrict access even when the resource itself is healthy.
- Virtual Network access should be checked when an Azure VM cannot reach Storage.
- Network access and identity permissions should be investigated separately.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Storage Account
- Azure Virtual Network
- Azure Portal

---

## Ticket Status

**Resolved**
