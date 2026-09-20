# PB-001: Azure VM Network Connectivity Troubleshooting

## Purpose

Use this playbook when an Azure VM cannot be reached through RDP, SSH, or another required network connection.

## Common Symptoms

- RDP or SSH connection fails.
- VM is running but unreachable.
- One VM cannot communicate with another VM.
- Application port is not responding.

## Troubleshooting Steps

### Step 1: Check VM Status

Open the Azure portal and confirm that the VM is in the Running state.

If the VM is stopped or has a platform issue, resolve that before continuing.

### Step 2: Confirm Network Details

Check the VM's:

- Virtual Network
- Subnet
- Network Interface
- Private IP
- Public IP, if required

Make sure the connection is being attempted using the correct address.

### Step 3: Review NSG Rules

Check the Network Security Group associated with the VM subnet or NIC.

Verify that the required port is allowed for the correct source.

Examples:

- RDP → TCP 3389
- SSH → TCP 22
- Application → Application-specific port

Also check rule priorities because a higher-priority deny rule can override an allow rule.

### Step 4: Check Operating System Firewall

If the NSG configuration looks correct, check the firewall inside the VM.

Confirm that the required port is allowed and that the application/service is listening on that port.

### Step 5: Test the Application or Service

If the VM is reachable but the application is not responding, check whether the required service is running.

Test the service locally from the VM where possible.

### Step 6: Check VM-to-VM Connectivity

For internal communication, confirm that both VMs are using the expected VNet/subnet configuration.

Review NSG rules on both the source and destination sides.

### Step 7: Retest Connectivity

After making the required change:

- Retry the connection.
- Confirm the required port is reachable.
- Verify that the application or remote service responds normally.

## Common Root Causes

- NSG blocking the required port.
- Higher-priority deny rule.
- Incorrect IP address.
- Operating system firewall blocking traffic.
- Required service not running.
- Incorrect VNet or subnet configuration.

## Security Checks

Do not allow unrestricted access unless required.

Where possible:

- Restrict source IP ranges.
- Allow only required ports.
- Avoid exposing management ports publicly.
- Remove temporary troubleshooting rules after testing.

## Verification Checklist

- [ ] VM is running
- [ ] Correct IP address confirmed
- [ ] VNet and subnet verified
- [ ] NSG rules checked
- [ ] Rule priorities checked
- [ ] OS firewall checked
- [ ] Required service running
- [ ] Connectivity tested successfully

## Related Tickets

- Ticket-017: Azure VM Unable to Connect via RDP
- Ticket-027: Azure VM Network Connectivity Lost
- Ticket-036: Azure VM Cannot Reach Another VM

## Related KB

- KB-001: Azure Virtual Machine Connectivity Troubleshooting
