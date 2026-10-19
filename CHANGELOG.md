# Changelog

What changed in each Velin release, newest first. Versions follow semantic versioning. Changes land under **Unreleased** as they are made; `script/release` turns that section into the release's notes and names it after the version.

## Unreleased

## 0.2.0 — 2026-10-19

### Changed

- Go Back and Go Forward are now ⌘[ and ⌘], as in other Mac apps (they were ⌥⌘← and ⌥⌘→). To keep the old keys, add them to your shortcuts file.
- Board columns run the full height of the board, so they never resize as cards come and go, and a card can be dropped anywhere in one. A long column scrolls inside itself.
- A board's folded columns wait in one Folded column at the end, a row each: click one to unfold it, or drop a card on it to move the card there. Folding and unfolding animate.
- A board column's header has its own sort button and a delete button, shown while the mouse is over it; the ⋯ button is gone (a right-click still opens the menu). New Column sits above the columns, beside Sort and Show, and the board scrolls to the column it adds.
- A folded heading or list item ends in a small pill of three dots, on the middle of its text, that brightens under the mouse and unfolds on a click.
- Folds slide shut and open instead of jumping, their text fading out and in as they go, and the fold arrows show only beside the line under the mouse.
- Folds are remembered by the line they are on, so they stay on the right heading when a note is changed outside Velin.
- Task boxes are redrawn: a finer border, softer corners and a drawn check that fills in when you check one. They brighten under the mouse with a pointer, sit centred on the text at any size, and numbered tasks show their number before the box.
- Tasks are their own module, under Settings → Modules → Tasks. Switched off, checkboxes show as plain `[ ]` text.
- Check or Uncheck Task (⌘L, or a vimrc mapping to it) makes any line a task: a list item gets a box, other text gets `- [ ] `. With several lines selected, each one is checked, unchecked or made a task. The separate Checklist entry is gone; ⌘L does both.
- Tags sit on a soft wash of their colour with rounded corners, like inline code, a little shorter than the line, instead of a flat block.
- Inline code sits on a rounded background with a little room on each side, and its text takes a hint of the theme's accent, so it stands out even when the text and code fonts are the same.
- Words across Velin are one voice: menus, buttons and palette entries in title case, plain actions instead of "Toggle" (*Bold*, *Show or Hide Sidebar*), images instead of pictures, Shortcuts instead of Keys, Board for kanban boards, and messages that say what happened and what to do.
- `velin mcp` offers four tools instead of one per command: `commands` finds commands, `run` runs any of them, `snapshot` says what is on screen and `screenshot` shows the window. Agents stay quick and accurate; every command is still there through `run`.
- Whiteboards are now called canvases: *New Canvas* and *Canvas: …* in the palette, `canvas.*` commands, and their own Visual group in Settings → Modules. Existing whiteboards open as before and are saved as canvases; `board.*` commands still work.
- Settings files are grouped like the Settings window's sections: `general`, `theme`, `background`, `text`, `images`, `layout`, `app_icon`, `modules`, then each module's own (`editor`, `vim`, `files`, `periodic_notes`, `calendar`). Files written with the old keys are still read, and rewritten in the new layout once, with the original kept beside them as `settings.jsonc.before-moves`.
- Page width and full width moved from the Editor module to Appearance → Text.
- Light or dark is set only under Appearance → Theme (it was also in General).
- The page grips are fainter, fade in and out, both show when the mouse is over either, and keep up with a fast drag.
- PDF pages take the theme's colours: the window colour becomes the paper and the text colour the ink. Switch *Pages in the theme's colours* off under Settings → Modules → PDFs for pages as the PDF has them, turned dark in dark mode.
- Every colour Velin draws comes from the theme: the dimming behind dialogs, shadows, the light on the glass edge, the text on the delete button and the marks for problems in a file. Themes can set the new ones (`scrim`, `shadow`, `edge_light`, `on_error`); left out, they are worked out from the theme's other colours.

### Added

