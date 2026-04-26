# 🏎️ Bishal's Pit Wall — F1 2026 Dashboard

<div align="center">

![F1 2026](https://img.shields.io/badge/Formula%201-2026%20Season-E8002D?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMiAxNWwtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTlMMTkgOGwtOSA5eiIvPjwvc3ZnPg==)
![License](https://img.shields.io/badge/License-Apache%202.0-27F4D2?style=for-the-badge)
![Single File](https://img.shields.io/badge/Single%20File-No%20Backend-229971?style=for-the-badge)
![Live Data](https://img.shields.io/badge/Live%20Data-OpenF1%20%2B%20Jolpica-FF8000?style=for-the-badge)

**An editorial-style, single-file F1 dashboard for the 2026 season.**  
Live standings · Countdown timer · Race popups · No backend. No database. No build tools.

[**→ View Live**](https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/f1dashboard_bishal.html)

</div>

---

## ✨ Features

| Feature | Details |
|---|---|
| ⏱️ **Live Countdown** | Auto-fetches the next race from the 2026 calendar — ticks every second |
| 🏆 **Driver Standings** | Top 10 WDC standings pulled live from Jolpica API on every page open |
| 🏗️ **Constructor Standings** | All 11 constructors with animated points bars — live from Jolpica |
| 📅 **Season Calendar** | All 23 rounds with race status, dates, winners, and flag emojis |
| 📊 **Race Stats Popup** | Click any completed race to see: P1–P10 classification, time gaps, constructor points for that race |
| 🎙️ **Paddock Intel** | Last race podium + editorial news section |
| 📰 **Scrolling Ticker** | Live stats ribbon across the top of the page |
| 📺 **FanCode Button** | One-click link to watch live on FanCode |
| 💅 **Zero Dependencies** | One `.html` file — no npm, no build step, no server |

---

## 🖥️ Preview

```
┌─────────────────────────────────────────────────────────┐
│  TICKER: WDC · ANTONELLI 72pts  |  WCC · MERCEDES 135  │
├─────────────────────────────────────────────────────────┤
│                                                         │
│   Bishal's Pit Wall.          Good evening, Bishal      │
│   ─────────────────           MON · 27 APR · 2026       │
│                                                         │
├───────────────────────┬─────────────────────────────────┤
│  Miami Grand Prix     │  Lights Out In                  │
│  Round 04 · Up Next   │  06 : 19 : 04 : 32              │
│  May 1–3              │  [ ▶ Watch on FanCode ]         │
├───────────┬───────────┴──────────┬──────────────────────┤
│ § 01      │ § 02                 │ § 03                 │
│ DRIVERS   │ CONSTRUCTORS         │ PADDOCK INTEL        │
│ ─────     │ ─────────            │ ────────────         │
│ 01 ANT 72 │ 01 Mercedes ████▌    │ Japanese GP Podium   │
│ 02 RUS 61 │ 02 Ferrari  ████     │ P1 Antonelli         │
│ ...       │ ...                  │ P2 Russell           │
└───────────┴──────────────────────┴──────────────────────┘
│  R01 🇦🇺  R02 🇨🇳  R03 🇯🇵  R04 🇺🇸 NEXT  R05 🇨🇦  ...   │
│  [click done rounds for race stats popup]               │
└─────────────────────────────────────────────────────────┘
```

---

## 🚀 Getting Started

### Option 1 — Open Locally
```bash
# Just double-click the file, or:
git clone https://github.com/bishals098/f1-pit-wall.git
cd YOUR_REPO_NAME
open f1dashboard.html
```
> Requires an internet connection for live API data. All layout/CSS loads offline.

### Option 2 — GitHub Pages (Recommended)
1. Push to GitHub
2. Go to **Settings → Pages**
3. Source: **Deploy from branch → `main` → `/ (root)`**
4. Save → your dashboard is live at `https://bishals098.github.io/f1-pit-wall/`

Every `git push` auto-redeploys. No manual republishing needed.

---

## 🔌 Live Data Sources

| Data | API | Endpoint |
|---|---|---|
| Driver standings | [Jolpica](https://api.jolpi.ca) | `/ergast/f1/2026/driverstandings.json` |
| Constructor standings | [Jolpica](https://api.jolpi.ca) | `/ergast/f1/2026/constructorstandings.json` |
| Race schedule | [Jolpica](https://api.jolpi.ca) | `/ergast/f1/2026/races.json` |
| Per-race results (popup) | [Jolpica](https://api.jolpi.ca) | `/ergast/f1/2026/{round}/results.json` |
| Last race podium | [OpenF1](https://openf1.org) | `/v1/session_result` |
| Fastest pit stop | [OpenF1](https://openf1.org) | `/v1/pit` |

All API calls include **3× retry with exponential back-off**. If any call fails, the rest of the page stays fully functional.

---

## 🎨 Design System

```
Typefaces
  Playfair Display  — editorial headings (italic weights)
  Inter             — UI and data text
  JetBrains Mono    — numbers, codes, countdown digits

Palette
  --carbon          #0a0a0a   Background
  --racing          #E10600   Accent red
  --paper           #F2ECE0   Text / cream surfaces
  --gold            #D4A017   Points badges
  --mercedes        #27F4D2   Favourite team accent ★
```

Team colours are pulled directly from the official 2026 liveries and applied via CSS custom properties (`--team-color`).

---

## 📁 Project Structure

```
f1dashboard_bishal.html     ← everything. the whole project.
README.md
LICENSE
```

That's it. No `node_modules`. No `package.json`. No Webpack. No React.  
Just one HTML file you can open in any browser.

---

## 🛠️ Customisation

All data is fetched dynamically — but a few things are still hardcoded and easy to tweak:

| What | Where in the file | How to change |
|---|---|---|
| Your name in the greeting | Search `Bishal` | Replace with your name |
| Favourite driver highlight | `driverId === 'hamilton'` | Change to any Jolpica driver ID |
| Favourite team highlight | `id === 'mercedes'` | Change to any constructor ID |
| Paddock news articles | `.news-item` blocks in HTML | Edit directly |
| Ticker items | `const items = [...]` in JS | Add/remove objects |

---

## 📋 Roadmap Ideas

- [ ] Fastest lap stat inside race popup
- [ ] Auto-updating ticker from live API
- [ ] Calendar auto-mark completed rounds dynamically
- [ ] Sprint race support
- [ ] Dark/light mode toggle

---

## 📄 License

Licensed under the **[Apache License 2.0](LICENSE)**.  
You are free to use, modify, and distribute this project with attribution.

```
Copyright 2026 Bishal Saha

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0
```

---

## 🙏 Acknowledgements

- [OpenF1 API](https://openf1.org) — free, open-source live F1 data
- [Jolpica Ergast Mirror](https://api.jolpi.ca) — reliable F1 results & standings
- [Google Fonts](https://fonts.google.com) — Playfair Display, Inter, JetBrains Mono

---

<div align="center">
  <sub>Built with ❤️ for the love of Formula 1 · 2026 Season</sub>
</div>