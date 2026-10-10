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

## Talk it out

Tap "Talk it out," then use the mic on your phone keyboard and talk. Say "next" between loops (or put each on its own line). You check everything on a review screen before anything is added.

- **Sort it (no AI)** splits on "next" and picks up a few phrases: times ("quick," "10 minutes," "half an hour," "takes forever"), energy ("when I'm tired," "need to be fresh"), "today," and "first step is..."
- **AI extract** sends the text to Claude, which splits it, fills in time and energy, and writes a tiny first step for each loop.
- **Quick sort** (shows up when loops are missing time or energy) goes one loop at a time. "Let AI fill all" fills them all in for review.
- **Suggest** (in a loop's editor, Quick sort, and Focus) asks Claude for a first step.

The AI features need a Claude API key (Data > Settings). Like the GitHub token, it's saved only in that browser. It's never in a backup or synced, so you add it on each device. Only the text you send with AI goes to Anthropic.
