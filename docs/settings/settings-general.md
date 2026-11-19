# Settings: General

Every setting in Settings › General: type, default, values and what it does.

These settings are in **Settings › General** (and in your `settings.json`).

### `ember.autoTitles`

After a chat's first reply, name it with a short generated title (one tiny, tool-less model call billed to your subscription). Renamed chats are never changed.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.chat.density`

How much of Claude's work a chat shows. A preset overrides `ember.chat.expandToolCalls`, `ember.chat.expandThinking` and `ember.chat.expandSubagents`; **Custom** uses them.

- **Type:** one of the values below
- **Default:** `"compact"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"compact"` | Read, search, edit and shell calls (and short lines between them) fold into one row each run; a finished turn folds into "Worked for …"; everything starts collapsed. |
| `"balanced"` | Read and search calls (and short lines between them) fold into "Explored …" rows; a finished turn folds into "Worked for …"; everything starts collapsed. |
| `"detailed"` | Every tool call on its own row; tool calls, thinking and subagents start expanded; nothing folds. |
| `"custom"` | Explored rows; the Expand, Fold finished turns and Group narration settings below decide the rest. |

### `ember.chat.expandSubagents`

Show subagent cards in chats expanded, with each subagent's work, instead of collapsed. Used when `ember.chat.density` is Custom.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.chat.expandThinking`

Show Claude's thinking in chats expanded instead of collapsed under "Thought". Used when `ember.chat.density` is Custom.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.chat.expandToolCalls`

Show tool calls in chats expanded (the command, diff and output) instead of one collapsed line each. Used when `ember.chat.density` is Custom.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.chat.fileWork`

How Claude works with files. **Ember** asks Claude to use its file tools, sends shell commands that only read or edit files to them, and turns the rest of its shell work into reviewable cards; **Claude Code** keeps the plain terminal behavior. New chats get the instruction to Claude (and an open one after its next restart).

- **Type:** one of the values below
- **Default:** `"ember"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"ember"` | Claude reads, searches and edits with its file tools (shell commands that only read or edit files are sent to them), and Ember shows shell work as cards: diffs with Keep and Undo for files a command changed, Explorer marks, Read and Search cards, git, test and package results. |
| `"claudeCode"` | Claude works exactly as in the terminal: shell output as is, and no diffs or Undo for files a command changed. |

### `ember.chat.foldTurns`

Fold a finished turn's work (tool calls, thinking, narration) into one "Worked for …" row above Claude's reply. Used when `ember.chat.density` is Custom.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.chat.groupNarration`

Fold short lines Claude writes between grouped tool calls into the group instead of letting them split it. Used when `ember.chat.density` is Custom.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.chat.htmlVisualizations`

Run ```html blocks in chats as visualizations: in a sandboxed frame with no network access, links disabled. Off: they show as code. Claude is told it can use them in chats started (or restarted) after the change.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.chat.jumpRail`

Show a short tick for each of your messages down the chat's left edge. Point at one to see your message and the start of Claude's answer; click it to go to that turn.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.chat.loadWarning`

Warn in the chat when Claude's background commands leave your computer overloaded (a high load average or little free memory), with a way to stop them. Each Ember window checks its own chats. Off by default; the warning's **Don't Show Again** turns it back off.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.chat.maxWidth`

Reading width of the chat transcript. `0` (the default) lets the chat fill its panel; a number from 320 to 4000 limits the transcript to that many pixels, centred.

- **Type:** one of the values below or any
- **Default:** `0`
- **Scope:** Application (all windows and profiles)

### `ember.chat.textSize`

Text size of the chat transcript and composer (a scale).

- **Type:** number
- **Default:** `1`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `0.85` |  |
| `1` |  |
| `1.15` |  |
| `1.3` |  |

### `ember.chats.showHookRuns`

Which hook runs show as rows in a chat.

- **Type:** one of the values below
- **Default:** `"problems"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"all"` | A row for every hook Claude Code runs. |
| `"problems"` | Only hooks that blocked something, changed a call or failed. |
| `"off"` | No hook rows. |

### `ember.composer.editRevert`

When you edit and resubmit an earlier message: whether the files changed after it go back to how they were before it. Asking offers your last answer first; **Don't Ask Again** keeps that answer here.

- **Type:** one of the values below
- **Default:** `"ask"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"ask"` | Ask whether to revert the files changed after the message, with your last answer as the default button. |
| `"always"` | Always revert them to how they were before the message. |
| `"never"` | Never revert: the files stay as they are. |

### `ember.composer.whileRunning`

What Enter does while a chat is running: queue the message behind the turn, or send it into the turn now. ⌥Enter (Alt+Enter) does the other; ⌘Enter (Ctrl+Enter) stops the turn and sends.

