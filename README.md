# Open Loops

A task tracker for getting open loops out of your head, picking one, and doing it.

Open it here: https://ehborden.github.io/open-loops/

The same guide is in the app under **Data > How to**.

---

## How to use it

### 1. Get it out of your head

- Type in the box at the top, or tap the mic on your phone keyboard and talk.
- Say **"next"** between loops. For steps, say **"steps"** with **"then"** between them.
  - Example: *"email Dana, that's quick, next, plan the unit, takes an hour, steps, find last year's doc, then pick the readings, next, call the dentist today"*
- **Add**: one loop goes straight in. Several open the check-over screen.
- **Add with AI**: Claude splits it up, fills in time and energy, and writes a tiny first step. Needs an API key (section 9).
- On the check-over screen you can change names, steps, time, energy, and Today right there. It's saved as a draft, so nothing is lost if you leave. **Keep draft** keeps it for when you come back.
- Without AI, Add picks up phrases like "quick," "10 minutes," "half an hour," "takes forever," "when I'm tired," "need to be fresh," "today," and "first step is."

### 2. Your loops

- Each loop is a note. **Time and energy** are the small tags on it. Tap one to change it.
- **Tap a loop's name** to open its card: name and steps, plus Break it down, Pick for today, Not today, and Let it go. Everything saves as you type.
- **Steps:** the next one shows on the note. Tap its box to check it off. **Steps** at the bottom of the note opens all of them, with a box to add one. The last one asks if you want to close the loop.
- **The circle** on the left closes the whole loop.
- **The x** at the top right of a note deletes it for good. It asks first, and Undo brings it back. A deleted loop is never counted as closed.
- **Types** are your kinds of work, like Class, Admin, or Projects. A loop's type is the tag after Today, and loops of the same type share a color. New loops land in a type by the words in their name. Tap the tag, on the note or in the loop's card, to change it, pick just a color, or edit the types. **Add with AI** picks the type for you.
- **Types** at the bottom of the notes opens colored chips with your types and how many loops each has. Tap one to show only those loops; tap it again, or All, to see everything. The button names the type while one is showing. A refresh shows everything again.
- **Data, then Lists, then Types** opens the types for this list: a name, a color, and the words that match. Each list has its own types, and they follow you to your other devices.
- The color is the thick band on the left of a note. The note you open is shown a little stronger.
- **The bar** under the tags fills as you check off steps. A longer bar means a longer task (set with the time tag).
- **Today** holds up to 3 picks. Tap the **Today** tag on a loop to pick or unpick it.
- **Sort** with the buttons above the notes (a single Sort button on a phone): Today first, Quickest, Easiest, Newest, or Oldest. Each device remembers its own.
- **Undo** reverses your last few actions. It appears in the message that pops up after an action, and at the top.

### 3. Pick for me

When choosing is the hard part. Tap **Pick for me** above the notes and it picks one loop, leaning toward quick, low-energy ones for an easy start. Tap **Pick again** for another, or choose **This or that** (two loops at a time, tap the one you would rather do) or **Spin the wheel** underneath. **Surprise me** goes back to a single pick. Tap **Right now I have...** to set your energy and time first. **Close** goes back to your loops.

### 4. Timer

- The timer is on the right, above Closed. On a phone it's a slim row at the top (tap **More** for the full card, and it opens by itself while a timer runs). The ring drains as the time runs down. **Start** begins it on the loop you opened last (tap **Steps** on a note to open it). With no loop open, it's a timer on its own.
- Pick the minutes first: 5 up to 45. It starts at 25.
- **Start** inside an open note, or on a loop from Pick for me, begins the timer on that loop right away.
- Scroll down on a phone while a timer runs and a bar at the bottom shows the time. Tap it to jump back up.
- **Step done** checks off the current step. **Close loop** finishes the whole thing. **Stop** asks you to leave a note for next time, which becomes the next step.
- For a timer with no loop, leave the dropdown on "Timer only". Picking a loop later attaches it to the running timer.

### 5. Closed

Every loop you close stays tracked in **Closed**, below the timer on a computer and at the bottom of the page on a phone. It starts folded, with just today's count. Tap it to open the counts for today, the last 7 days, your streak, and steps checked off today, plus the list. **Reopen** puts a loop back. The **x** deletes one, and **Delete all closed** clears the list. Both ask first, Undo brings them back, and deleted loops drop out of the counts.

