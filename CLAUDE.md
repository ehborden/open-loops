# Open Loops

A personal task tracker built for ADHD-friendly capture, picking, and focus. The owner uses it daily on a phone, a work computer, and a home computer, with real tasks synced between them. Treat changes as changes to a live app with live data.

## How it is built

- The whole app is `index.html`: plain HTML, CSS, and JavaScript. There is no build step, framework, or package manager. Keep it that way unless the owner asks otherwise.
- Hosted on GitHub Pages from `main`, root folder: https://ehborden.github.io/open-loops/. Pushing to `main` deploys it, so only push when the change is tested.
- `manifest.json` and `icon-*.png` support Add to Home Screen.

## Data (do not break this)

- Local copy: `localStorage` key `openloops_v2`. Shape: `{ app, version: 2, current, lists: { Work: {tasks, deleted}, Home: {tasks, deleted} }, settings, timer }`.
- Sync: each list is a file (`work.json`, `home.json`) in the owner's private repo `open-loops-data`, read and written through the GitHub contents API. The token lives only in `localStorage` key `openloops_sync`.
- Merging is item by item. Every task has `updated` (ms timestamp), and removed tasks leave a record in `deleted` (`{id: ms}`). `save()` stamps these on its own by comparing each list to the last saved version (`stampChanges`). Change task data by editing the objects and then calling `save()`. Never write to `localStorage` directly for task data.
- New task fields must be optional. Old data and other devices running an older version will not have them.
- If the stored shape ever has to change, bump the version and migrate the old key the way `loadState()` migrates `openloops_v1`. Devices update at different times, so the old and new shapes have to work side by side.
- Task ids go into `onclick` attributes. Anything loaded from a file or from GitHub passes through `cleanList` / `cleanTask`, and all user text is escaped with `esc()`. Keep both rules for any new field or source of data.

## Features that must keep working

- Backup downloads both lists as JSON and never includes the token. Restore checks the file, shows its date, and asks before replacing. It still accepts first-version backups (`tasks` + `space`).
- With sync on, `autoBackup()` saves `backups/open loops backup YYYY-MM-DD.json` to the data repo after a full sync (both lists) when the newest one is 7 or more days old, then deletes all but the newest 12. It only lists or deletes files matching that name. Restore from GitHub runs the same `restorePayload()` checks as a file restore.
- Steps: a task may have `steps` ([{id, text, done}], ids validated in `cleanTask` because they go into onclick). `step` is kept as a copy of the next unchecked step so older data and older app copies still work. Read with `getSteps()` and write with `setSteps()`, never `t.steps` or `t.step` directly. `getSteps()` also turns a `step`-only task into a one-step list and picks up a `step` changed by an older app.
- Layout: at 980px and wider, the page is two columns: the current screen on the left, and `#side` on the right with the Focus card (always shown) and a small Wins panel. Below 980px, `#side` sits above the screens and the Focus card only shows while a loop is picked, a timer is running, or after tapping the Focus tab (`body.focus-active`). `goFocus(id, true)` starts the timer. On a phone, the bar at the bottom shows a running timer when the card is scrolled out of view. The header stays visible in both.
- Checked-off steps carry an optional `doneAt` (ms) for "steps checked off today" in Wins.
- Talk it out: `splitLoops` / `parseLoop` are the no-AI sorter ("next" splits loops; "steps ... then ..." splits steps); AI extract, AI fill, and Break it down call the Claude API with the key in `localStorage` key `openloops_ai` (never in backups or sync). Everything goes through the review screen before tasks change.
- Undo reverses only the loops that one action changed (`before` and `after` snapshots), so it never overwrites edits that synced in from another device.
- The focus timer stores an end time, not a countdown, so a refresh does not lose it.

## Testing before you push

Use Playwright with the preinstalled Chromium. Serve the folder over `http://localhost`. Mock `https://api.github.com/**` with `context.route` (a fake store for GET/PUT of contents, with sha checks that return 409 on a mismatch), and use two browser contexts as two devices. At minimum, check: add, complete, delete, and undo on both devices end up the same; offline and then back online; a 401 shows "Sync problem"; backup and restore; no page errors; no sideways scrolling at 375px wide.

## Owner preferences for anything that shows up in the app

- No em dashes. Use hyphens or rewrite the sentence.
- No emojis.
- Plain, warm wording. No corporate jargon.
- File names use spaces, not underscores (for example `open loops backup 2026-10-10.json`).
