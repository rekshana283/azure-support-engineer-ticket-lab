# Ticket-048: Azure NSG Rule Priority Blocking Traffic

## Issue
An application running on an Azure VM could not be accessed through the expected network port.

## Investigation
- Confirmed that the VM and application were running.
- Checked the Network Security Group attached to the VM subnet.
- Found an allow rule for the application port.
- Reviewed the rule priorities and found a higher-priority deny rule matching the same traffic.
- Confirmed that the deny rule was taking precedence.

## Root Cause
A higher-priority NSG deny rule was overriding the required allow rule.

## Resolution
Adjusted the NSG rule priorities so that the required allow rule was evaluated before the deny rule.

## Verification
- Retested the application port.
- Confirmed that the required traffic was allowed.
- Verified that unrelated traffic remained blocked.

## Status
Resolved
