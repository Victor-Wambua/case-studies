# Self-refreshing dashboards and desks

Four smaller automations built on one idea: a scheduled agent does the routine work, checks its own data before publishing anything, and leaves the last good version up if any step fails.

[← All case studies](../README.md)

## Self-refreshing IT Desk

**Built with:** Node, Basecamp API, a scheduled AI task

- A read-only dashboard for a help-desk card table in Basecamp.
- On weekdays at 8:00 and 14:00, a scheduled task fetches the board from the Basecamp API, runs 18 checks, rebuilds the page and republishes it.
- If any step fails, it restores the previous snapshot and does not publish. The page shows how fresh its data is, and warns when a run is overdue.
- Sign-in tokens are kept in the macOS Keychain, never in files.

## AI usage tracking

**Built with:** TypeScript, SQLite, Claude Code

- Usage and cost tracking for a ten-person Claude team. The team plan has no usage API, so it combines the admin exports with detailed local records.
- One SQLite database feeds three ways in: a web dashboard, a terminal tool and a Claude Code command.
- A Refresh button on the shared page writes a request. A scheduled agent picks it up, downloads fresh exports, imports them and republishes.
- The page says plainly what each figure covers, and never presents local data as organisation totals.

## Inbox Command Center

**Built with:** Gmail, Google Calendar, AI drafting

- A morning briefing: an action queue of what needs a reply, and a rail of upcoming meetings and deadlines.
- Reply drafts open beside each message for review. Nothing is sent without approval.

## M-Pesa Sorting Desk

**Built with:** SMS parsing, a shared web page, Google Apps Script

- Reads M-Pesa SMS receipts on the Mac and lays them out on a shared desk.
- Each transaction gets a category, a need-or-want tag and a note.
- One go-ahead imports the sorted batch into the Loan Portal's expenses, and duplicates are skipped by transaction code.
