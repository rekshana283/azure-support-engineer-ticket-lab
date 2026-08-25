# Ticket-025: Azure VM High CPU Usage

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-025 |
| Priority | High |
| Service | Azure Virtual Machine |
| Category | Performance |
| Status | Resolved |

---

## Customer Issue

The customer reported that an application running on an Azure VM had become slow and was taking longer than usual to respond.

---

## What I Checked

I checked the VM status and confirmed that it was running normally.

I then reviewed the CPU usage and found that it was consistently high.

I checked the processes running inside the VM and identified an application process consuming a large amount of CPU.

---

## Troubleshooting

- Confirmed the VM was running.
- Reviewed CPU usage through Azure Monitor.
- Checked the processes inside the VM.
- Identified the process causing high CPU usage.
- Restarted the affected application service.
- Monitored CPU usage after the restart.

---

## Root Cause

An application process was consuming excessive CPU resources, which was affecting the VM's overall performance.

---

## Resolution

Restarted the affected application service and monitored the VM.

CPU usage returned to a normal level and the application became responsive again.

---

## Verification

- Confirmed CPU usage returned to normal.
- Tested the application.
- Verified that response times improved.
- Monitored the VM for further CPU spikes.

---

## What I Learned

- High CPU usage can directly affect application performance.
- Azure Monitor can help identify VM resource usage.
- Checking processes inside the VM helps identify the actual source of high CPU consumption.
- Resource monitoring can help detect performance issues before they affect users.

---

## Azure Services Used

- Azure Virtual Machine
- Azure Monitor
- Azure Portal

---

## Ticket Status

**Resolved**
