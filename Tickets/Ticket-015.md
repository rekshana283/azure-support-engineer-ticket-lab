# Ticket-015: Azure SQL Database Connection Failure

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-015 |
| Priority | High |
| Service | Azure SQL Database |
| Category | Database Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application was unable to connect to an Azure SQL Database. The application was returning a connection timeout error.

---

## Environment

- Microsoft Azure
- Azure SQL Database
- Azure App Service
- Azure Portal
- Microsoft Entra ID

---

## Investigation

The following checks were performed:

- Verified that the Azure SQL Database was available.
- Confirmed that the application was running.
- Reviewed the application's database connection configuration.
- Checked the Azure SQL Database firewall rules.
- Verified whether the application was allowed to connect to the database.
- Identified that the required client IP address was not allowed by the Azure SQL Database firewall configuration.

---

## Root Cause Analysis

The Azure SQL Database firewall configuration was blocking the connection from the application's source network.

---

## Resolution

Updated the Azure SQL Database firewall configuration to allow the required source network while avoiding unnecessary broad access.

---

## Verification

- Retested the application database connection.
- Confirmed that the application successfully connected to the Azure SQL Database.
- Verified that database operations were functioning normally.
- Customer confirmed that the application was working as expected.

---

## Lessons Learned

- Check Azure SQL firewall rules when troubleshooting database connectivity.
- Avoid allowing unrestricted access when configuring database firewall rules.
- Verify the application's source network before modifying firewall settings.
- Use secure authentication methods and least-privilege access wherever possible.

---

## Azure Services Used

- Azure SQL Database
- Azure App Service
- Microsoft Entra ID

---

## Ticket Status

**Resolved**
