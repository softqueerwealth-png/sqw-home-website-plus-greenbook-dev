# Building Things That Matter: Quarterly Check-in

An internal tool for **Soft Queer Wealth**, **The Mahogany Pages** and **Softer Strategies**. Each quarter, the team uses it to review our north star and goals, record what actually happened, check in on how the work feels, and read what the results could mean.

It's an internal audit of our products, our processes and our intentions, asking one question:

> *Are we building businesses that give us the freedom to do more of the work we love, with the people we care about, for communities we believe in?*

---

## What's inside

The page has five tabs, laid out like folder tabs:

| Tab | What it's for |
|---|---|
| **01 North Star** | Why we build, the north star, our five guiding principles, how the three ventures support each other, and the "connected missions, separate books" rule for money between them. |
| **02 Goals** | All 24 goals across the three ventures. Each has a baseline, a target, why it matters, how it's measured, and a status label: Current, Historical, Proposed, Aspirational or To establish. |
| **03 Check-in** | Record each goal's actual result, progress, owner and notes for the quarter. Leave a field blank rather than guess. |
| **04 Pulse** | Each person scores six dimensions from 1 to 10 (purpose, community impact, learning, freedom, financial sustainability, energy), rates whether we're living each principle, and answers nine reflection questions. Reflections stay private unless the person chooses to share them. |
| **05 Results** | Summary numbers, progress bars by venture, a team pulse chart and an automatic "What this could mean" reading. You can also download a CSV of the quarter. |

---

## Two ways to run it

### 1. As a Claude artifact (recommended for team check-ins)

The same file is published as a private Claude artifact. Opened there, it gets things this repo version can't do on its own:

- **Shared, live team data:** everyone sees the same check-in and entries save automatically.
- **Separate logins:** each person's pulse is tied to their own Claude account.
- **"Interpret this quarter":** Claude writes a deeper reading of the results, and anyone can save it for the team.
- **Editor-only goals:** only editors can change goals or open a new quarter.

Share the artifact from its **Share** menu, and give teammates **Contributor** access so they can enter results and their own pulse.

### 2. From this repo (GitHub Pages or locally)

`index.html` runs on its own. When it's opened outside Claude, it switches to **local mode**:

- Goals start from the Q4 2026 plan built into the file.
- Check-ins, pulses and goal edits are saved **in your browser on that device**.
- Type your name in **"Checking in as"** at the top so each person's pulse is saved separately.
- The automatic reading works. The Claude interpretation button doesn't.

**To publish on GitHub Pages:**

1. Commit `index.html` to the root of the repo.
2. In the repo, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**. Pick `main` and `/ (root)`, then save.
4. After a minute, the page is live at `https://<your-username>.github.io/<repo-name>/`.

**To run it locally:** double-click `index.html` to open it in a browser. Nothing needs to be installed.

---

## Saving your data and coming back

In local mode, the data lives in your browser. Clearing browser data or switching computers means starting from the 24 goals again unless you have a backup.

At the end of every check-in:

1. Go to **05 Results** and scroll to the bottom.
2. Click **Download backup (JSON)**.
3. Store the file somewhere **private** (see below).

To pick up where you left off, click **Restore from backup** and choose the file. This works on any computer.

---

## Privacy: please read

- **Public repo = public page.** If this repo is public, GitHub Pages lets anyone with the link see the page, including our goals and targets. Make the repo private if that matters. Note that GitHub Pages on a private repo needs a paid GitHub plan.
- **Never commit backup files to a public repo.** Backups contain everyone's pulse scores and their reflections, including the private ones. Add this to `.gitignore`:

  ```gitignore
  check-in-backup-*.json
  ```

- In the Claude artifact version, private reflections can only be read by the person who wrote them, including from you as the owner.

---

## The quarterly rhythm

| When | What happens |
|---|---|
| **Start of quarter** | Review North Star and Goals together. Editors update targets. In the Claude version, an editor clicks **Open Q[n]** to start the new quarter. |
| **Monthly** | Owners update their goals on the Check-in tab as results come in. |
| **End of quarter** | Everyone saves their Pulse. Then review Results together, discuss the reading, and agree on stop / start / continue. |
| **After the meeting** | Download the CSV and, in local mode, a backup. |

---

## Editing goals

- **In the page:** go to **02 Goals** and click **Edit goal** or **Add a goal**. Fill in the baseline and target numbers whenever a goal can be counted, so Results can show progress automatically. Leave the numbers blank for milestone goals.
- **In the code:** the starting plan is the `DEFAULT_PLAN` object in `index.html`. Changing it only affects browsers that haven't saved data yet.

### How progress is calculated

- **With a numeric baseline:** progress is the share of the way from baseline to target. For example, 31,800 followers from a baseline of 30,000 toward a target of 33,000 counts as 60% of the way.
- **Without a baseline:** progress is the actual result divided by the target.
- **Automatic progress label:** 100% or more is *Achieved*, 75% or more is *On track*, 40% or more is *At risk*, and anything lower is *Behind*. A progress label someone picks by hand always wins.

The automatic reading looks for patterns, not causes. It points to questions to discuss and doesn't prove why anything happened.

---

## Files

```
index.html   The whole app: markup, styles and script in one file, no build step
README.md    This file
```

**Built with:**

- Plain HTML, CSS and JavaScript, with no frameworks.
- Fonts from Google Fonts: Instrument Serif, Instrument Sans and Courier Prime.
- Light and dark mode follow your system setting.

**Companion files** (kept outside this repo):

- *Building Things That Matter, Q4 2026*: the five-page strategy deck (PDF + PowerPoint).
- *KPI Tracker*: the Excel version of the goal list.

---

*A living document, revisited quarterly. Built by community, for community.*