- Back and Forward work like a browser's: a tab opened to go somewhere closes again on Back, unless you pinned it, and Forward opens it again where it was, scrolled and with the cursor as you left it. Going somewhere new after going back drops the way forward.
- Drag a board's column by its header to move it.
- A board column can sort its cards its own way, over the board's sort. Cards put in order by hand still come first, and each column's sort button forgets its own order set by hand.
- On a board, vim's keys move between cards: h j k l, gg and G; Alt with h j k l carries the card. O opens it. Moving across, empty columns are passed over, and the board scrolls to show the card.
- The space menu (the space's name above the file tree) has Sample Space at its end, to open the sample space at any time, and Start the Sample Space Over…, which puts your copy in the Trash and opens a fresh one.
- Hide a note's properties (its frontmatter) with the eye on them (it shows while the mouse is over them) or ⌥⌘P (*Note: Show or Hide Properties*): they leave the note, out of reach of the cursor and of edits, while boards and dashboards still read them. Hidden, the eye waits at the end of the title row, showing while the mouse is over the title. Each note remembers this until it is set back to the setting.
- Typing `---` at the start of a note with hidden properties shows them, and so does a search or find result inside them. Properties typed into a note show, whatever the setting.
- Code blocks fold: the arrow beside a block's first line folds it to one row naming its language. With the cursor on that row, the block opens as source until the cursor leaves.
- Typing `[` after a list marker makes the task's box, `- [ ] `, with the cursor after it.
- In vim mode, commands mapped to `:` from visual mode act on the selected lines (`vmap t :toggletask<CR>`).
- The page width can be changed where you write: drag the grips beside the text (past the edge for full width), or use View → Wider Page (⌃⌘=), Narrower Page (⌃⌘-), Default Page Width and Full Width (⌃⌘0). The width is saved where it is set: the space's settings or your own.
- A note can have its own width with a `width:` property: `full`, `narrow`, `wide`, or a number of points. The grips and commands then change that note only.
- Sliders in Settings take the keyboard once pressed: the arrow keys step them (ten steps with Shift), Home and End go to their ends. Click a slider's number to type an exact one.
- The page's width shows beside the grip under the mouse: click it to type an exact width (points, or full, narrow, wide). View → Set Page Width… opens the same box.
- Settings → Files has a row for the character before the number of a name already taken ("Editing-1.png").

### Fixed

- On a board, a trackpad swipe keeps to the direction it starts in: scrolling a column up or down no longer slides the board sideways, and scrolling the board sideways no longer moves a column.
- A tab added to the open list in the sidebar fades in as the tabs below make room, instead of showing over one still moving.
- The tab switcher shows boards, sheets and dashboards as they look (columns and cards, cells, widgets) instead of their JSON tree.
- A board, dashboard or sheet changed so that one of its settings goes while another comes in at the same place is saved as valid JSON. Before, the file could be left broken.
- Opening the space that is already open (or starting the sample space over) no longer stops search with an index error. If another app holds a space's index, the status bar now says so plainly.
- A click on the left edge of a fold arrow or task box folds or checks it, instead of starting to drag the page width.
- Clicking a fold arrow twice quickly folds and unfolds, instead of selecting a word.
- Clicking a task's box twice quickly checks and unchecks it, instead of selecting a word and missing the second click.
- The cursor can move into a task's `- [ ]`: the box shows as typed while the cursor is in it, so it can be edited like any other syntax. Before, the box hid where the cursor really was.
- In vim mode the cursor keeps its shape when the `:` line opens, so mappings that run through it no longer flicker the cursor.
- Weeks start on the day set in Settings (or your Mac's region) from launch. Until a setting was changed, they started on Sunday, so weekly notes and the calendar could be a week off on Sundays.
- A double-click in a text box (a name, a slider's number, the page width) selects the word under it, a triple-click everything.
- A light Velin on a Mac set to dark had a dark border and shadow around its window.
- In vim mode, j, G and clicks reach the empty line after a note's last line break, so a note ending in empty lines can be written at its end.

### Removed

- The shaded edges at a board's sides, which cut off at the top.
- Done dates: ticking a task no longer adds a date to it. Dates already in notes stay as text.
- The `tasks` source for dashboards, one row per checkbox. The `notes` source still counts each note's tasks and those done. The Week dashboard template shows notes written and edited instead.
- New periodic notes no longer take the last one's unfinished tasks; they start from their template alone.

## 0.1.1 — 2026-10-17

### Fixed

- Choose another place… copies into the folder you pick (it has to be empty, as a folder made with New Folder is), instead of making a folder inside it.
- Choose another place… looks and behaves like a link.

## 0.1.0 — 2026-10-17

First release, for Macs with Apple silicon.
