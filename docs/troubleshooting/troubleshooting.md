# Troubleshooting

Fixes for common problems — a waiting card you can't see, a blank window when a worktree opens, approvals that keep asking, a notice that went, claude not found, sign-in, a stuck index — and where to find logs and diagnostics.

Start with the section that matches what you see. If nothing here helps, gather the log and diagnostics described at the end.

## Claude is waiting and I can't see why

When Claude waits on you, the line under the chat says so: **Waiting on you: an approval**, **Waiting on you: a
question**. The approval or question itself is always on screen:

- It sits in the chat, where Claude asked. If that spot is folded away, inside a closed subagent or scrolled out of
  view, it shows just above the message box instead.
- In the message box, Alt+↑ jumps to the newest one.
- You can also answer by writing in the message box: your message skips the command (or answers the question) and
  goes to Claude. Writing never approves anything; see [Write instead of answering](../chat/approvals.md#write-instead-of-answering).

If you can't find the chat that waits, run **Needs You**: it lists every chat that waits on you,
in every tab and window. A chat that isn't on screen also sends a notification, and the chat panel's icon counts what
waits there.

## The window went blank when a worktree opened

When a chat moves to its worktree's new tab, the tab you're in stays in front, saying **Opening** *name* **in a new
tab…** with the Ember flame and the seconds so far. The new tab shows in the row of tabs at once, with the flame, and
comes forward only once its chat is there. Click it to go there sooner. If its window doesn't open, your tab says so,
with **Retry**.

If a new tab still comes up blank, you can make new tabs show straight away instead, as Ember did before. Create an
empty file named `reveal-at-once` in the `ember-tabs` folder of Ember's data folder (on macOS
`~/Library/Application Support/Ember/ember-tabs`, on Windows `%APPDATA%\Ember\ember-tabs`, on Linux
`~/.config/Ember/ember-tabs`), then restart Ember. Delete the file to go back. Please also report what you saw.

