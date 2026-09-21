# PB-003: Azure App Service and Azure SQL Connectivity Troubleshooting

## Purpose

Use this playbook when an Azure App Service cannot connect to an Azure SQL Database or database operations are failing.

## Common Symptoms

- Application cannot connect to Azure SQL.
- Database connection timeout occurs.
- Application returns database-related errors.
- Application starts but database operations fail.

## Troubleshooting Steps

### Step 1: Check Service Status

Confirm that both the App Service and Azure SQL Database are running and available.

### Step 2: Check Database Connection Settings

Review the application's database connection configuration.

Verify:

- SQL Server name
- Database name
- Authentication method
- Required application settings

### Step 3: Check SQL Network Access

Review the Azure SQL Server networking configuration.

Confirm that the required application traffic is allowed and that firewall or network restrictions are not blocking the connection.

### Step 4: Check Managed Identity

If the application uses Managed Identity, confirm that the identity is enabled and has the required database permissions.

### Step 5: Review Application Logs

Check App Service logs for:

- Connection timeout
- Authentication failure
- Network errors
- Invalid connection configuration

### Step 6: Test the Connection

After correcting the identified issue, test the application connection to the database.

### Step 7: Verify Application

Confirm that database-dependent application features are working normally.

## Common Root Causes

- SQL firewall restrictions.
- Incorrect connection settings.
- Missing database permissions.
- Managed Identity configuration issues.
- Incorrect server or database name.
- Network access restrictions.

## Security Checks

- Avoid exposing the database unnecessarily.
- Allow only required network access.
- Use Managed Identity where appropriate.
- Do not store database credentials directly in application code.
- Review access permissions regularly.

## Verification Checklist

- [ ] App Service status checked
- [ ] SQL Database status checked
- [ ] Connection settings verified
- [ ] SQL network access checked
- [ ] Managed Identity checked
- [ ] Application logs reviewed
- [ ] Database connection tested
- [ ] Application functionality verified

## Related Tickets

- Ticket-016: Azure App Service Cannot Connect to Azure SQL Database
- Ticket-022: Azure SQL Database Connection Timeout
- Ticket-032: Azure App Service Environment Variable Missing

## Related KB

- KB-001: Azure Virtual Machine Connectivity Troubleshooting
