# PB-005: Azure Identity and Access Troubleshooting

## Purpose

Use this playbook when an application, user, or Azure resource cannot access another Azure resource because of an authentication or authorization issue.

## Common Symptoms

- Access denied error.
- Application cannot read a secret.
- Application cannot access a Storage Account.
- User can see a resource but cannot perform an operation.
- Managed Identity authentication fails.

## Troubleshooting Steps

### Step 1: Identify the Identity

Determine which identity is making the request:

- User account
- Service Principal
- Managed Identity

Confirm that the expected identity is being used.

### Step 2: Check Authentication

Confirm that the identity is enabled and authentication is working correctly.

For Managed Identity, verify that it is enabled on the required Azure resource.

### Step 3: Review RBAC Permissions

Check the role assignments for the identity.

Confirm that the assigned role provides the required permissions for the requested operation.

### Step 4: Check Scope

Verify where the role is assigned:

- Management Group
- Subscription
- Resource Group
- Individual Resource

Make sure the permission is assigned at the appropriate scope.

### Step 5: Check Resource-Specific Access

Some Azure services have additional access controls.

Review service-specific permissions such as:

- Key Vault access
- Storage data permissions
- SQL database permissions

### Step 6: Correct the Permission

Assign the required role or permission at the appropriate scope.

Avoid granting broader access than necessary.

### Step 7: Retest Access

Retry the original operation and confirm that the identity can now access the required resource.

## Common Root Causes

- Required RBAC role missing.
- Incorrect role assigned.
- Role assigned at the wrong scope.
- Managed Identity disabled.
- Resource-specific permission missing.
- Network restrictions combined with an access issue.

## Security Best Practices

- Follow the principle of least privilege.
- Grant only the permissions required for the task.
- Prefer Managed Identity where appropriate.
- Review unused role assignments regularly.
- Avoid giving broad Owner or Contributor access when a narrower role is sufficient.

## Verification Checklist

- [ ] Correct identity identified
- [ ] Authentication checked
- [ ] Required role verified
- [ ] Scope checked
- [ ] Resource-specific permissions checked
- [ ] Required permission granted
- [ ] Original operation retested
- [ ] Access confirmed

## Related Tickets

- Ticket-018: Azure Storage Account Access Denied
- Ticket-023: Azure Storage Blob Upload Failed
- Ticket-035: Azure Key Vault Access Denied
- Ticket-032: Azure App Service Environment Variable Missing

## Related KB

- KB-001: Azure Virtual Machine Connectivity Troubleshooting
