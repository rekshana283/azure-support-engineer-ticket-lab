# Ticket-033: Azure Load Balancer Backend Server Unhealthy

## Issue
Users were unable to access an application through the Azure Load Balancer. The backend VM was running, but the Load Balancer was not sending traffic to it.

## Investigation
- Checked the Azure VM status and confirmed the VM was running.
- Checked the Load Balancer backend pool and found the VM was marked as unhealthy.
- Reviewed the health probe configuration.
- The probe was configured to check the wrong port, so the application was not responding to the probe.

## Root Cause
The Load Balancer health probe was configured with an incorrect port.

## Resolution
Updated the health probe to use the port on which the application was actually listening.

After the change, the backend VM became healthy and traffic started reaching the application again.

## Verification
- Confirmed the backend VM status changed to healthy.
- Tested the application through the Load Balancer public IP.
- Verified that requests were successfully reaching the backend VM.

## Status
Resolved
