# Open Loops

A task tracker for getting open loops out of your head, picking one, and doing it.

Live at: https://ehborden.github.io/open-loops/

## Where the data lives

- Each browser keeps its own copy (localStorage).
- With sync on, the Work and Home lists are also saved as `work.json` and `home.json` in the private repo `open-loops-data`. Every device that is connected sees the same lists.
- The access token is stored only in each browser. It is never in this repo or in a backup file.
- Data > Backup downloads both lists as one file. Data > Restore loads one back.

## Connecting a device

1. Open the site (on iPhone, add it to the Home Screen first and open it from the icon).
2. Tap "Sync off" at the top.
3. Enter your GitHub username, `open-loops-data`, and your access token.
