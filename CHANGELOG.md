# Changelog

What changed in each Velin release, newest first. Versions follow semantic versioning. Changes land under **Unreleased** as they are made; `script/release` turns that section into the release's notes and names it after the version.

## Unreleased

## 0.5.0 — 2026-11-07

### Changed

- `velin import <space>` now copies the space beside the original, as `<name> (Velin)`, and converts the copy; the original stays as it was. Pass `--to <folder>` to choose where the copy goes, or `--in-place` to convert the space itself as before.
- The finance dashboard template keeps its data in plain CSV files beside the dashboards (transactions, categories, debts, balances, rules and imports) instead of a database, so you can read and change them anywhere and each change shows in the file's history. Categorising in the Month table changes that row of the file, the rules sort transactions by the first one that matches, in the file's order, and the Week template counts money spent from the same file. Finance dashboards made before keep working on their database.
- The Cyberpunk group of themes is now called Digital.
- Tables in notes sit on a soft panel, like callouts, with quiet lines between the rows and more room in the cells.
- A note starts further down the window, and stays where it is when the top bar comes and goes.
- The top bar's button stays quiet while the top bar is kept in view, like the status bar's.
- Mermaid diagrams have a new look: soft shapes that let the background show through, your note's font, and colours that all come from the theme.
- Lines in Mermaid diagrams run in right angles with their labels beside them, and edges from one node join into a single line.
- Sequence diagrams show their participants once, at the top, and class diagrams leave out empty parts.
- Actors in sequence diagrams are cards with a person beside the name, user journeys show scores as numbered dots, and pie charts draw as rings with the total in the middle.

### Added

- Dashboards can change CSV files: an editable table or a button works on a CSV file as it does on a database. Only the rows that change are rewritten, so the rest of the file stays exactly as it was.
- Habits: right-click a day to mark it missed or skipped (or press m or s). Missed counts as a day not done but shows it is dealt with; skipped is left out of rates and streaks, and takes its share off a week's or month's count. Days to come can be skipped ahead, and a day's count turns to the accent once every habit is dealt with.
- Velin tells you when a newer version is out: at launch it checks, and the status bar offers the update. One click downloads it, checks that it is signed and notarized, and puts it in place; Restart opens the new version. Turn the check off in Settings → General, or check by hand with Check for Updates in the Velin menu.
- Canvases show their file too: Cmd-E, or *Tree* and *Source* in the status bar, opens the canvas as a tree or as text in the same tab, and Cmd-E brings it back.
- Icons in Mermaid diagrams: Font Awesome and other icon names (`fa:fa-car`, `::icon(fa fa-book)`, `@{ icon: "fa:user" }`) draw as matching Lucide icons in flowcharts, mindmaps, architecture, tree view and use case diagrams. Names with no match, like brand logos, are left out.
- Velin draws Mermaid Wardley maps, Cynefin diagrams and railroad diagrams in EBNF, ABNF, PEG and Mermaid's own primitives.
- Velin draws Mermaid use case, swimlane, agent flow and event modeling diagrams.
- Velin draws Mermaid requirement, C4, architecture and block diagrams.
- Velin draws eight more kinds of Mermaid diagram: packet, kanban, tree view, radar, sankey, treemap, Ishikawa and Venn.
- Mermaid class diagrams group classes in namespaces, nested too, and entity relationship diagrams group entities in subgraphs.
- Mermaid pie charts take `donutHole`, `legendPosition` and `highlightSlice`; Gantt charts draw vertical markers, a today line and compact rows, and take `tickInterval`.
- Mermaid git graphs run `TB` and `BT`, line up parallel commits, and can hide branch names and commit labels; XY charts run sideways and show a legend and value labels.
- Mermaid timelines run downwards with `timeline TD`, quadrant points take their own styles, and mindmaps can colour by depth.
- Mermaid class diagrams draw two-way relations and lollipop interfaces, state diagrams draw concurrent regions, and `classDef`, `class`, `:::` and `style` now work in class, state and entity relationship diagrams.
- Mermaid sequence diagrams draw boundary, control, entity, database, collections and queue participants, participants created and destroyed along the way, central connections, half arrows and `autonumber` with a start and step.
- Mermaid flowchart nodes can take a label in brackets and settings in `@{ }` together, as in `a["Draft"]@{ shape: doc }`.
- Mermaid flowcharts draw every named shape, like `A@{ shape: doc }`, with the text centred in the part of the shape that holds it and lines meeting the shape itself; small picture shapes such as the hourglass and bolt carry their label beneath. They also follow `linkStyle` and show Markdown in labels written in backticks.
- Background images can be pixelated: the Pixelate slider under Settings → Background → Image turns any image, a theme's painting included, into square blocks of colour.
- Many more painting themes, each in dark and light with colours from the painting, from Bruegel’s *Hunters in the Snow* to Monet’s *Impression, Sunrise*.
- Bug recorder: switch the module on and Cmd-Shift-U, or the bug button in the sidebar, freezes the window as it is, asks what went wrong, and saves a note with a screen capture to a folder you choose.