- **Type:** one of the values below
- **Default:** `"queue"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"queue"` | Enter queues the message: it is sent when the running turn ends. ⌥Enter (Alt+Enter) sends it into the turn now. |
| `"steer"` | Enter sends the message into the running turn now. ⌥Enter (Alt+Enter) queues it. |

### `ember.ideTools`

Give Claude Ember's read-only IDE tools: the Problems list, your open editors and selection, and recent terminal output. Takes effect in new chats.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.notifications.enabled`

macOS notifications when a chat finishes ("Done • <chat>") or needs your approval (with Run / Skip). Clicking one focuses VSCodium and opens the chat.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.notifications.sound`

Play the Ember tone with notifications.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.notifications.soundPath`

Custom sound file to play instead of the Ember tone: any format `afplay` plays on macOS, `paplay` on Linux, a `.wav` file on Windows.

- **Type:** string
- **Default:** empty
- **Scope:** User or workspace

### `ember.notifications.usageWarnAt`

Warn in the chat once a Claude usage limit (5-hour, weekly, or a model's weekly limit) is at this percent or more. The notice names the limit, how full it is and when it resets, once per limit until it resets (the context ring shows it after that). Reaching a limit is always shown.

- **Type:** number
- **Default:** `80`
- **Range:** 50 to 99
- **Scope:** User or workspace

### `ember.notifications.when`

When to send notifications.

- **Type:** one of the values below
- **Default:** `"unfocused"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"unfocused"` | Only while VSCodium is not the focused app. |
| `"always"` | Also for chats in the background while you work in VSCodium. |

### `ember.notifications.writer`

Haiku reads the end of the chat and writes the notification, using your Claude subscription. Turn it off to get Ember's fixed wording. Chats on your own models, such as local or custom endpoints, are never sent to Claude, so their notifications stay templated.

- **Type:** one of the values below
- **Default:** `"haiku"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"haiku"` | Claude Haiku writes each notification from the chat's own facts, using your Claude subscription. |
| `"off"` | Ember's fixed wording. |

### `ember.promptSuggestions`

After each turn, show Claude's guess at your next prompt in the empty chat input (Tab to use it). Uses the chat's prompt cache, so it is nearly free.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.searchConversations.ownModels`

Also give the conversation-search tool to chats on your own models (Settings › Models). Off by default: those chats would send excerpts of your other conversations to that provider.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.searchConversations.tool`

Give Claude a read-only tool that searches your earlier chats in this project by what was said (Ember's local index). Matching excerpts go to the chat's model like anything Claude reads. Not offered to subagents. Takes effect in new chats.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.statusBar.statusLine`

Off by default. On: run your Claude Code `statusLine` command (from `~/.claude/settings.json`, or the project's settings in a trusted workspace) and show its output in its own row under the chat's composer. Off while `disableAllHooks` is on.

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace

### `ember.tabs.dashboard`

Ember app: the Dashboard has a tab of its own, first in the tab strip and pinned, with no chat. Off: the Dashboard opens inside the tab you're in.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.tabs.enabled`

Ember app: show open repositories and worktrees as tabs in the window's title bar, so one window holds several of them. Each tab is still its own workspace.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.tabs.openFoldersIn`

Ember app: where a folder or worktree that Ember opens goes (Open in New Ember Tab, Open tab on a branch). Hold `Alt` (`⌥`) when choosing to get the other one.

- **Type:** one of the values below
- **Default:** `"tab"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"tab"` | A folder or worktree Ember opens becomes a new tab in this window. |
| `"window"` | A folder or worktree Ember opens gets a window of its own. |

### `ember.tabs.restore`

Ember app: which tabs open again when Ember starts. Sleeping tabs use no memory until you click them.

- **Type:** one of the values below
- **Default:** `"all"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"all"` | Every tab that was open comes back open. |
| `"active"` | Only each window's front tab comes back open; the others come back asleep and open when you click them. |

### `ember.tabs.style`

Ember app: how a workspace tab shows its repo. Every style keeps the repo whole and opens a shrunk tab when you point at it. Also in a tab's right-click menu (Tab Style).

- **Type:** one of the values below
- **Default:** `"repoLead"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"repoLead"` | Repo lead: the repo first, then the pull request, wt and the branch. |
| `"colourTag"` | Colour tag: the repo as a tinted tag; tabs of one repo share its tint. |
| `"repoGroups"` | Repo groups: tabs gathered behind one label per repo. Your own order is kept underneath. |
| `"stacked"` | Stacked: the repo, pull request and wt on a small top line, the branch underneath. |

### `ember.update.mode`

Updates to Ember itself. Ember looks for a new version when it starts and about every two hours.

- **Type:** one of the values below
- **Default:** `"notify"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"notify"` | Tell me when a new version of Ember is out, with Install and Restart and its release notes. |
| `"auto"` | Download new versions in the background and install them when Ember quits. |
| `"off"` | Never check for new versions. |

---

[All documentation](../README.md)
