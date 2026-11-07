# Changelog

What changed in each Velin release, newest first.

Your notes are plain `.md` files and stay that way: whatever changes below, they open in any editor, on any computer.

Velin is in alpha, so a release may change the files Velin keeps for itself: settings, boards, canvases, sheets, dashboards and the `.velin/` folder in a space. Each release lists those changes first, under **Breaking**, with what to do about them.

## 0.5.0 — 2026-11-07

### Breaking

- `velin import` now converts a copy of the space, beside the original, and leaves the original as it was. Add `--in-place` to convert the space itself, as before.

### Changed

- New finance dashboards keep their data in plain CSV files instead of a database. Finance dashboards made before keep working as they are.
- The Cyberpunk themes are now called Digital.
- Tables in notes sit on a soft panel, with more room in the cells.
- A note starts a little further down the window and stays put when the top bar comes and goes.
- Mermaid diagrams have a new look: soft shapes, your note's font and the theme's colours, with lines at right angles.

### Added

- Velin tells you when a new version is out and updates itself in one click. Turn the check off in Settings → General.
- Dashboards can change CSV files, through editable tables and buttons. Only the rows that change are rewritten.
- Habits: mark a day missed or skipped. Skipped days are left out of rates and streaks.
- Canvases open as a tree or as text, like other data files (⌘E).
- Many more kinds of Mermaid diagram, and icons inside them.
- Many more painting themes, each in dark and light.
- Background images can be pixelated, under Settings → Background → Image.
- Bug recorder module: freeze the window, say what went wrong, and save it as a note with a screen capture.

### Fixed

- Typing while another app, an assistant or git changes the same note no longer loses either side. Changes merge; where both touch the same words, yours go to a copy beside the note.
- Making, copying, renaming or moving a file never replaces another file of that name.
- Following a link to a note Velin hadn't listed yet could empty that note. It now opens as it is.
- Enter on an empty nested list item moves it out a level, and numbered lists keep their numbers in order.
- In weekly templates, the days of the week fall in the note's own week when weeks start on Monday.
- Wide tables wrap their cells to fit the note.
- Large boards scroll smoothly.

## 0.4.0 — 2026-10-29

### Breaking

- Nothing in Velin's own files changed.

### Changed

- Habits label days with two letters (Mo, Tu, We), like the calendar.

### Added

- Habits that aren't kept every day: on some days of the week, or a number of times a week or month.
- Habits in notes: embed a habits file and a periodic note shows the days of its period, ticked in place.
- Habits work with vim's keys.

### Fixed

- In habits, the arrow keys stay on days that can be ticked.

## 0.3.1 — 2026-10-26

### Breaking

- Nothing in Velin's own files changed.

### Fixed

- Pasting text with old kinds of line breaks, from some apps, old files or a terminal, no longer closes Velin.

## 0.3.0 — 2026-10-26

### Breaking

- Nothing in Velin's own files changed.

### Changed

- A board's **+** names a new card at the top of the column and keeps you on the board, instead of opening a new note.
- Clicking a board card selects it. Open its note with a double-click, Return or the arrow on the card.

### Added

- Habits: a file of habits ticked day by day, with goals, rates and streaks. Make one with *New Habits File*.
- Select several board cards and move or delete them together.
- Datafall, a theme with neon light falling behind the window, in several colours.
- Show or hide line numbers from the margin beside the text.

### Fixed

- Undo on a board puts moved cards back, the property in their notes too.
- Dragging to the window's edge no longer brings in a hidden sidebar or bar.

## 0.2.0 — 2026-10-19

### Breaking

- Settings files are grouped like the Settings window. Old settings files are still read and rewritten once in the new layout; the original stays beside them as `settings.jsonc.before-moves`.
- Whiteboards are now canvases. Existing whiteboard files open as before and are saved as canvases. Commands are `canvas.*`; `board.*` still works.
- Dashboards lose the `tasks` source. The `notes` source still counts each note's tasks.
- Ticking a task no longer adds a done date. Dates already in notes stay as text.
- New periodic notes no longer carry over the last one's unfinished tasks.
- Go Back and Go Forward are ⌘[ and ⌘]. To keep the old keys, add them to your shortcuts file.
- `velin mcp` offers four tools in place of one per command: `commands`, `run`, `snapshot` and `screenshot`.

### Changed

- Board columns run the full height of the board, and folded columns wait together at the end.
- Folds slide open and shut, and stay on the right heading when a note changes outside Velin.
- Task boxes are redrawn, and Tasks is its own module.
- ⌘L makes any line a task, or checks and unchecks it.
- Tags and inline code sit on soft rounded backgrounds.
- PDF pages take the theme's colours. Switch it off under Settings → Modules → PDFs.
- Every colour Velin draws comes from the theme.

### Added

- Back and Forward work like a browser's.
- Drag a board column by its header to move it; each column can sort its cards its own way.
- On a board, vim's keys move between cards.
- Hide a note's properties with the eye beside them (⌥⌘P).
- Code blocks fold.
- Change the page width where you write: drag the grips beside the text, or give a note its own `width:`.
- Open the sample space from the space menu at any time, or start it over.

### Fixed

- Weeks start on the day set in Settings from launch, so weekly notes and the calendar are no longer a week off on Sundays.
- A board, dashboard or sheet could be saved as broken JSON when one setting replaced another. It now saves as valid JSON.
- Opening the space that is already open no longer stops search.
- On a board, a trackpad swipe keeps to the direction it starts in.

## 0.1.1 — 2026-10-17

### Breaking

- Nothing in Velin's own files changed.

### Fixed

- *Choose another place…* copies into the folder you pick, instead of making a folder inside it.

## 0.1.0 — 2026-10-17

The first release, for Macs with Apple silicon.
