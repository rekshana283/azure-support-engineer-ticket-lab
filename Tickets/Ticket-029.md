# Ticket-029: Azure App Service Health Check Failure

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-029 |
| Priority | High |
| Service | Azure App Service |
| Category | Application Availability |
| Status | Resolved |

---

## Customer Issue

The customer reported that their web application was intermittently unavailable.

The App Service was running, but the application was being marked unhealthy.

---

## What I Checked

I checked the App Service status and reviewed the health check configuration.

The health check was configured to use an incorrect application path, so Azure was receiving an unsuccessful response.

---

## Troubleshooting

- Confirmed the App Service was running.
- Reviewed the Health Check configuration.
- Tested the configured health check path.
- Found that the path did not return a successful response.
- Updated the health check path to the application's correct health endpoint.

---

## Root Cause

The App Service Health Check was using an incorrect URL path, causing the application to be reported as unhealthy.

---

## Resolution

Updated the Health Check configuration with the correct application endpoint.

---

## Verification

- Tested the health check endpoint.
- Confirmed it returned a successful response.
- Monitored the App Service health status.
- Verified that the application was accessible normally.

---

## What I Learned

- An App Service can be running while the application is still reported as unhealthy.
- Health Check configuration should point to a valid application endpoint.
- Checking the health endpoint directly helps identify configuration issues.

---

## Azure Services Used

- Azure App Service
- Azure Portal
- App Service Health Check

---

## Ticket Status

**Resolved**
