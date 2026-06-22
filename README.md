# Daily Planner

A single-page, self-contained daily planner styled to match the original "Daily Planner" design — same layout, same color palette, and the actual bow/flower/bunny/butterfly artwork from the source design. No build step, no server, no account. Just open the HTML file in a browser.

## Features

- **To Do List** — add, check off, and delete tasks. Completed tasks get struck through.
- **Priorities** — a separate short list for the few things that matter most today.
- **Notes** — a free-text scratchpad, ruled like notebook paper.
- **Day picker** — click any day in the current week's strip to select it. Each day sits in its own fixed circular slot, so the selection ring is always a clean, evenly-centered circle regardless of whether the label is "SUN" or "WED." The selected day gets a soft pink fill plus an outline ring; today always has a small dot under it so you can tell "today" apart from whichever day you're currently viewing.
- **Per-day data** — each day of the week keeps its own to-do list, priorities, and notes. Switching days doesn't erase or mix anything.
- **Reset this day** — a small link under the date clears the to-dos, priorities, and notes for the currently selected day only. It asks for confirmation first, so you can't wipe a day by accident, and it doesn't touch any other day.
- **Autosave** — every change (checking a box, typing a task, editing notes) saves automatically. A small "Saved" pill flashes in the bottom-right corner to confirm.
- **Persistence across reloads** — close the tab, restart your browser, come back tomorrow: your data is still there.
- **Real artwork** — the bow, flower, bunny, and butterfly are the actual graphics from the original design (extracted and embedded directly into the file), not redrawn approximations.

## How to use it

1. Open `daily-planner.html` in any modern browser (Chrome, Safari, Firefox, Edge).
2. Click a day in the top-right strip to select it.
3. Add tasks/priorities by typing in the input row and pressing **Enter**.
4. Click the checkbox to mark something done; click the **✕** (appears on hover) to delete it.
5. Type freely in the Notes box — it saves a moment after you stop typing.
6. To clear a day, click **"Reset this day"** under the date and confirm.

That's it — no setup, no login.

## How data is saved

Data is stored in the browser's `localStorage`, under the key `dailyPlannerData_v1`, as a JSON object keyed by date (`YYYY-MM-DD`). For example:

```json
{
  "days": {
    "2026-06-22": {
      "todos": [{ "id": "id1a2b3c", "text": "Finish report", "done": false }],
      "priorities": [{ "id": "id4d5e6f", "text": "Call dentist", "done": true }],
      "notes": "Remember to bring the charger."
    }
  }
}
```

Resetting a day simply replaces that date's entry with an empty `{ todos: [], priorities: [], notes: "" }` — it does not touch any other date's data.

### Important limitations

- **Local to one browser, one device.** Data is not synced anywhere. Opening the file in a different browser, a different device, or in private/incognito mode will not show your saved data — it starts empty.
- **Clearing browser data deletes it.** If you clear your browser's site data/cache/local storage, the planner's saved content is gone. There is currently no export/backup button.
- **Resetting is permanent.** Once you confirm "Reset this day," that day's data cannot be recovered — there is no undo.
- **The day strip shows the current calendar week** (Sunday–Saturday based on today's date) — it does not let you browse past or future weeks. Selecting, say, "Monday" always shows this week's Monday entry, not a fresh slate, unless you've reset or changed it.

## Customizing

Everything is in one file (`daily-planner.html`) — no dependencies to install, other than two Google Fonts loaded via CDN (`Cormorant` for headings, `Quicksand` for body text).

- **Colors**: edit the CSS variables at the top of the `<style>` block (`--bg`, `--rule`, `--text-deep`, etc.) to change the theme.
- **Artwork**: the bow, flower, bunny, and butterfly are embedded as base64-encoded PNGs directly in the HTML (`<img class="deco ...">` tags). To swap them, replace the `src="data:image/png;base64,..."` value with a new base64 string, and adjust the matching `.deco-*` position/size rules in the CSS.
- **Adding more sections**: follow the pattern used for `todos`/`priorities` — each is a list of `{ id, text, done }` objects rendered by the same `renderList()` function.

## Possible future upgrades

- Export/import data as a JSON or PDF file (manual backup)
- Sync across devices via an account + cloud database
- Month/year view instead of just the current week
- Drag-to-reorder tasks
- Undo for "Reset this day"
