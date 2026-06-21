# 🌸 Kawaii Daily Timetable

link:https://kawai-time-table.netlify.app/

Wanted a cute timetable, so I built one. A single-page, pastel-pink planner for tracking your weekday and weekend schedule — editable times, custom "vibes" for each slot, and a notes box, all wrapped in a soft kawaii aesthetic.

![style](https://img.shields.io/badge/style-kawaii-ffb3c6) ![type](https://img.shields.io/badge/type-static%20site-cdeee0)

## ✨ Features

- **Two schedules** — toggle between Weekday (School Days) and Weekend (Chill Mode)
- **Editable time slots** — click any time block and type your own
- **Custom vibes** — add a note, mood, or task next to each time slot
- **Notes section** — space for reminders or goals
- **Auto-save** — everything is saved automatically in your browser (via `localStorage`), so it's still there next time you open the file
- **Reset button** — restore the default times anytime without losing your vibes or notes
- **No build tools, no dependencies** — it's one HTML file

## 🚀 Getting started

Just open `kawaii-timetable.html` in any web browser. That's it — no installation, no server required.

## 💾 How saving works

Your edits are stored locally in your browser, tied to this specific file. That means:

- Reopening the **same file** in the **same browser** on the **same device** → your data is still there
- Renaming the file, moving it to a different location, or opening it in a different browser → starts fresh

If you want your schedule synced across devices or backed up properly, that would need a small backend (this version doesn't include one).

## 🌐 Deploying for free

Since this is a single static HTML file, you can host it for free with any of these:

- **[Netlify Drop](https://app.netlify.com/drop)** — drag and drop the file, get a live link instantly, no account required to start
- **[GitHub Pages](https://pages.github.com/)** — push to a GitHub repo and enable Pages for a free `username.github.io` link
- **[Vercel](https://vercel.com/)** — connect a repo or drag-and-drop deploy
- **[Cloudflare Pages](https://pages.cloudflare.com/)** — similar drag-and-drop or Git-based deploy

## 🛠 Customizing

Everything lives in one file (`kawaii-timetable.html`):

- **Colors** — edit the CSS variables at the top of the `<style>` block (`--pink`, `--peach`, `--mint`, etc.)
- **Default times** — edit the `schoolTimes` and `weekendTimes` arrays near the bottom of the file
- **Fonts** — currently uses Baloo 2 (headings) and Quicksand (body) from Google Fonts

## 📄 License

Free to use, edit, and share for personal projects.
