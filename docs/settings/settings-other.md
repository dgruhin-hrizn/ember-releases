# Settings: Only in settings.json

Every setting in Settings › Only in settings.json: type, default, values and what it does.

These settings have no row in Ember's Settings: change them in your `settings.json` (Preferences: Open User Settings (JSON)).

### `ember.accounts.default`

The Claude account chats use when nothing else picks one: no account of their own, none for the window or tab, none for the folder. Empty: your main account (Claude Code's own `~/.claude`). Swap it from the account item in the status bar, **Ember: Switch Default Claude Account**, or Settings › Accounts. Chats on the default move on their next message and continue the same conversation.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.accounts.list`

Your Claude accounts besides the main one, and the folders each is for. Manage them in **Settings › Accounts**: each signs in through Claude Code's own `claude auth login` in its own config folder, and shares your chats, settings, rules, memory, skills and MCP servers with the main one. Ember never reads a token.

- **Type:** array
- **Default:** `[]`
- **Scope:** Application (all windows and profiles)

### `ember.accounts.lowAt.fiveHour`

An account is low at this percent of its 5-hour limit. Empty: 92%.

- **Type:** integer or null
- **Default:** `null`
- **Range:** 1 to 100
- **Scope:** Application (all windows and profiles)

### `ember.accounts.lowAt.weekly`

An account is low at this percent of its weekly window.

- **Type:** integer
- **Default:** `90`
- **Range:** 1 to 100
- **Scope:** Application (all windows and profiles)

### `ember.accounts.whenLow`

What Ember does when a Claude account's usage runs low. Only accounts assigned to the same folder, signed in and below both thresholds are ever offered or switched to. A switch takes effect on the chat's next message and continues the same conversation.

- **Type:** one of the values below
- **Default:** `"notify"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"notify"` | Tell me, and offer to wait for the reset or turn on extra usage. |
| `"ask"` | Also offer to move the chat (or Bonfire's next to-do) to another account assigned to that folder. |
| `"switch"` | Move it by myself to another account assigned to that folder (asks you to acknowledge the terms note once). |

### `ember.agreements`

Working agreements every chat keeps, by name: `true` turns one on, `false` off. A repository's `.ember/repo.json` `agreements` decides first. Every agreement is off by default: Ember adds no branch, worktree or pull-request rules of its own, and process comes from the repository's CLAUDE.md and rules.

- **Type:** object
- **Default:** `{}`
- **Scope:** User or workspace

### `ember.babysit.replyToComments`

Let **Watch PR** reply on GitHub to the review comments it addressed. Off: it changes code and pushes, and never posts.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.babysit.updateStrategy`

How **Watch PR** brings a conflicting pull request up to date with its base branch. Only `rebase` ever pushes with `--force-with-lease`; nothing ever pushes with `--force`.

- **Type:** one of the values below
- **Default:** `"merge"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"merge"` | Merge the base branch into the PR branch and push normally |
| `"rebase"` | Rebase the PR branch onto the base branch and push with --force-with-lease |

### `ember.dashboard.showOnStartup`

When a window opens with the Ember Dashboard (a window with no folder opens Welcome instead). Ember.app defaults to `always`.

- **Type:** one of the values below
- **Default:** `"never"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"always"` | Every window opens with its Dashboard, pinned at the far left, over the editors it restored. If you close it, that window keeps it closed until Ember next starts. |
| `"emptyWindows"` | Only a window with no open editors opens the Dashboard. |
| `"never"` | Don't open it, or Welcome, on startup. |

### `ember.dashboard.summaryModel`

Model that writes the short summary under **Where you left off** on a worktree tab's Dashboard (one call per finished turn, on your Claude subscription). `off` shows the chat's last message instead.

- **Type:** string
- **Default:** `"haiku"`
- **Scope:** User or workspace

### `ember.debug.dragLog`

Write the chat's drag-and-drop events to the Ember log (for diagnosing drops). `EMBER_DRAG_LOG=1` in the environment turns it on too.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.forge.enabled`

Use Forge, Ember's git. Off: Forge never opens, its Source Control sections go and the built-in Source Control stays; Ember's Forge buttons, links and keys show Source Control instead. Forge opens only when you ask for it either way.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.git.keepClaudeOut`

Keep Claude out of commits and pull requests. A commit, tag or merge message, or a pull request title or description, that names Claude or Anthropic is sent back to Claude to write again, at every permission level. No `Co-Authored-By` line or "Generated with" footer is added, whatever Claude's own `attribution` setting says, and commit messages Ember drafts leave Claude out too. A name inside a path, branch or package (`CLAUDE.md`, `.claude/`, `claude/my-branch`) is fine.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.help.tool`

Give Claude a read-only `ember_help` tool that searches Ember's help pages, so it can answer how-to questions about Ember itself (settings, shortcuts, Bonfire, Forge…) with links into Help. It never asks for approval and changes nothing.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.keepAwake`

Keep this Mac awake while chats work or a Bonfire run is scheduled, then let it sleep again. macOS only. A closed lid on battery still sleeps.

- **Type:** one of the values below
- **Default:** `"whileWorking"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"whileWorking"` |  |
| `"off"` |  |

### `ember.learn.corrections`

When you correct Claude the same way a third time ("never use git stash", "Opus for everything"), in one chat or across several, Ember offers to save it as a rule or memory, so you don't have to repeat yourself. Nothing is saved until you click **Save**; **Dismiss** never asks about that correction again.

- **Type:** one of the values below
- **Default:** `"ask"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"ask"` | When you give Claude the same correction a third time, a card in the chat offers to save it as a rule or memory |
| `"off"` | Never offer to save corrections |

### `ember.plans.openOnReady`

Open a plan beside the chat as soon as it is ready (the chat keeps focus).

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.plans.reviewOnFirstEdit`

When a plan's build makes its first file edit, open Review Changes where the plan tab is, once per build. Not when the chat runs without asking (Run everything).

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.review.deepDefault`

Agent Review starts as **Deep** (thorough, more turns and higher effort) instead of **Quick**.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.review.includeUntracked`

Agent Review includes files git doesn't track yet.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.review.onCommit`

Agent Review: Check for Bugs after each commit (it reviews the commit just made, in the background).

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.version.statusBar`

Show Ember's version at the far right of the status bar. Click it for About Ember. Turned off, the Dashboard item's hover, About Ember and **Settings › General › Version** still show the version.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

---

[All documentation](../README.md)
