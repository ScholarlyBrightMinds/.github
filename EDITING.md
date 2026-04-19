# ✏️ How to edit your site

**No coding experience needed.** Everything about your site (your bio, your photo, your projects, your timeline, your social links) lives in one file called `theme.config.js`. Edit that file and your site updates itself in about 2 minutes.

This guide shows you three ways to edit, from easiest to most flexible. Pick the one that feels right for you.

<br/>

## 🟢 Method 1 · Edit directly on GitHub

**Easiest option. Works on phone or laptop. No software to install. Nothing to break.**

### The 60-second version

1. Go to your repo on GitHub (for example `github.com/ScholarlyBrightMinds/yourname`)
2. Click the file you want to change, usually `theme.config.js`
3. Click the **pencil icon** in the top-right of the file
4. Make your change in the text box
5. Scroll to the bottom, write a short note like `update bio`, then click **Commit changes**
6. Wait about 2 minutes. Your site is updated.

That's it. No branches, no pull requests, no approvals if it's your own repo.

### What each section of `theme.config.js` controls

| Section | What it controls |
|:--|:--|
| `identity` | Your name, role, photo path, status line, tagline |
| `palette` | Your colors (day and night modes) |
| `ids` | Scholar, Scopus, ORCID, email |
| `social` | The icons in your header and footer |
| `bio` | The text that appears on the home page |
| `chips` | The little bubbles under your name on the home page |
| `ledes` | The short description at the top of About, Projects, etc. |
| `about` | Your paragraphs, timeline, pillars, awards |
| `projects` | Your current projects (active, published, etc.) |
| `blog` | List of blog posts |
| `footer` | Copyright year and credits |

### Quick recipes

**Change my photo**
1. Click `images/profile.png`, then the trash icon, then commit
2. Click `Add file` → `Upload files` and drag your new photo
3. Name it exactly `profile.png` (or update the `photo:` line in `theme.config.js`)

**Change my bio**
1. Open `theme.config.js`
2. Find the `bio:` section
3. Edit the text inside the quotes
4. Commit

**Add a new project**
1. Open `theme.config.js`
2. Find the `projects:` section
3. Copy an existing project block (from `{` to `}`) including the comma
4. Paste it above or below an existing one
5. Change the `n:`, `title:`, `desc:`, `tech:`, `status:`, `statusKind:`, `needs:` values
6. Commit

**Mark a project as published**
1. Find it in `projects:`
2. Change `statusKind: "active"` to `statusKind: "published"`
3. Update `status:` to something like `"Published · Journal Name · 2026"`
4. The badge turns green automatically and the collaborate button disappears

**Add a new award**
1. Find `awards:` inside the `about:` section
2. Copy an existing award line
3. Change the `icon`, `title`, `venue`
4. Commit

**Update citation count or h-index**
- You don't. The publications page updates itself every Monday (Scholar) and on the 1st of every month (Scopus)
- Chips on the home page like "13 Publications · 98 Citations" are manual. Edit those in `theme.config.js` under `chips:` when you want to refresh them

### Mistakes to avoid

Three things will break a `theme.config.js` edit:

1. Deleting a comma between items (every line except the last in a block needs a comma at the end)
2. Deleting a quote mark `"` (text must be wrapped in quotes)
3. Deleting a bracket `{` `}` `[` `]` (they come in pairs, always)

If you break one, the site goes blank. Don't panic. GitHub keeps every old version. Go to your repo, click the commit count at the top of the file list, find your last working version, click the `•••` menu next to it, then **Revert**. You're back in 30 seconds.

### Previewing before committing

GitHub has a **Preview** tab when you're editing, but it only works for markdown (`.md`) files. For `theme.config.js` you edit and commit. The safety net is: even if you break the site, it's reversible in under a minute.

If you want a real preview before committing, see Method 3 below.

<br/>

## 🟡 Method 2 · Ask the team

**For friends who genuinely don't want to touch any files.**

1. Send an email to **abdallah.abouhajal@gmail.com** describing what you want changed, like: *"Hey, can you update my bio to say X, add a new project about Y, and change my status chip to 'Currently writing my thesis'?"*
2. Attach any new photos, new CV, anything relevant
3. The team makes the change for you, commits it, and replies when it's live

Turnaround is usually same-day for small edits.

<br/>

## 🔵 Method 3 · Edit on your computer with a live preview

**For the curious. 15 minutes to set up once, then editing is the same speed as Method 1 but you can see changes before they go live.**

### One-time setup

1. Install **Git** from https://git-scm.com/downloads
2. Install a code editor (Visual Studio Code is free and works on everything): https://code.visualstudio.com/
3. Install **Python** if you don't have it: https://www.python.org/downloads/
4. Open Terminal (Mac/Linux) or PowerShell (Windows) and run:
   ```
   git clone https://github.com/ScholarlyBrightMinds/YOUR-NAME.git
   cd YOUR-NAME
   ```

### Daily flow

1. Open the folder in VS Code
2. Start a local preview:
   ```
   python3 -m http.server 8000
   ```
3. Open http://localhost:8000/ in your browser. That's your site exactly as it will look live.
4. Edit `theme.config.js`, save, refresh the browser, see your change instantly
5. Once you like it, commit and push:
   ```
   git add -A
   git commit -m "updated bio"
   git push
   ```
6. Live in about 2 minutes.

### Why Method 3 is worth it for some people

- See exactly how it looks before anyone else does
- Experiment without committing
- Edit without internet (commit later)
- Learn git, which is useful for a hundred other things

<br/>

## 🎁 Bonus · Letting a friend propose changes without edit access

**Useful if you want someone to help but not hand over your repo password.**

### How it works

1. They fork your repo (makes their own copy)
2. They edit their copy
3. They open a pull request asking to merge their changes into your repo
4. You review, click **Merge**, live in 2 minutes
5. You can say no at any point

### How they do it

1. Go to your repo on GitHub
2. Click **Fork** in the top-right, fork to their account
3. Edit whatever they want in their fork (same as Method 1)
4. Click **Contribute** → **Open pull request**
5. Write what they changed, click **Create pull request**
6. You get a notification, review, merge if you like it

<br/>

## 🆘 When something breaks

**Site shows nothing, blank page**
You probably broke the JavaScript. Open your repo, click the commit history at the top, find the last working commit, click the `•••` menu, then **Revert**. Done.

**Publications not updating**
They update Monday at 05:00 UTC (Scholar) and the 1st of the month at 05:00 UTC (Scopus). To trigger manually: go to your repo, click the **Actions** tab, click the workflow, then **Run workflow**. If that fails, check your repo → **Settings** → **Secrets and variables** → **Actions**. Both `SERPAPI_KEY` and `SCOPUS_API_KEY` must exist.

**New photo not showing**
Filename must be exactly `profile.png` and live in the `images/` folder. Hard-refresh your browser (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac). Your browser is caching the old one.

**Mobile looks weird**
Hard-refresh. Your phone caches aggressively. Safari: clear history. Chrome: pull down twice to refresh. Samsung: Settings → Delete browsing data → "Cached images and files".

<br/>

