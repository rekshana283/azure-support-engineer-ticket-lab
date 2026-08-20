# Ticket-021: Azure App Service Application Returns 503 Error

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-021 |
| Priority | High |
| Service | Azure App Service |
| Category | Application Availability |
| Status | Resolved |

---

## Customer Issue

The customer reported that their website hosted on Azure App Service was returning a **503 Service Unavailable** error.

The issue started after a recent application deployment.

---

## What I Checked

I first checked the App Service status and confirmed that the service was running.

I then reviewed the application logs and deployment history. The latest deployment had completed, but the application was not starting correctly.

---

## Troubleshooting

- Confirmed the App Service was running.
- Checked the application logs.
- Reviewed the latest deployment.
- Found errors during application startup.
- Rolled back to the previously working application version.

---

## Root Cause

The latest application deployment contained a startup configuration issue, which prevented the application from starting correctly.

---

## Resolution

Rolled back the application to the previous working version.

The application started normally after the rollback.

---

## Verification

- Opened the application URL.
- Confirmed the 503 error was no longer displayed.
- Verified that the application pages were loading normally.
- Checked the application logs for new startup errors.

---

## What I Learned

- A running App Service can still return 503 errors if the application itself fails to start.
- Application logs are useful when investigating App Service availability issues.
- Deployment history helps identify whether a recent deployment caused the problem.
- Rolling back to a known working version can quickly restore application availability.

---

## Azure Services Used

- Azure App Service
- Azure Portal
- Application Logs

---

## Ticket Status

**Resolved**
