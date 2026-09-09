# Ticket-036: Azure VM Cannot Reach Another VM

## Issue
A VM was unable to communicate with another VM in the same Azure Virtual Network.

## Investigation
- Confirmed both VMs were running and connected to the same VNet.
- Checked the subnet and NIC configuration.
- Reviewed the Network Security Group rules on both VMs.
- Found that the NSG was blocking the required inbound port on the destination VM.
- Tested the connection again after reviewing the effective security rules.

## Root Cause
An NSG rule was blocking the required inbound traffic to the destination VM.

## Resolution
Updated the NSG to allow the required port from the source subnet while keeping the rule restricted to the required network.

## Verification
- Retested connectivity between both VMs.
- Confirmed the required port was reachable.
- Verified that unrelated inbound traffic remained restricted.

## Status
Resolved
