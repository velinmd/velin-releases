# Changelog

## 0.7.0 — 2026-11-13

### Changed

- Deleted files and folders wait a day before they go to the Trash, the space's .trash, or for good. ⌘Z outside a note, or Undo in the status bar, puts them back and opens their tabs again; on a board, ⌘Z brings deleted cards back in place.
- ⌘Z outside a note also takes back moves, renames, new notes and folders, copies and pastes, with ⌘⇧Z to do them again.
- A card moved into another column goes where that column's sort puts it, wherever it's dropped; only moving a card within its column places it by hand. If that place is out of view, the column scrolls to show it land.
- Cards on a board reorder more calmly: they stay solid as they travel, those going further start in a short cascade and pass each other side by side, rising cards over sinking ones, and they slide in from behind a column's edge rather than over it.
- Deleting one file no longer asks first; folders and several files at once still do (Settings → General).

### Added

- Recently Deleted, at the foot of the sidebar, lists what was deleted in the last day, with Put Back and Empty.
- Sync keeps a space the same on all your Macs, end-to-end encrypted: the server can't read your files or their names. Changes arrive in under a second and keep syncing while Velin is closed; a cloud in the status bar shows how it stands, and a lost device can be removed. Settings → Modules → Sync.
- Archive board cards with E, from a card's menu, or a whole column at once: they leave the board but keep their notes and column. Archived above the columns shows them, to drag back or unarchive.
- A card moved to another column notes when, in its note (`status_changed`), so a column can sort with the most recently moved cards first, or those there longest.
- Dates with a time in a note's properties show in your local time, readably (`Yesterday 18:40`); the exact date shows when you edit it.
- Search a board's cards with ⌘F: cards that don't match fade away, and each column counts its matches.
- On a board, Shift with the arrow keys selects more cards.
- Dragging a card or column near a board's edge scrolls the board or the column; Escape puts a dragged card back.

### Fixed

- A new card's name wraps onto more lines as you type it, breaking where it will on the card, instead of scrolling sideways.
- A card dragged on a board keeps its own font and look, and lands from exactly where it was dropped. The gap it opens is its exact size: in another column it opens where the card will land (the column scrolling to show it at its foot), the one it left closes where it was, and on letting go it stays until the card covers it.

### Security

- SQLite is updated to 3.54.1: a database file crafted together with its write-ahead log could make Velin read leftover memory.

## 0.6.0 — 2026-11-07

### Changed

- A new version shows as a button beside Settings at the foot of the sidebar, instead of in the status bar: click it to update, and again to restart.

### Added

- History keeps earlier versions of every file in your space, outside it. ⌘⌥Y shows a note's versions and what changed, restores one with a click, and brings deleted files back.
- Help → Report a Problem… (or ⌘⇧U) sends us what went wrong, with a screen capture if you keep it ticked.
- After Velin quits unexpectedly, the next start offers to send the crash report, once.
- Help → Terms of Use and Third-Party Notices.

## 0.5.0 — 2026-11-07

### Breaking

- `velin import` now converts a copy of the space, beside the original, and leaves the original as it was. Add `--in-place` to convert the space itself, as before.

### Changed

- New finance dashboards keep their data in plain CSV files instead of a database. Finance dashboards made before keep working as they are.
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

### Changed

- Habits label days with two letters (Mo, Tu, We), like the calendar.

### Added

- Habits that aren't kept every day: on some days of the week, or a number of times a week or month.
- Habits in notes: embed a habits file and a periodic note shows the days of its period, ticked in place.
- Habits work with vim's keys.

### Fixed

- In habits, the arrow keys stay on days that can be ticked.

## 0.3.1 — 2026-10-26

### Fixed

- Pasting text with old kinds of line breaks, from some apps, old files or a terminal, no longer closes Velin.

## 0.3.0 — 2026-10-26

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

### Fixed

- *Choose another place…* copies into the folder you pick, instead of making a folder inside it.

## 0.1.0 — 2026-10-17

The first release, for Macs with Apple silicon.
