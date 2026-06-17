# Throughline

**Your day, in logical order.** A single-file, zero-dependency task management app that runs entirely in the browser. Data lives in `localStorage` with optional cloud sync via Supabase.

---

## Features

### Task Management
- **Add tasks** with a text field, domain, importance, urgency, and optional due date
- **Quick-add via keyboard** — press Enter to add
- **Edit** any task inline via a modal: change text, domain, importance, urgency, shop category, due date, and notes
- **Delete** tasks from the edit modal
- **Mark done / undo** — completed tasks stay greyed until end of day, then move to history
- **"Set date" prompt** — completing a task containing "set date" triggers a modal to spin off a dated follow-up item

### Organization
- **6 domains**: House, Work, Life admin, Health, Creativity, Shopping
- **5 importance levels**: Accountable (red) → Mandatory → Necessary → Preferable → Optional (grey)
- **7 urgency levels**: Date specific, Today, This week, This month, This year, 5 year plan, Optional
- **Shopping sub-categories**: Online, General store, Specialty store, Custom order, Dedicated outing, Thrift, Share
- **Notes & details** per item — editable in a dedicated modal, auto-saved on close

### Views & Filtering
- **Tabbed navigation**: All, individual domain tabs, History
- **Full-text search** across task text and notes
- **Filters** by importance, urgency, and shop category (shown only on the Shopping tab)
- **Sort options**: Auto (logical), Importance, Urgency, Domain, Due date, Date added, A–Z

### Smart Sorting (Auto mode)
- Overdue & due-now items are pinned to the top in a "Due now" group
- Items with due dates within 3 days are intermixed with "Today" items
- Everything else flows by urgency × importance
- Completed-today items remain visible at the bottom until midnight

### History
- Completed items appear grouped by day (Today / Yesterday / full date)
- Shows completion timestamp and preserves domain context

### Back up & Restore
- **Export** — downloads a JSON backup file
- **Import** — restores from a previously exported JSON file

### Cloud Sync (optional)
- Built-in Supabase integration for cross-device sync
- Login / signup overlay (email + password)
- Conflict resolution: newer local data wins, otherwise cloud data is adopted
- Sync status pill: Local only / Saving… / Synced / Offline

### Responsive Design
- Adapts layout for narrow screens (≤520px): hides "Add" label, adjusts font sizes and select widths
- Touch-friendly tap targets throughout
- Modal bottom-sheet on mobile, centered dialog on desktop

### No Dependencies
- Pure HTML + CSS + vanilla JavaScript — zero build tools, frameworks, or runtime dependencies
- Uses Supabase JS SDK (loaded from CDN) only when cloud keys are configured
- Fonts loaded from Google Fonts (Fraunces + Inter)

---

## Configuration

1. Open `index.html`
2. Find the `SUPABASE_URL` and `SUPABASE_ANON_KEY` constants (lines 549–550)
3. Paste your Supabase project credentials to enable cloud sync
4. Leave them blank for local-only mode

No other setup required — open the file in any modern browser.
