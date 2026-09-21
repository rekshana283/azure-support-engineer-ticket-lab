# PB-002: Azure VM Disk Space and Performance Troubleshooting

## Purpose

Use this playbook when an Azure VM has low disk space, high CPU or memory usage, or reduced application performance.

## Common Symptoms

- Disk space is running low.
- Application is responding slowly.
- CPU usage is unusually high.
- Memory usage is high.
- Application or system services become unstable.

## Troubleshooting Steps

### Step 1: Check VM Status

Confirm that the VM is running and does not have an active platform issue.

### Step 2: Check Resource Metrics

Open Azure Monitor and review:

- CPU usage
- Memory usage
- Disk usage
- Disk I/O

Compare the metrics with the time when the issue was reported.

### Step 3: Check Disk Space

Inside the VM, identify which disk or partition is running low.

Look for:

- Temporary files
- Application logs
- Old backups
- Unnecessary files

Do not remove files without confirming that they are safe to delete.

### Step 4: Check Running Processes

If CPU or memory usage is high, identify the process consuming the resources.

Check whether the process belongs to an expected application or service.

### Step 5: Review Application Logs

Check application and system logs for repeated errors, excessive logging, or unusual activity that could explain the resource increase.

### Step 6: Take Corrective Action

Depending on the cause:

- Remove unnecessary files.
- Rotate or clean up old logs.
- Restart an affected service if appropriate.
- Investigate abnormal processes.
- Increase disk capacity when required.

### Step 7: Monitor After the Change

Continue monitoring CPU, memory, disk space, and application performance after the corrective action.

## Common Root Causes

- Large application or system logs.
- Temporary files accumulating.
- Application process consuming excessive CPU.
- Memory-intensive workload.
- Insufficient disk capacity.
- Unexpected increase in application workload.

## Security and Maintenance Checks

- Do not delete unknown system files.
- Keep required application logs for troubleshooting.
- Use monitoring alerts for important resource thresholds.
- Review disk and resource usage regularly.

## Verification Checklist

- [ ] VM is running
- [ ] CPU usage checked
- [ ] Memory usage checked
- [ ] Disk space checked
- [ ] Large files reviewed
- [ ] Application logs reviewed
- [ ] Corrective action completed
- [ ] Resource usage returned to expected levels
- [ ] Application tested successfully

## Related Tickets

- Ticket-020: Azure VM Disk Space Running Low
- Ticket-025: Azure VM High CPU Usage
- Ticket-039: Azure App Service Slow Response
- Ticket-047: Azure VM Availability Alert Triggered

## Related KB

- KB-002: Azure Virtual Machine Low Disk Space Troubleshooting
