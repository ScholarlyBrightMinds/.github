<div align="center">

<img src="https://raw.githubusercontent.com/ScholarlyBrightMinds/.github/main/profile/banner.png" width="100%" alt="ScholarlyBrightMinds"/>

<br/>

<sub><i>A small hub for researchers who want their own corner of the internet.</i></sub>

<br/>

[![Organization](https://img.shields.io/badge/GitHub-ScholarlyBrightMinds-181717?style=flat-square&logo=github)](https://github.com/ScholarlyBrightMinds)
[![Members](https://img.shields.io/badge/Members-2-informational?style=flat-square)](https://github.com/orgs/ScholarlyBrightMinds/repositories)
[![License](https://img.shields.io/badge/License-MIT-amber?style=flat-square)](#)
[![Hosted on](https://img.shields.io/badge/Hosted-GitHub%20Pages-181717?style=flat-square&logo=github)](https://pages.github.com/)

</div>

<br/>

## § About the hub

Academic personal websites should be *clean, fast, and honest* — not WordPress installations that rot, not Squarespace subscriptions, not the same tired CV-on-a-PDF. We build researchers their own small piece of the web — one that updates itself, costs nothing to run, and stays with them even if they change institution.

Every site in this hub shares the same visual spine — what we call the **Lab-Notebook Elevated** aesthetic: refined editorial typography, subtle molecular atmosphere, a proper day/night theme, and a publications dashboard that updates automatically from Google Scholar and Scopus. Each researcher picks their own accent colour — and that's where the family resemblance ends and their personality begins.

<br/>

## § Members

| Researcher | Focus | Site | Accent |
| :-- | :-- | :-- | :-- |
| **Abdallah Abou Hajal** | AI × Drug Discovery · Cheminformatics | [scholarlybrightminds.github.io/abdallahabouhajal](https://scholarlybrightminds.github.io/abdallahabouhajal/) | 🟢&nbsp; Teal |
| **Molham Sakkal** | Cancer Cell Biology · Drug Delivery | [scholarlybrightminds.github.io/molhamsakkal](https://scholarlybrightminds.github.io/molhamsakkal/) | 🟣&nbsp; Indigo |

<br/>

## § What every site ships with

- **Auto-updating publications** — Google Scholar (weekly) and Scopus (monthly) via GitHub Actions. Publish a paper, wait a week, it shows up. No manual entry, ever.
- **Live metrics dashboard** — publications, citations, h-index, plus a citation-growth sparkline built from the researcher's own cumulative data.
- **Editorial typography** — Fraunces for display, Manrope for body, JetBrains Mono for mono. No bootstrap defaults, no generic AI slop.
- **Day / night toggle** — respects system preference on first visit, remembers your choice after.
- **Ready sections** — About (narrative + timeline + research pillars + awards), Ongoing Research, Publications, Blog.
- **Full mobile support** — hamburger nav, responsive everything, works on a cheap phone.
- **Owned outright** — every line of code lives in the researcher's own repo. If this org disappears tomorrow, their site keeps running.

<br/>

## § Under the hood

Each researcher's site is a single repo with this rough anatomy:

```
theme.config.js       ← single source of truth: name, palette, bio, projects
styles.css            ← shared visual system (CSS variables injected at runtime)
scripts.js            ← shared runtime (nav, bindings, theme toggle, reveal)
serpapi_fetcher.py    ← weekly Scholar refresh  (GitHub Actions cron)
scopus_fetcher.py     ← monthly Scopus refresh (GitHub Actions cron)
data/                 ← auto-updated JSON, the site's source of truth
```

Adding a new researcher means forking the template, swapping **one config file**, and setting two API secrets. Deploy time: ~10 minutes.

<br/>

## § Want a site?

If you're an early-career researcher and the current options (WordPress, Squarespace, writing your own from scratch) feel either expensive or soul-crushing — reach out. We'll set it up for you, free, no strings.

📧 &nbsp;**[abdallah.abouhajal@gmail.com](mailto:abdallah.abouhajal@gmail.com)**

Or [open a quick request](https://github.com/ScholarlyBrightMinds/.github/issues/new?template=website-request.yml) and we'll take it from there.

<br/>

---

<div align="center">

<sub>Built on <a href="https://github.com/muhammedrashidx/ScholarSite_2.0">ScholarSite_2.0</a> by <a href="https://github.com/muhammedrashidx">muhammedrashidx</a> — redesigned &amp; extended by the hub.</sub>

<br/>

<sub><i>Built with curiosity, coffee, and a little bit of CSS.</i></sub>

</div>
