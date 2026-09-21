# PB-004: Azure Monitoring and Alert Troubleshooting

## Purpose

Use this playbook when an Azure Monitor alert is not triggering, is triggering unexpectedly, or is not sending the expected notification.

## Common Symptoms

- Expected alert was not triggered.
- Alert triggered at an unexpected time.
- Notification was not received.
- Resource metrics show abnormal activity but no alert was generated.

## Troubleshooting Steps

### Step 1: Check Resource Metrics

Open Azure Monitor and review the relevant metric for the affected resource.

Confirm that the metric actually reached the expected condition.

### Step 2: Review Alert Rule

Check:

- Target resource
- Metric
- Condition
- Threshold
- Evaluation frequency
- Time window

Make sure the rule matches the expected monitoring requirement.

### Step 3: Check Alert Status

Confirm that the alert rule is enabled and review its current state.

Check previous alert instances for additional details.

### Step 4: Check Action Group

If the alert triggered but no notification was received, review the associated Action Group.

Verify that the configured notification method and recipient are correct.

### Step 5: Review Activity and Alert History

Check alert history and Activity Log entries around the reported time.

Use the timestamps to compare the resource event with the alert evaluation.

### Step 6: Correct the Configuration

If the threshold, target, condition, or notification configuration is incorrect, update the alert rule and save the changes.

### Step 7: Verify

Monitor the resource and confirm that the alert behaves as expected when the configured condition is reached.

## Common Root Causes

- Threshold configured incorrectly.
- Wrong resource or metric selected.
- Alert rule disabled.
- Evaluation period does not match the expected condition.
- Action Group configuration issue.
- Notification recipient configured incorrectly.

## Best Practices

- Set thresholds based on expected resource behavior.
- Avoid unnecessary alert noise.
- Keep notification recipients up to date.
- Review alert rules after major resource changes.
- Regularly test important monitoring and notification rules.

## Verification Checklist

- [ ] Correct resource selected
- [ ] Metric verified
- [ ] Threshold checked
- [ ] Evaluation period checked
- [ ] Alert rule enabled
- [ ] Action Group checked
- [ ] Alert history reviewed
- [ ] Notification configuration verified
- [ ] Alert behavior tested

## Related Tickets

- Ticket-034: Azure Monitor Alert Not Triggering
- Ticket-047: Azure VM Availability Alert Triggered
- Ticket-050: Azure Budget Alert Not Triggering

## Related KB

- KB-002: Azure Virtual Machine Low Disk Space Troubleshooting
