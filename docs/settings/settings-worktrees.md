# Settings: Worktrees

Every setting in Settings › Worktrees: type, default, values and what it does.

These settings are in **Settings › Worktrees** (and in your `settings.json`).

### `ember.agentBranchPrefix`

Prefix for the branches of chats that run in a new git worktree (e.g. `ember/fix-login`).

- **Type:** string
- **Default:** `"ember/"`
- **Scope:** User or workspace

### `ember.worktrees.chatMovesToTab`

Where a chat goes when it moves into a worktree. By default Ember asks: **New Tab** or **New Window**. The tab you're in is never switched to the worktree, so what you had open stays where it is. You can always move a chat with **Move to its tab**.

- **Type:** one of the values below
- **Default:** `"ask"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"ask"` | When Claude moves a chat into a worktree, Ember asks whether to open the worktree in a new tab or a new window, and the chat carries on there. The question is a card in the chat; Stay here (or closing it) keeps the chat in the tab it's in. |
| `"always"` | Without a question, a chat moves to its worktree's own tab when Claude moves it into a worktree, and when you start a new chat in a new worktree (forks and versions stay to be compared). |
| `"claude"` | Without a question, and only when Claude moves it into a worktree with EnterWorktree, to the worktree's own tab. |
| `"never"` | Chats stay in the tab they started in, even when they work in a worktree (the explorer and Git keep showing this tab's folder). Move to its tab still moves one when you ask. |

### `ember.worktrees.claudeMayEnter`

Let Claude make a worktree, move the chat into it and leave it again by itself (Claude Code's `EnterWorktree` / `ExitWorktree`), just as Claude Code does on its own. The same chat keeps going, and (with **When a chat goes into a worktree** on its default) Ember asks whether to open the worktree in a new tab or a new window, where the explorer and Git show the chat's branch: you never have to open a second chat and paste your request again, and the tab you're in stays as it is.

A **worktree** is a second copy of your repository in its own folder, on its own branch. Work there doesn't touch the folder you have open, so several chats can work at once without moving each other onto the wrong branch.

**On (default):** when your project's instructions want work on its own branch, Claude makes the worktree and carries on there.

**Off:** a chat always stays in the folder it started in. Claude can't move it; if your project wants a worktree, Claude asks you to start a new chat from the **Where** menu.

Whether Claude makes a worktree at all comes from your project's own instructions (`CLAUDE.md`, rules, memories). This only decides whether it's allowed to. A project can set this in its `.vscode/settings.json`, and that value wins over yours.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.worktrees.maxCount`

Most worktrees Ember keeps for chats. Past it, the overflow and 4 more are removed, unused ones first, then the least recently used; each goes forced and keeps its branch. Never one a chat is running in, or one you kept when you archived its chat.

- **Type:** number
- **Default:** `25`
- **Range:** 1 to 500
- **Scope:** User or workspace

### `ember.worktrees.maxSizeGb`

Most disk space (GB) Ember's worktrees may use; 0 = no limit.

- **Type:** number
- **Default:** `50`
- **Range:** 0 to 1000
- **Scope:** User or workspace

### `ember.worktrees.root`

Folder new chat worktrees go in, one sub-folder per repository. Empty: `~/.ember/worktrees`. Worktrees already made stay where they are.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
