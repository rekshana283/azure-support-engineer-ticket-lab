# Ticket-030: Azure VM Extension Failed

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-030 |
| Priority | Medium |
| Service | Azure Virtual Machine |
| Category | VM Configuration |
| Status | Resolved |

---

## Customer Issue

The customer reported that an Azure VM extension deployment had failed.

The extension was required to run a configuration task on the VM.

---

## What I Checked

I checked the VM status and confirmed that the VM was running normally.

I then reviewed the VM extension status and deployment details. The extension had failed during installation because the VM agent was not responding correctly.

---

## Troubleshooting

- Confirmed the VM was running.
- Checked the VM Agent status.
- Reviewed the extension deployment error.
- Restarted the VM Agent service.
- Retried the extension deployment.

---

## Root Cause

The Azure VM Agent was not responding correctly, which caused the VM extension installation to fail.

---

## Resolution

Restarted the VM Agent service and redeployed the required VM extension.

---

## Verification

- Confirmed the VM Agent was responding.
- Verified the extension deployment completed successfully.
- Checked the extension status in the Azure Portal.
- Confirmed the required configuration task completed.

---

## What I Learned

- VM extensions depend on the Azure VM Agent.
- Extension deployment errors should be investigated from the VM Agent and extension status.
- Checking the deployment error before retrying helps avoid repeated failures.

---

## Azure Services Used

- Azure Virtual Machine
- Azure VM Extensions
- Azure Portal

---

## Ticket Status

**Resolved**