### Fixed

- Enter on an empty nested list item moves it out a level instead of clearing it; only an empty top-level item ends the list.
- Numbered lists keep their numbers in order: adding an item in the middle renumbers the ones after it, and an indented list starts again at 1.
- The quick switcher goes away when a shortcut opens a note or another tab comes forward, instead of staying over it.
- In a weekly note's template, `{{monday}}`, `{{sunday}}` and the other days now fall in the note's own week when weeks start on Monday; before, Monday came out as Tuesday and Sunday as the Monday before.
- The sample space's weekly template no longer repeats the note's name as a heading under its title.
- Following a link to a note Velin hadn't listed yet, like one an assistant had just written or one in a hidden folder, could empty that note. It now opens the note as it is.
- Making, copying, pasting, renaming or moving a file never replaces another file of that name, even one another app makes at the same moment.
- A file Velin has to write in place (one with a second name, or in a folder Velin can't add to) gets its old text back if the write fails partway.
- Renaming a note keeps the spaces around its name in links written as `[[ Name ]]`.
- With the image frame on, a picture in its own tab rounds its corners to the frame's, and PDF pages wear the frame too.
- Icon names in Mermaid flowchart labels no longer show as text.
- In a weekly note's bar, each day's name and date sit centred in their box, with room around them, whether or not the day has a note.
- Lines into a Mermaid subgraph go round what is inside it, instead of running through it.
- Tables wider than the note wrap their cells to fit, instead of running off the screen.
- Mermaid shapes written the long way, like `A@{ shape: cyl, label: "Data" }`, draw as that shape instead of a diamond with the raw text.
- Mermaid trapezoids draw correctly with another slanted shape later on the same line.
- Package visibility `~` on class members in Mermaid diagrams stays as written.
- Dates along a Gantt chart's axis no longer run into each other, and `until` can name a task further down.
- Group names in Mermaid diagrams stay readable where a line passes under them.
- Cloud and bang nodes in Mermaid mindmaps look like a cloud and a burst.
- Diagram and chart blocks no longer show a fold button that did nothing; folding the heading above still hides them.
- Lines in Mermaid diagrams that join several nodes to several others meet in one junction, and a line into a node nested in groups comes round the outside and straight in instead of running along the borders.
- Boards with hundreds of cards scroll smoothly.
- Shortcuts are drawn crisp and even in every font, in tooltips, the command palette and Settings.
- Typing while another app, an AI or git changes the same note no longer loses either side. Changes in different places merge, word by word. Where both touch the same words, the file's version stays and yours goes to a copy beside it, “Note (your changes)”, and the status bar says so. Two panes on one note merge the same way, and canvases keep unsaved changes in a copy.
- Long stretches of typing without a pause are saved every few seconds, not only when you stop.
- Saving can no longer leave a half-written file: after a crash, a full disk or a power cut the file is the old version or the new one, whole. Links stay links, and files keep their permissions, tags and creation date.
- A note that disappears for a moment, as during a sync or a checkout, goes back to saving by itself.
- Velin no longer writes over a file it can't read, or one that stopped being text outside Velin.
- Canvases say when they can't be saved and try again, and a canvas broken outside Velin is left as it is until it is fixed.
- When a save fails, Velin says why in plain words, keeps your changes and saves by itself once it can. Closing a tab or quitting asks before letting them go.
- In a copy of a space from another app, links by full path point into the copy, so editing through them leaves the original alone.

### Security

- Velin no longer trusts website certificates from emSign intermediates that browsers have stopped trusting, when it fetches web data or checks for updates.

## 0.4.0 — 2026-10-29

### Changed

- Habits label the days with two letters (Mo, Tu, We), like the calendar and periodic notes, so Tuesday and Thursday no longer look alike.

### Added

- Habits that aren't kept every day: keep one on some days of the week (only those days are due), or a number of times a week or month (any day counts, and each week shows how many of its times are done, more than asked included). Right-click a habit's name to set it; how it is kept shows in a badge beside the name. Streaks count those days, or weeks and months in a row.
- Habits in notes: embed a habits file with `![[Sleep.json]]` and the note shows the days of its period. A daily or weekly note shows each habit's boxes as the habits file draws them, today's band and each day's count included, ticked with a click; a monthly note a mark per day and the share kept; a quarterly or yearly note the share as a bar; any other note this week. Several in one note line up, day under day, and a name cut short shows whole under the mouse. Fold an embed with the arrow beside it, like a heading, to keep just its title and today's ticks. Put it in your weekly template and every week starts with its habits.
- Habits work with vim's keys: h j k l between days and habits, w and b a week, 0 the habit's first day, $ or t back to today, gg and G the first and last habit. x ticks, o adds a habit, r or cw renames it, dd removes it, Alt-j and Alt-k move it, u and Ctrl-R undo and redo. Alt-↑ and Alt-↓ move a habit too.

### Fixed

- In habits, the arrow keys stay on days that can be ticked: they stop at today, and at the day a habit was first kept.

## 0.3.1 — 2026-10-26

### Fixed

- Pasting text copied from some apps, old files or a terminal no longer closes Velin. Their old kinds of line breaks become ordinary ones, and notes that already have them open as they should.

## 0.3.0 — 2026-10-26

### Changed

- A board's **+** no longer opens a new note: you name the card at the top of the column and stay on the board. Return makes it, the card sliding down to its place, and lets you type the next, Cmd-Return makes it and opens its note, Escape stops. **n** does the same in the column you are in.
- Clicking a board card selects it instead of opening its note. Open a note with a double-click, Enter, or the arrow that shows on the card under the mouse.

### Added

- Habits: keep habits in a file and tick them day by day, a row per habit and a column per day. Set a goal (the days it runs and the share to reach) by clicking it, with lines in the days where it starts and ends, and see how it stands, with each habit's rate and streak. Click a name to rename it, drag it to reorder the habits, and remove one with the bin beside it. Make one with *New Habits File* in the command palette.
- Board cards can be selected together: Cmd-click across columns, Shift-click for a range in a column, Cmd-A for all. Drag, Alt-arrows or the right-click menu move them all at once, and Backspace deletes their notes. Dragged, the other selected cards glide in to stack behind the one you hold, and when you let go they glide from there to their places.
- Datafall, a new theme with an image behind the window: neon light falling through the dark, in nine colours. Pick the colour from the swatches under the theme cards. Your own themes can come in several colours too.
- Line numbers can be shown or hidden from the margin beside the text: move the mouse there and click the button that fades in, or right-click for the menu. *Show or Hide Line Numbers* is in the palette too.

### Fixed

- Undo on a board puts cards moved to another column back, the property in their notes too, and Redo moves them again. Folding and unfolding a column is no longer undone, and a folded column opens when an undo changes what is in it.
- Dragging the page width, a selection or anything else held by the mouse to the window's edge no longer brings a hidden sidebar, top bar or status bar in. Dragging a tab or file there still does.

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
