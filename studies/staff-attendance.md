# Staff Attendance and Staff Portal

**Status:** deployed and tested in the Salesforce sandbox · **Built with:** Apex, Lightning Web Components, Visualforce site, scheduled jobs

[← All case studies](../README.md)

## The problem

Staff attendance lived on paper and in spreadsheets. Many staff have no Salesforce login, so they had no way to record their own days, and corrections had no approval trail.

## What it does

- **My Attendance:** staff with a Salesforce login check in and out from an app inside Salesforce.
- **Staff Portal website:** staff without a login sign in with a code sent to their email.
- **Location checks:** on office days, check-in needs a location within the office radius.
- **Corrections:** staff ask for a correction with a reason, and an admin approves it. Saved days are locked outside these screens.
- **Attendance Admin:** a records search, settings, an Emails tab with a test-or-live switch, and CSV export with staff IDs.
- **Automation:** reminders, a Friday summary, a Monday follow-up, a nightly catch-up, and public holidays added automatically each year.

## How it is built

- Apex services handle the portal, its sign-in, catch-up, summaries, records search, weekly email, reminders, sharing and guarded writes.
- Triggers stop saved attendance and corrections being edited outside the approved screens.
- Lightning Web Components serve staff and admins. A Visualforce site serves staff without logins.
- Custom objects hold attendance, corrections, portal sessions, public holidays and an admin log. Custom metadata holds the settings.
- A runbook and checked deploy manifests ship with it.

## Where it stands

The full system is merged and tested in the sandbox, with its staff guide written. Going live is the next step.