To stop chats moving to a new tab at all, set **When a chat goes into a worktree** in Settings › Worktrees
([`ember.worktrees.chatMovesToTab`](../settings/settings-worktrees.md#emberworktreeschatmovestotab)) to **never**. See [Claude makes a worktree itself](../worktrees/worktrees.md#claude-makes-a-worktree-itself).

## It keeps asking me to approve commands

- **Raise the level.** The mode button in the message box names the chat's permission level ("Agent · Safe
  commands"). Its menu sets the level for this chat only; Settings › Permissions
  ([`ember.permissions.level`](../settings/settings-permissions.md#emberpermissionslevel)) sets the level new chats start at. See
  [Choose a permission level](../chat/approvals.md#choose-a-permission-level).
- **Save a rule.** **Always run** on the approval saves a rule, such as `Bash(npm run test:*)`, so commands like it
  stop asking. Click **⌄** beside it to pick a wider rule. See [Choose the rule Always run saves](../chat/approvals.md#choose-the-rule-always-run-saves).
- **Allow it for this chat.** A command that always asks, such as `rm -rf dist`, offers **Allow in this chat**
  instead: the same kind of command runs without asking until the chat ends.
- **A rule that looks right still asks.** The approval says which rule and why in its one line, for example because
  the shell moved to another folder. See [When a saved rule still asks](../chat/approvals.md#when-a-saved-rule-still-asks).
- **Some commands always ask** below Run everything, whatever rule you saved: force pushes, hard resets, recursive
  deletes, `sudo` and the like. See [Commands that always ask](../chat/approvals.md#commands-that-always-ask).

## A command I expected to run asks

At **Run safe commands**, tests, builds and read-only commands run on their own only where Ember can tell they stay
in this chat's project. They ask, and the approval says where, when:

- the shell is in another folder, in `node_modules` or in a hidden folder such as `.git` (`cd node_modules/x && npm
  test`);
- git reads another folder (`cd /tmp/x && git status`), since git runs programs a repository's settings there name;
- the command reads a hidden file in your home folder, however the path is written (`~/.netrc`,
  `/Users/you/.netrc`), or a keychain, saved passwords or cookies;
- a path is filled in by `$(…)` or a variable, or leads out of the project through a link, unless Ember can tell it
  stays inside.

Run it once with **Run**, or see the full table in [The same in every mode](../chat/approvals.md#the-same-in-every-mode).

## Where did the notice go?

Ember's notes about a chat sit just above its message box, and each stays only as long as it's useful:

- A note that confirms what you just did goes by itself after five seconds on screen.
- A note that's only worth knowing becomes a line in the chat, where it stays.
- A note about something under way goes when that step ends.
- A notice that needs you, or says something failed, stays until you answer it or press **Dismiss**.

Up to three show at once; older ones fold into **N more notices**. A notice you dismissed doesn't come back with the
same words. When the chat panel is closed or covered, the answer to a click shows as a notification in the bottom-left
corner instead, and anything that needs you also counts on the chat panel's icon, with **Show chat**. A notification
that asks you something stays until you answer it. See [Notices above the message box](../chat/reading-a-chat.md#notices-above-the-message-box).

## Ember can't find `claude`

Ember runs your own `claude` CLI so chats bill to your Claude subscription. Settings › Accounts › **Claude CLI** shows the path and version it uses, or **Not found — set a path.**

1. Check Claude Code is installed: run `claude --version` in a terminal.
2. If it runs there but Ember can't find it, paste its full path into **Claude CLI** ([`ember.claudePath`](../settings/settings-account.md#emberclaudepath)). Empty means Ember looks on your login shell's `PATH` and in the usual install folders.

**Open Settings › Accounts**

## Sign-in problems

Settings › Accounts shows the account the CLI is signed in to, or **Not signed in**. See [Sign In with Your Claude Subscription](../getting-started/sign-in.md) to sign in.

- **Settings that sign in another way** lists settings that make Claude Code use an API key or another provider instead of your subscription. Ember never writes them; edit the file it names if you don't want them. Ember's own chats still run on your subscription.
- **Run diagnostics** has Claude Code check its installation, settings files and updates. Nothing is changed.

## The codebase index is stuck

Open Settings › Indexing. The row for this folder shows its state — **Indexing** with a percentage, **Synced**, **Out of sync** or **Error** with the message.

- **Sync** reads only the files that changed.
- **Rebuild** starts over: it re-reads and re-embeds every file.
- **Delete Index** removes it; **Index this folder** starts again.
- **Semantic** shows how much of the index has vectors. **Pause meaning-based indexing** stops sending code to the embeddings model; keyword search stays current.

If the line says **Waiting while a chat uses the embeddings endpoint**, a chat is using a model on the same local server; indexing carries on when it's done.

**Open Settings › Indexing**

See [Codebase Index](../knowledge/codebase-index.md) for how the index works.

## The embeddings server doesn't answer

Search keeps working by keyword without it. To find the cause:

1. Open Settings › Models › **Roles**. The result of the last test of the embeddings model shows under its picker, with ✕ and the error when it failed.
2. For a local server, check it's running and that the endpoint's **Base URL** and port match it. Click **Edit** on the endpoint, then **Test again**.
3. For a hosted provider, check the key: **Edit** the endpoint and paste it again.

See [Your own endpoints](../models/own-endpoints.md).

## A Bonfire run seems stuck

The Bonfire page's progress line says what the run is doing:

- **Paused · …** — the run is paused. Click **Resume all**.
- **Waiting for the usage reset at …** — Ember is pacing your plan's usage. Under the pace bar it says when it waits: if a to-do would take usage past the limit shown, Ember waits for the reset and then carries on. **Resume now** starts new to-dos straight away.
- A to-do showing **Waiting for you: …** needs an answer or a decision from you; open it to see what.

## Logs

- **Show Ember Log** opens Ember's log in the Output panel. To see more detail, run VS Code's **Developer: Set Log Level…** and set Ember's log to Debug or Trace.
- Each approval, question or MCP input writes a line to that log when it arrives (**ask raised**) and when it is answered or goes away (**ask settled**, with how long it waited). The lines name the chat, the tool and counts, never the command, the question or your answer.
- Each notice above the message box writes a line to that log when it shows (**notice shown**) and when it goes (**notice gone**, with how long it was up and whether you closed it, pressed one of its buttons, Ember took it down or it cleared itself). The lines name the chat, the kind of notice, its class (whether it confirms, reports progress, informs, needs you or reports an error) and its buttons, never what the notice says. A note that went into the chat as a row says **in transcript**; one you closed before that came again with the same words, and so wasn't shown, writes **notice held back**.
- The model bridge has its own log: **Show log** on the **Bridge** row in Settings › Models.
- Chats in Debug mode keep the logs your instrumented code sends them: **Show Debug Logs**.

## Copy diagnostics

**About Ember**

In About Ember, **Copy diagnostics** copies a short summary for a bug report: Ember's version and build, what it runs on, whether you're signed in and your plan (not your email), the chat model, the roles' endpoints, the model bridge's state and the index. Your home folder is shortened in paths. **Open logs folder** opens the folder with Ember's log files.

## VS Code's own tools

- **Developer Tools** — Help › **Toggle Developer Tools** (command **Developer: Toggle Developer Tools**). Its Console shows errors from the editor's windows, Ember's panels included.
- **Process Explorer** — Help › **Open Process Explorer** (command **Developer: Open Process Explorer**). It shows each process's CPU and memory, which helps when something is slow.

---

[All documentation](../README.md)
