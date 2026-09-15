# Ticket-045: Azure Private Endpoint DNS Resolution Failed

## Issue
An application running inside an Azure VNet could not connect to a Storage Account through its Private Endpoint.

## Investigation
- Confirmed the Private Endpoint was provisioned successfully.
- Checked the VNet and subnet configuration.
- Tested DNS resolution from the application VM.
- Found that the Storage Account hostname was resolving to a public IP instead of the Private Endpoint IP.
- Reviewed the Private DNS Zone configuration.

## Root Cause
The Private DNS Zone was not correctly linked to the application VNet.

## Resolution
Linked the Private DNS Zone to the required VNet and verified the DNS record for the Private Endpoint.

## Verification
- Tested DNS resolution from the VM.
- Confirmed the hostname resolved to the private IP address.
- Retested the application connection to the Storage Account successfully.

## Status
Resolved
