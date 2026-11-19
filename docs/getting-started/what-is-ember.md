# What is Ember?

Ember is a Claude workspace for VS Code and VSCodium: Ember.app, or the Ember extensions in your own editor.

Ember puts Claude next to your code: a chat panel where Claude reads, searches, edits and runs commands in your
project, plans you can review before anything is built, and tools to keep or undo every change Claude makes. It
runs on your Claude subscription through the Claude Code CLI on your computer, so your `CLAUDE.md` files, skills,
hooks, subagents, MCP servers and permission rules work in Ember just as they do in the terminal.

## Two ways to run Ember

| | What it is |
|---|---|
| **Ember.app** | A complete editor: a VSCodium build with Ember's extensions built in, its own updates, and a few changes to the editor itself. |
| **The Ember extensions** | The same extensions installed into your own VS Code or VSCodium. |

The extensions are:

- **Ember**: the chat panel, chats and plans, reviewing changes, Settings, Help and everything else on these pages.
- **Ember Tab**: next-edit predictions as you type (see [Tab Predictions](../editing/tab-predictions.md)).
- **Ember Light** and **Ember Dark**: the color themes, and **Ember**, the product icon theme that draws the editor's
  own icons in Ember's stroke style (the debugger's controls and breakpoints, the test states and the find toggles
  too). The themes carry Ember's colours into the editor's terminal (red is Ember's clay) and settings editor; in
  Ember.app the settings editor also gets serif headings and switches for on/off settings.

Almost everything works in both. Ember.app adds editor changes the extension API can't make, for example showing
the lines Claude removed inline above a change, **Keep · Undo** buttons on each change, and asking before you quit
while chats are still working. Help points these out where they matter.

> **Note:** Ember.app opens the Ember Dashboard in every window, over the editors it restored (Welcome, in a window with
> no folder). In VS Code or VSCodium, turn this on with [`ember.dashboard.showOnStartup`](../settings/settings-other.md#emberdashboardshowonstartup).

## What you need

- A Claude subscription.
- The Claude Code CLI (`claude`) installed and signed in. See [Sign In with Your Claude Subscription](sign-in.md).

## Where to go next

- [Install and Update Ember](install-update.md)
- [Your First Chat](first-chat.md)
- [Glossary](../glossary/glossary.md) for the words Ember uses.

---

[All documentation](../README.md)
