# Ticket-022: Azure SQL Database Connection Timeout

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-022 |
| Priority | High |
| Service | Azure SQL Database |
| Category | Database Connectivity |
| Status | Resolved |

---

## Customer Issue

The customer reported that their application was unable to connect to the Azure SQL Database.

The application was running, but database requests were failing with a connection timeout.

---

## What I Checked

I checked the SQL Database and confirmed that it was available.

I then reviewed the server firewall rules and found that the application's source IP address was not allowed.

---

## Troubleshooting

- Confirmed the SQL Database was available.
- Checked the application connection settings.
- Reviewed the SQL server firewall rules.
- Identified that the required source IP was not allowed.
- Added the required IP address to the firewall rules.

---

## Root Cause

The Azure SQL Database firewall was blocking the application's connection because the required source IP address was not allowed.

---

## Resolution

Updated the SQL server firewall configuration to allow the required source IP address.

Only the required access was allowed instead of opening the database to all networks.

---

## Verification

- Retried the database connection.
- Confirmed the application could connect successfully.
- Verified that database-dependent pages were loading.
- Checked the application logs for further connection errors.

---

## What I Learned

- SQL Database firewall rules can prevent applications from connecting even when the database is healthy.
- Checking network access should be part of database connectivity troubleshooting.
- Firewall access should be limited to required sources.

---

## Azure Services Used

- Azure SQL Database
- Azure Portal
- SQL Server Firewall

---

## Ticket Status

**Resolved**