### 6. Not seeing the latest changes?

Tap **Data**, then **Get the latest version**. It loads the newest copy of the app and keeps your loops. The version at the bottom of the Data menu tells you which copy a device is running.

### 7. Work and Home

The two list buttons at the top right switch between two separate lists. They start as **Work** and **Home**. A bar across the top of the page takes the list's color, teal for Work and purple for Home. To use other names (Personal, for example) or other colors, tap **Data**, then **Lists**, then **Names and colors**. With sync on, the names and colors follow you to your other devices.

---

## Setup

### 8. Sync your devices (your own GitHub)

This keeps your phone and computers showing the same lists. Your loops are saved in a private GitHub repo that only you can see.

**One time:**

1. Make a free account at **github.com** if you don't have one.
2. Make a new repository. Click **+** at the top right, then **New repository**.
   - Name it `open-loops-data`.
   - Choose **Private**. The app won't connect to a public one.
   - Click **Create repository**.
3. Make an access token. Click your profile picture, then **Settings**, **Developer settings** (at the bottom), **Personal access tokens**, **Fine-grained tokens**, **Generate new token**.
   - Name it "open loops" and pick an expiration (a year is fine).
   - Under **Repository access**, choose **Only select repositories** and pick `open-loops-data`.
   - Under **Permissions**, find **Contents** and set it to **Read and write**.
   - Click **Generate token**, then copy it right away. It's only shown once.

**On each device:**

1. Open the app. On iPhone, add it to your Home Screen first (Share button, **Add to Home Screen**) and open it from the icon.
2. Tap **Sync off** at the top.
3. Enter your GitHub username, `open-loops-data`, and the token. Tap **Connect**.

The token is saved only in that browser. It's never in a backup or in this repo.

### 9. Turn on AI (your own Claude account)

Add with AI and Break it down use Claude. This is pay-as-you-go and separate from a Claude Pro or Max subscription. With the cheaper model, a brain dump costs roughly a tenth of a cent, so $5 lasts a long time.

**One time:**

1. Go to **console.anthropic.com** and sign in (or make an account).
2. Go to **Settings**, then **Billing**, and buy a small amount of credit, such as $5.
3. **Turn auto-reload off** in the same Billing area. Then you can never be charged more than what you bought.
4. Go to **API Keys** and click **Create Key**.
   - If you see a screen about "identity federation," click **Continue with an API key**.
   - Name it "open loops." The other settings can stay as they are.
5. Copy the key right away. It starts with `sk-ant-` and is only shown once. If you lose it, just make a new one.

**On each device:**

1. Open the app and tap **Data**, then **Settings**.
2. Paste the key into **Claude API key**.
3. Leave the model on **Claude Haiku 5.5** (cheapest), or pick Opus 5.5 for better results at a higher cost.
4. Tap **Save**.

**Good to know:**

- The key is saved only in that browser. It's never in the app's code, a backup, or sync, so other people who open the app can't use it.
- Never paste your key into a chat, an email, or a document. Only into the app.
- Only the text you choose to send with an AI button goes to Anthropic. Nothing runs on its own.
- Check what you've spent at console.anthropic.com under **Usage**.
- To remove the key from a device, clear the box in **Data > Settings** and tap **Save**.

---

## Backups

- **Automatic:** with sync on, the app saves a backup to a `backups` folder in `open-loops-data` about once a week (so the date in the Data menu can say a few days ago) and keeps the last 12. **Data > Restore > From GitHub** lists them by date.
- **By hand:** **Data > Backup** saves both lists as one file (**To a file**), or, with sync on, saves a backup into your GitHub data repo right now (**To GitHub**). **Data > Restore** loads one back (from a file, or from GitHub when sync is on). It always shows you what's in it and asks before replacing anything.

## Fixes for common problems

- **Don't see a new update?** On a computer, press Cmd + Shift + R (Mac) or Ctrl + Shift + R (Windows). On a phone, close the app completely and reopen it. It can take up to 10 minutes.
- **Sync says "Sync problem"?** Tap it. The token may have expired. Make a new one (section 8) and paste it in.
- **AI says the key wasn't accepted?** Check the key in **Data > Settings**, and check that your Anthropic account still has credit.
- **Timer stuck at 0:00?** Tap **Stop here**, then **Skip**.
- **On iPhone, don't delete and re-add the Home Screen icon** unless Sync says "Synced." Deleting it also deletes what's saved on that phone.
