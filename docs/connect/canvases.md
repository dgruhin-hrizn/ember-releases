# Canvases

Small React apps Claude builds for you — dashboards, reports, trackers — that open beside the chat, keep their state, and can be fixed by Claude when they break.

A canvas is a small app Claude writes for you — a dashboard, a report, a tracker, a little tool — that opens beside the chat. It's a single React file, compiled on your computer with no network, kept in Ember's storage for this workspace.

Canvases are on by default ([`ember.canvas.enabled`](../settings/settings-browser.md#embercanvasenabled)). Claude is told how to build them at the start of each new chat.

## Ask for a canvas

Type `/canvas` in the message box and then what you want, for example `/canvas that charts this week's test failures by folder`. You can also just ask Claude for one in your own words.

When Claude saves the file, Ember compiles it and opens it beside the chat. Each time Claude saves it again, an open canvas reloads where it is, and a canvas you closed opens again beside the chat. Neither takes the focus from the message box. When you save the file in your own editor, an open canvas reloads; a closed one stays closed, and **Show Canvas** opens it.

To bring a canvas back without changing it, ask Claude to open it ("open the canvas again"). Claude has a `canvas_open` tool for that, which opens only canvases in this workspace's canvases folder.

A canvas can:

- show tables, stats, bar and line charts, cards and callouts, in your theme's colors;
- have buttons, text fields, selects and toggles, and remember what you entered — its state is kept in a file beside it;
- start a new chat with a prompt in the message box (not sent until you send it), or open a file in this workspace — only after you click something in the canvas.

A canvas can't reach the network, load other files, or open files outside the workspace.

## Browse your canvases

**Browse Canvases**

The list shows this workspace's canvases by title. Pick one to open it, or click the trash icon to delete it (Ember asks first).

## Source and canvas

- **Show Canvas Source** in an open canvas's title bar opens its `.canvas.tsx` file beside it.
- **Show Canvas** in a canvas file's title bar opens the canvas. It's there for the canvases in this workspace's canvases folder, including one you opened from the `ember` command line, not for other `.canvas.tsx` files.

Edit the source yourself or ask Claude to; the canvas reloads either way. A `// canvas-title: …` line at the top sets its title.

## When a canvas breaks

If a canvas doesn't compile or hits an error while running, its panel says so and shows the error, with:

- **Fix with Claude** — sends the error and the canvas to a new chat so Claude can fix it;
- **Show Source** (compile errors) or **Reload** (runtime errors).

When Claude saves a canvas that doesn't compile, Claude hears it right away: the save's result carries the error with its file, line and message, so Claude usually fixes it in the same turn without you clicking anything. Ember checks only what its own compiler sees (syntax and imports), not types, and says it once for each save. Errors a canvas hits while running still show only in its panel.

If a canvas stops responding — for example it loops forever — Ember closes its panel and tells you, with **Fix with Claude**, **Show Source** and **Reload Window**. It won't open that canvas on its own again until Claude saves a new version of it, or you open it.

> **Note:** To turn canvases off, set [`ember.canvas.enabled`](../settings/settings-browser.md#embercanvasenabled) to off. `/canvas` then tells you they're off.

---

[All documentation](../README.md)
