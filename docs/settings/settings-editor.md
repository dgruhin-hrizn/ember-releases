# Settings: Editor

Every setting in Settings › Editor: type, default, values and what it does.

These settings are in **Settings › Editor** (and in your `settings.json`).

### `ember.blame.gutter`

Agent Blame: mark the lines Ember wrote with a thin bar in the gutter, one colour per chat (also **Ember: Toggle Agent Blame**). Hover a line to see which chat wrote it.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.blame.statusBar`

Agent Blame: when the cursor is on a line Ember wrote, show that chat's title in the status bar (click it to open the chat).

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.blame.tool`

Agent Blame: give Claude the read-only `agent_blame` tool, so it can tell which chat wrote lines of a file and why they are there.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.chat.emptyStateTips`

Show a rotating tip under the quickstart buttons of a new chat.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.modeProposals`

Claude can propose switching a chat's mode (for example to Plan for a large, unclear task, or to Agent once a plan is agreed). A switch to Agent takes effect at once; any other from the next turn. New chats pick up a change.

- **Type:** one of the values below
- **Default:** `"auto"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"ask"` | Ask with Switch / Stay (the card waits until you answer or write) |
| `"auto"` | Switch without asking to a mode that lets Claude do less (Agent → Plan → Ask); a mode that lets it do more is still asked (the default) |
| `"off"` | Claude never proposes a mode |

### `ember.review.formatOnFinish`

When a chat's turn ends, format the files it edited in that turn (with the file's formatter). The formatting becomes part of the pending change. Files with unsaved edits, `.emberignore`d files and files without a formatter are left alone.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.review.hunkPills`

Show a small **Keep · Undo** pill above the change under the caret or the mouse (the mouse only while `editor.hover.enabled` is on), and the first change (at most 3 per editor; needs the `editorInsets` proposal — on in Ember.app). Where pills show, the per-change CodeLens rows are hidden; the file's row stays.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.review.inlineRemoved`

Show the lines Claude removed inline, above each change (needs the `editorInsets` proposal — on in Ember.app). Off: a note with the removed lines on hover.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.review.nextFileOnKeep`

After **Keep File** or **Undo File** in an editor, open the chat's next changed file at its first change.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.selectionToolbar`

Show **Add to Chat** and **Quick Edit** on a text selection.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.selectionToolbarPlacement`

Where the selection toolbar (`ember.selectionToolbar`) appears. The toolbar needs editor features only Ember.app turns on.

- **Type:** one of the values below
- **Default:** `"selection"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"selection"` | Under the selection's last line, as a line of its own (the lines below move down while it shows). |
| `"corner"` | In the editor's floating toolbar, bottom right. |

### `ember.statusBar.show`

> **Deprecated.** The chat panel has no status bar now: the branch and where it works are on its context line (click the branch for its menu), and your `statusLine` has its own row under the composer ([`ember.statusBar.statusLine`](settings-general.md#emberstatusbarstatusline)).

No longer used.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.statusBar.showBranch`

> **Deprecated.** The chat panel has no status bar now: the branch and where it works are on its context line (click the branch for its menu), and your `statusLine` has its own row under the composer ([`ember.statusBar.statusLine`](settings-general.md#emberstatusbarstatusline)).

No longer used.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.statusBar.showContext`

Show the chat's context window in the composer's ring. Off: the ring holds only your plan's limits.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.statusBar.showEnvironment`

> **Deprecated.** The chat panel has no status bar now: the branch and where it works are on its context line (click the branch for its menu), and your `statusLine` has its own row under the composer ([`ember.statusBar.statusLine`](settings-general.md#emberstatusbarstatusline)).

No longer used.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.statusBar.showRepo`

> **Deprecated.** The chat panel has no status bar now: the branch and where it works are on its context line (click the branch for its menu), and your `statusLine` has its own row under the composer ([`ember.statusBar.statusLine`](settings-general.md#emberstatusbarstatusline)).

No longer used.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.terminal.commandK`

⌘K (Ctrl+K on Windows and Linux) in the terminal asks what the command should do and puts the command Claude writes on the prompt line, without running it. Off: the shortcut clears the terminal again.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

---

[All documentation](../README.md)
