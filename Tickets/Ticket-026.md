# Ticket-026: Azure App Service Configuration Change Not Taking Effect

## Ticket Information

| Field | Details |
|--------|---------|
| Ticket ID | ASL-026 |
| Priority | Medium |
| Service | Azure App Service |
| Category | Configuration |
| Status | Resolved |

---

## Customer Issue

The customer reported that a configuration value was changed in their Azure App Service, but the application was still using the previous value.

---

## What I Checked

I verified the App Service configuration and confirmed that the new value had been saved.

I then checked the application behavior and found that the application had not reloaded the updated configuration.

---

## Troubleshooting

- Checked the App Service configuration settings.
- Confirmed the new value was saved correctly.
- Reviewed the application logs.
- Restarted the App Service to reload the configuration.
- Tested the application again.

---

## Root Cause

The configuration change had been saved, but the application had not reloaded the updated setting.

---

## Resolution

Restarted the App Service so that the application could load the updated configuration.

---

## Verification

- Confirmed the new configuration value was being used.
- Tested the affected application function.
- Checked the application logs.
- Confirmed the application was working normally.

---

## What I Learned

- App Service configuration changes may require the application to restart or reload.
- Always verify the application's actual behavior after changing configuration.
- Application logs can help confirm whether the updated settings are being loaded.

---

## Azure Services Used

- Azure App Service
- Azure Portal
- Application Logs

---

## Ticket Status

**Resolved**
