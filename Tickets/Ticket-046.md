# Ticket-046: Azure App Service Slot Swap Caused Application Issue

## Issue
After swapping an App Service staging slot with production, users reported that the application was not working as expected.

## Investigation
- Confirmed both staging and production slots were running.
- Checked the application settings in both slots.
- Compared the slot-specific configuration values.
- Found that a production-specific application setting was not marked as a deployment slot setting.
- During the swap, the value was moved to production incorrectly.

## Root Cause
A production-specific application setting was not configured as a deployment slot setting.

## Resolution
Marked the setting as a deployment slot setting and corrected the production value.

## Verification
- Rechecked the application settings after the correction.
- Tested the application in production.
- Confirmed the application was working normally after the configuration change.

## Status
Resolved
