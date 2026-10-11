# Open Loops

A task tracker for getting open loops out of your head, picking one, and doing it.

Open it here: https://ehborden.github.io/open-loops/

The same guide is in the app under **Data > How to**.

---

## How to use it

### 1. Get it out of your head

- **One at a time:** type in the box at the top and press Enter.
- **Lots at once:** tap **Talk it out**, tap the mic on your phone keyboard, and talk.
  - Say **"next"** between loops.
  - To list steps, say **"steps"** and put **"then"** between them.
  - Example: *"email Dana, that's quick, next, plan the unit, takes an hour, steps, find last year's doc, then pick the readings, next, call the dentist today"*
- Then tap one of these:
  - **AI extract** sends it to Claude, which splits it up, fills in time and energy, and writes a tiny first step. (Needs an API key, see section 8.)
  - **Sort it (no AI)** splits on "next" and picks up a few phrases: "quick," "10 minutes," "half an hour," "takes forever," "when I'm tired," "need to be fresh," "today," and "first step is."
- Either way, you check everything on a review screen before anything is added.

### 2. Your loops

- **Tap a loop's name** to edit it: the name, steps, how long, energy, and Pick for today. **Not today** and **Let it go** are under **More**.
- **Steps:** the list shows the next step with a small box. Tap the box to check it off. Tap the arrow to see all the steps. Checking off the last step asks if you want to close the loop.
- **Break it down** (in the editor) asks Claude for 3 to 5 small steps. You check them before they're used.
- **The circle** on the left closes the whole loop.
- **Today** holds up to 3 picks. Fewer picks means you actually finish them.
- **Quick sort** shows up when loops are missing time or energy. It goes one loop at a time with big buttons. **Let AI fill all** fills them all in for you to check.
- **Undo** (at the top) reverses your last few actions.

### 3. Pick one

When choosing is the hard part. Set your energy and time, then swipe through cards, spin the wheel, or let it pick for you.

### 4. Focus

- **Start** on any loop begins a timer right away.
- **On a computer:** Focus is always on the right, with your Wins under it.
- **On a phone:** Focus is a card at the top. If you scroll down while a timer runs, a bar at the bottom shows the time. Tap it to jump back.
- **Step done** checks off the current step. **Close loop** finishes the whole thing. **Stop** asks you to leave a note for next time, which becomes the next step.
- To use a timer with no loop, pick "Timer only" from the Focus dropdown. Picking a loop later attaches it to the running timer.

### 5. Wins

Everything you've closed, with counts for today, the last 7 days, your streak, and steps checked off today. Look here when your brain says you did nothing.

### 6. Work and Home

The **Work / Home** toggle at the top switches between two separate lists.

---

## Setup

### 7. Sync your devices (your own GitHub)

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

### 8. Turn on AI (your own Claude account)

AI extract, Let AI fill all, and Break it down use Claude. This is pay-as-you-go and separate from a Claude Pro or Max subscription. With the cheaper model, a brain dump costs roughly a tenth of a cent, so $5 lasts a long time.

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

- **Automatic:** with sync on, the app saves a backup to a `backups` folder in `open-loops-data` about once a week and keeps the last 12. **Data > Restore from GitHub** lists them by date.
- **By hand:** **Data > Backup** downloads both lists as one file. **Data > Restore** loads one back. It always shows you what's in it and asks before replacing anything.

## Fixes for common problems

- **Don't see a new update?** On a computer, press Cmd + Shift + R (Mac) or Ctrl + Shift + R (Windows). On a phone, close the app completely and reopen it. It can take up to 10 minutes.
- **Sync says "Sync problem"?** Tap it. The token may have expired. Make a new one (section 7) and paste it in.
- **AI says the key wasn't accepted?** Check the key in **Data > Settings**, and check that your Anthropic account still has credit.
- **Timer stuck at 0:00?** Tap **Stop here**, then **Skip**.
- **On iPhone, don't delete and re-add the Home Screen icon** unless Sync says "Synced." Deleting it also deletes what's saved on that phone.
