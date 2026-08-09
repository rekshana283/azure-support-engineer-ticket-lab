# KB-001: Azure Virtual Machine Connectivity Troubleshooting

## Overview

This knowledge base article provides a structured troubleshooting approach for Azure Virtual Machines that cannot be accessed through Remote Desktop Protocol (RDP) or other network connections.

---

## Common Symptoms

A user may experience one or more of the following symptoms:

- Unable to connect to the Azure Virtual Machine.
- RDP connection fails.
- Connection request times out.
- Website hosted on the VM is unreachable.
- Network connectivity between Azure resources is unavailable.

---

## Troubleshooting Checklist

### 1. Check Virtual Machine Status

Verify that the Azure Virtual Machine is in the **Running** state.

If the VM is stopped or deallocated, start the VM and test the connection again.

---

### 2. Verify Public IP Address

For connections from the internet, verify that the Virtual Machine has the correct Public IP address.

Confirm that the user is connecting to the correct IP address or DNS name.

---

### 3. Check Network Security Group Rules

Review the Network Security Group (NSG) associated with the VM's network interface or subnet.

Verify that the required inbound traffic is allowed.

For Windows Remote Desktop, the default RDP port is:

**TCP 3389**

For a web application, commonly used ports include:

- HTTP: TCP 80
- HTTPS: TCP 443

Only required ports should be allowed.

---

### 4. Check Operating System Firewall

If the NSG configuration is correct, verify the firewall settings inside the Virtual Machine.

Ensure that the required application or service is allowed through the operating system firewall.

---

### 5. Verify the Required Service

Check whether the required service is running inside the Virtual Machine.

For RDP connectivity, verify that the Remote Desktop service is available.

For web applications, verify that the web server service is running.

---

### 6. Check Network Configuration

Review the following Azure networking components:

- Virtual Network (VNet)
- Subnet
- Network Interface
- Network Security Group
- Public IP Address
- Route configuration

Confirm that the resources are configured correctly.

---

## Root Cause Examples

Common causes of Azure VM connectivity problems include:

- VM is stopped or deallocated.
- Incorrect Public IP address.
- NSG blocking required traffic.
- Operating system firewall blocking traffic.
- Required service is not running.
- Incorrect network configuration.
- Incorrect routing configuration.

---

## Resolution Approach

Follow these steps in order:

1. Verify the VM status.
2. Verify the Public IP address.
3. Check NSG inbound rules.
4. Check the operating system firewall.
5. Verify the required service.
6. Review VNet and subnet configuration.
7. Test connectivity again.
8. Document the root cause and resolution.

---

## Security Best Practices

- Allow only required ports.
- Avoid opening unnecessary ports to the internet.
- Restrict administrative access to trusted source IP addresses where possible.
- Follow the principle of least privilege.
- Review NSG rules regularly.
- Use secure protocols such as HTTPS whenever applicable.

---

## Verification

After applying a configuration change:

- Test the connection again.
- Confirm that the required application or service is accessible.
- Verify that no unnecessary ports were opened.
- Confirm that the customer can access the required resource.

---

## Conclusion

Azure Virtual Machine connectivity issues should be investigated systematically rather than changing multiple configurations at once.

Checking the VM status, Public IP, NSG rules, operating system firewall, services, and network configuration helps isolate the root cause and resolve connectivity problems efficiently.

---

## Related Support Tickets

- Ticket-001: Unable to Connect to Azure Virtual Machine
- Ticket-007: Network Security Group Blocking Web Traffic
- Ticket-010: Azure Virtual Network Connectivity Issue
