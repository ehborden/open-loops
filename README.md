# Open Loops

A task tracker for getting open loops out of your head, picking one, and doing it.

Live at: https://ehborden.github.io/open-loops/

## Where the data lives

- Each browser keeps its own copy (localStorage).
- With sync on, the Work and Home lists are also saved as `work.json` and `home.json` in the private repo `open-loops-data`. Every device that is connected sees the same lists.
- The access token is stored only in each browser. It is never in this repo or in a backup file.
- Data > Backup downloads both lists as one file. Data > Restore loads one back.
- With sync on, the app also saves a backup to the `backups` folder in `open-loops-data` about once a week and keeps the last 12. Data > Restore from GitHub lists them by date. With weekly backups running, the backup reminder stays away.

## Connecting a device

1. Open the site (on iPhone, add it to the Home Screen first and open it from the icon).
2. Tap "Sync off" at the top.
3. Enter your GitHub username, `open-loops-data`, and your access token.

## Talk it out

Tap "Talk it out," then use the mic on your phone keyboard and talk. Say "next" between loops (or put each on its own line). You check everything on a review screen before anything is added.

- **Sort it (no AI)** splits on "next" and picks up a few phrases: times ("quick," "10 minutes," "half an hour," "takes forever"), energy ("when I'm tired," "need to be fresh"), "today," and "first step is..."
- **AI extract** sends the text to Claude, which splits it, fills in time and energy, and writes a tiny first step for each loop.
- **Quick sort** (shows up when loops are missing time or energy) goes one loop at a time. "Let AI fill all" fills them all in for review.
- **Steps:** say "steps" and put "then" between them ("plan the unit, steps, find last year's doc, then pick the readings"). Both Sort it and AI extract keep your steps.
- **Break it down** (in a loop's editor and in Focus) asks Claude for 3 to 5 small steps, which you check before they're used.

## Steps, Start, and Focus

- Each loop can have a checklist of steps. The list shows the next one; tap the arrow to see them all. Tap a box to check a step off. Checking off the last one asks if you want to close the loop.
- Tap a loop's name to edit it: name, steps, time, energy, and Pick for today. Not today and Let it go are under More.
- Start begins a timer right away. Focus opens on top of whatever screen you were on, with a Step done button. Back to list keeps the timer going in a bar at the bottom; tap the bar to return.

The AI features (AI extract, AI fill, Break it down) need a Claude API key (Data > Settings). Like the GitHub token, it's saved only in that browser. It's never in a backup or synced, so you add it on each device. Only the text you send with AI goes to Anthropic.
