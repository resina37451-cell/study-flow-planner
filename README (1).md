# 📅 Study Flow Planner

> A powerful visual timeline calendar plugin for [Obsidian](https://obsidian.md/), built for students and professionals who want to plan their week at a glance.


---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Installation](#-installation)
- [Getting Started](#-getting-started)
- [User Interface](#-user-interface)
- [Creating & Managing Events](#-creating--managing-events)
- [View Modes & Zoom Levels](#-view-modes--zoom-levels)
- [Study Mode](#-study-mode)
- [Note Integration](#-note-integration)
- [Auto-Detection from Notes](#-auto-detection-from-notes)
- [Language Support](#-language-support)
- [Color System](#-color-system)
- [Keyboard & Mouse Interactions](#-keyboard--mouse-interactions)
- [Data Persistence](#-data-persistence)
- [FAQ](#-faq)
- [Contributing](#-contributing)

---

## 🔭 Overview

**Study Flow Planner** is a visual timeline calendar that lives inside your Obsidian vault. It displays a scrollable day-by-day grid from **5:00 to 23:00**, lets you create color-coded events, link them to notes, add tags, and switch into a focused **Study Mode** that automatically highlights academic content.

Whether you're a student organizing exam prep or a professional managing your daily schedule, Study Flow Planner gives you a Google Calendar-like experience without ever leaving Obsidian.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📆 Timeline calendar | Scrollable grid from 5:00 to 23:00, organized by day |
| 🔭 Multiple zoom levels | View 1 day, 1 week, 2 weeks, 1 month, or 2 months |
| ➕ Event creation | Create timed or all-day events with a single click |
| 🎨 Color coding | 10 preset colors to categorize your events visually |
| 🎓 Study Mode | Highlights study-related events with subject-specific colors |
| 🔗 Note linking | Link any event directly to a note in your vault |
| 🔍 Note autocomplete | Smart search suggestions while linking notes |
| 📄 Auto-detection from notes | Events written in daily notes appear automatically |
| 🏷 Tags | Add freeform tags to each event |
| ✅ Done state | Mark events as completed with strikethrough style |
| 🕐 Now line | A live red line shows the current time in today's column |
| 💬 Tooltips | Hover any event to see details instantly |
| 🌐 Bilingual | Fully supports Portuguese 🇧🇷 and English 🇺🇸 |
| 💾 Persistent data | All events are saved automatically to your vault data |

---

## 🛠 Installation

### Manual Installation (recommended while not on Community Plugins)

1. Download the latest release files:
   - `main.js`
   - `manifest.json`
   - `styles.css`

2. In your Obsidian vault, navigate to:
   ```
   YourVault/.obsidian/plugins/
   ```

3. Create a new folder called `study-flow-planner` and place all three files inside it:
   ```
   YourVault/
   └── .obsidian/
       └── plugins/
           └── study-flow-planner/
               ├── main.js
               ├── manifest.json
               └── styles.css
   ```

4. Open Obsidian → **Settings** → **Community Plugins** → Enable **Study Flow Planner**.

5. The calendar icon (📅) will appear in your left ribbon. Click it to open the planner.

> **Note:** You may need to restart Obsidian or click "Reload plugins" for the plugin to appear.

### Requirements

- Obsidian version **0.15.0** or higher
- Works on both **desktop** and **mobile**

---

## 🚀 Getting Started

Once installed and enabled, you can open Study Flow Planner in two ways:

1. **Ribbon icon** — click the 📅 calendar icon in the left sidebar.
2. **Command palette** — press `Ctrl/Cmd + P` and search for:
   - `Open Study Flow Planner` (English)
   - `Abrir Study Flow Planner` (Portuguese)

On first launch, the planner loads with a few sample events so you can immediately see how it looks. These will be replaced as soon as you create your own events.

---

## 🖥 User Interface

The planner is divided into four main areas:

```
┌─────────────────────────────────────────────────────────────────┐
│ TOOLBAR: Title | Navigation | Zoom Buttons | Study Mode | + New │
├──────────┬──────────────────────────────────────────────────────┤
│          │  DAY HEADERS (Mon 1, Tue 2, Wed 3...)                │
│  GUTTER  ├──────────────────────────────────────────────────────┤
│  (time   │  ALL-DAY ROW                                         │
│  labels) ├──────────────────────────────────────────────────────┤
│  05:00   │                                                      │
│  05:30   │          TIME GRID (scrollable)                      │
│  06:00   │          Events appear as colored blocks here        │
│  ...     │          Red "now" line on today's column            │
│  23:00   │                                                      │
└──────────┴──────────────────────────────────────────────────────┘
```

### Toolbar Elements

| Element | Description |
|---|---|
| **📅 Planner** | Plugin title |
| **‹ ›** | Navigate backward / forward by the current zoom period |
| **Period label** | Shows the current date range (e.g. "1 Apr – 14 Apr 2025") |
| **1 Day / 1wk / 2wks / Month / 2 months** | Zoom level selector |
| **🎓 Study Mode / 📅 Normal Mode** | Toggle between modes |
| **+ New** | Opens the event creation modal |

### Gutter (Left Column)

The left column shows time labels in **30-minute slots** from `05:00` to `23:00`. It scrolls in sync with the main grid. Full-hour labels are displayed in a bolder style for quick visual scanning.

### Day Headers

Each column header shows:
- Month abbreviation (e.g. **Apr**)
- Day of the week (e.g. **Mon**)
- Day number — today's number is highlighted with a colored circle

Weekend columns (Saturday and Sunday) have their day name and number displayed in **red** to stand out.

### All-Day Row

A thin row below the day headers is reserved for **all-day events**. Click any cell in this row to quickly create an all-day event for that date.

### Time Grid

The main scrollable area. Each column is one day. Each row is a **30-minute slot**. The full-hour boundaries have a slightly stronger line. Events appear as colored blocks sized proportionally to their duration.

---

## 📝 Creating & Managing Events

### Creating a New Event

There are three ways to open the creation form:

1. **Click any time slot** in the grid → opens the modal pre-filled with that date and time.
2. **Click a day header** → opens the modal pre-filled with that date as an all-day event.
3. **Click + New** in the toolbar → opens a blank modal defaulting to today at 09:00.

### The Event Form

| Field | Description |
|---|---|
| **Title** | The event name. Required — the form won't save without it. |
| **Date** | The date of the event (YYYY-MM-DD format). |
| **Start / End** | The start and end times (hidden for all-day events). |
| **Notes** | Optional free-text notes visible in the tooltip. |
| **Linked Note** | Path to a note in your vault (e.g. `folder/my-note.md`). |
| **Tags** | Comma-separated tags (e.g. `study, exam, biology`). |
| **Color** | One of 10 preset color swatches. Click to select. |
| **Done** *(edit only)* | Checkbox to mark the event as completed. |

### Editing an Event

Click any event block in the grid to open the edit modal. It works exactly like the creation form, but also shows:

- A **Done** checkbox to mark the event as completed (appears with strikethrough style on the grid).
- A **Delete** button (red) to permanently remove the event.

### Deleting an Event

Open the event's edit modal and click the red **Delete** button at the bottom left. The action is immediate — there is no confirmation dialog.

### Marking as Done

Open the event's edit modal, check the **Done** checkbox, and click Save. The event block will appear faded with a strikethrough title on the grid.

---

## 🔭 View Modes & Zoom Levels

The zoom buttons in the toolbar control how many days are visible at once:

| Button | Days shown | Column width | Best for |
|---|---|---|---|
| **Today / Hoje** | 1 day | 220 px | Detailed daily planning |
| **1wk / 1sem** | 7 days | 110 px | Standard weekly view |
| **2wks / 2sem** | 14 days | 78 px | *(Default)* Fortnight overview |
| **Month / Mês** | 30 days | 52 px | Monthly overview |
| **2 months / 2 meses** | 60 days | 28 px | Long-term planning |

### Navigation

- Click **‹** to go back one period.
- Click **›** to go forward one period.
- The navigation arrows are hidden in **Today/1-day** view (always shows the current day).
- The period label at the top updates automatically to reflect the visible date range.

---

## 🎓 Study Mode

Study Mode is a special display layer designed for students. Toggle it with the **🎓 Study Mode** button in the toolbar. Its state is remembered between sessions.

### What Study Mode Does

When enabled:

1. **Highlights study-related events** with **subject-specific colors** — automatically, based on keywords in the event title.
2. **Note-sourced events** (auto-detected from daily notes) also receive subject colors when Study Mode is active.
3. User-created events that are not study-related are displayed normally.

### Subject Color Map

Study Mode detects the subject from the event title and assigns a color:

| Subject (keywords) | Color |
|---|---|
| Biology / Biologia | 🟢 Green `#3aaa6e` |
| Chemistry / Química | 🟠 Orange `#e07c3a` |
| Physics / Física | 🔵 Blue `#4a7fe8` |
| Math / Matemática | 🟣 Purple `#7c5cbf` |
| English / Inglês | 🩵 Cyan `#2bbfc9` |
| History / História | 🟤 Brown `#c9722b` |
| Geography / Geografia | 🔷 Steel blue `#5a7fa8` |
| Portuguese / Literature / Redação | 🌸 Pink `#c94f7c` |
| Revision / Revisão | 🔴 Red `#e05c5c` |
| Other study keywords | 🔵 Blue `#4a7fe8` |

### Study Keywords Detected

Study Mode recognizes the following words (case-insensitive) in event titles:

> study, revision, review, biology, chemistry, physics, math, mathematics, english, history, geography, science, literature, grammar, vocabulary, exercise, practice, homework, reading, lecture, exam, test, quiz, class, estudo, estudar, revisão, biologia, química, física, matemática, inglês, história, geografia, ciência, literatura, gramática, vocabulário, exercício, prática, tarefa, leitura, aula, prova, teste, redação, português

---

## 🔗 Note Integration

### Linking a Note to an Event

Inside the event form, the **Linked Note** field accepts any file path within your vault, for example:

```
Studies/Biology/Cell Division.md
Daily Notes/2025-04-10.md
Projects/Thesis.md
```

**Autocomplete:** As you type in the Linked Note field, the planner searches your vault in real time and shows up to 8 matching file paths. Click a suggestion to fill the field automatically.

**Open Note button:** Once a path is entered, an **Open Note** button appears next to the field. Click it to open the linked note directly (works both inside the modal and from the tooltip).

### Clicking a Note-Linked Event

Clicking an event that has a source note (auto-detected from a daily note) opens the corresponding note in Obsidian. These events are read-only — they cannot be edited through the planner.

---

## 📄 Auto-Detection from Notes

Study Flow Planner **automatically reads events from your daily notes** — no manual import needed.

### How It Works

1. The plugin scans all Markdown files in your vault.
2. Files whose **base name contains a date** in `YYYY-MM-DD` format are parsed (e.g. `2025-04-10.md`, `Daily Notes/2025-04-10 Monday.md`).
3. Any line matching the pattern `HH:MM Event title` is turned into a calendar event.

### Supported Line Formats

```markdown
09:00 Study Biology
- 14:30 Review Chapter 5
* 11:00 Math homework
- [ ] 16:00 Gym session
- [x] 08:00 Morning reading
```

All of the above will generate events on the matching date.

### Notes About Auto-Detected Events

- They appear with a **dashed left border** to distinguish them from user-created events.
- They are **read-only** — clicking them opens the source note, not an edit modal.
- Their color defaults to gray (`#888888`). In **Study Mode**, they receive subject-specific colors automatically.
- They are **never persisted** to the plugin's own data — they are always re-read live from your notes.
- The calendar **updates automatically** whenever a note is created, modified, renamed, or deleted.

---

## 🌐 Language Support

Study Flow Planner automatically detects your language from Obsidian's locale setting (or your browser/system locale).

| Language | Detected when locale starts with |
|---|---|
| 🇧🇷 Portuguese | `pt` |
| 🇺🇸 English | anything else |

All labels, buttons, day names, month names, and placeholder text switch to the detected language automatically. No configuration needed.

---

## 🎨 Color System

When creating or editing an event, you can choose from 10 preset colors:

| Swatch | Hex | Suggested use |
|---|---|---|
| 🔵 Blue | `#4a7fe8` | Work / default |
| 🟣 Purple | `#7c5cbf` | Projects |
| 🔴 Red | `#e05c5c` | Urgent / exams |
| 🟠 Orange | `#e07c3a` | Health / gym |
| 🟢 Green | `#3aaa6e` | Study / done |
| 🩵 Cyan | `#2bbfc9` | Social |
| 🟤 Brown | `#c9722b` | Personal |
| 💜 Magenta | `#b03ab5` | Creative |
| 🔷 Steel | `#5a7fa8` | Recurring |
| 🌸 Pink | `#c94f7c` | Wellness |

---

## 🖱 Keyboard & Mouse Interactions

| Action | How |
|---|---|
| Open new event modal | Click **+ New** or click any time slot |
| Create all-day event | Click a **day header** or any cell in the **all-day row** |
| Edit an event | Click the event block |
| Delete an event | Open edit modal → click **Delete** |
| Mark as done | Open edit modal → check **Done** → Save |
| Open linked note | Click event (note-sourced) or **Open note** button in modal |
| See event details | Hover over any event block |
| Navigate forward/back | Click **‹** or **›** in the toolbar |
| Change zoom level | Click any zoom button in the toolbar |
| Toggle Study Mode | Click **🎓 / 📅** button in the toolbar |
| Close modal | Click **Cancel** or click outside the modal |

---

## 💾 Data Persistence

All user-created events are automatically saved to Obsidian's plugin data storage (`data.json` inside the plugin folder). You do not need to manually save anything.

**What is saved:**
- All user-created events (title, date, times, color, notes, tags, linked note, done state)
- Study Mode on/off state

**What is NOT saved:**
- Note-detected events (always re-read live from your vault files)

Events persist across Obsidian restarts and vault reopens.

---

## ❓ FAQ

**Q: Can I create recurring events?**
A: Not currently. Each event is a single occurrence. For recurring items, the best workaround is to use the auto-detection feature by writing time-stamped entries in your daily notes.

**Q: Can I resize or drag events?**
A: Not in this version. To change the time of an event, click it to open the edit modal and update the start/end times manually.

**Q: The all-day row is separate from the time grid — why?**
A: All-day events (like holidays or deadlines) don't have a meaningful start/end time, so they are shown in a dedicated row at the top, similar to Google Calendar's behavior.

**Q: My daily note events aren't showing up — what's wrong?**
A: Make sure the file name includes a date in `YYYY-MM-DD` format anywhere in the base name. Also ensure the time entries follow the format `HH:MM Event title` at the start of the line (optional list markers `- `, `* `, or checkboxes `- [ ] ` are supported).

**Q: Can I use the plugin in Portuguese and English simultaneously?**
A: The plugin uses a single language, auto-detected from your system locale. It is not possible to mix languages in the same session.

**Q: Does the plugin sync with Google Calendar or any external calendar?**
A: No. Study Flow Planner is self-contained within your Obsidian vault. There is no external sync.

**Q: Is my data stored in the cloud?**
A: No. All data is stored locally inside your vault's `.obsidian/plugins/study-flow-planner/data.json` file.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues for bug reports or feature requests, and pull requests for improvements.

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<p align="center">Made with ❤️ for Obsidian users who love to study and plan.</p>
