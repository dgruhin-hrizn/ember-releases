# Glossary

The words you meet on the way from a first chat to a merged pull request, in plain words, with where you see each one.

The words you meet on the usual way through Ember: open a folder, chat, approve a command, review the changes, work
in a worktree, open a pull request. They're in alphabetical order, each with where you see it. Words that only
Bonfire uses are on its own page: [Bonfire words](../plans/bonfire-howto.md#bonfire-words). A few more words are at the
[end of this page](#more-words).

### Allow in this chat

A button on an approval for an everyday command that always asks, such as `rm -rf dist`. The same kind of command
then runs without asking for the rest of that chat; nothing is saved. See [Allow in this chat](../chat/approvals.md#allow-in-this-chat).

### Always ask

Your own list of commands and tools that ask every time, whatever the permission level, for example
`Bash(git push:*)`. Edit it in **Settings › Permissions**. See [Manage your rules](../chat/approvals.md#manage-your-rules).

### Always run

The third button on an approval. It runs the command and saves a rule, such as `Bash(npm run test:*)`, so commands
like it run without asking from now on. Point at it to see the rule and where it's saved. See
[Choose the rule Always run saves](../chat/approvals.md#choose-the-rule-always-run-saves).

### Approval

What Claude asks before it runs a command Ember doesn't let it run on its own. It appears as a card in the chat that
starts **Needs you · approval**, with **Run**, **Skip** and often **Always run**. See [Approvals and Permissions](../chat/approvals.md).

### Background

The list titled **Background** just above the message box: everything a chat still runs on the side, such as
subagents and long commands, each with **Open** and **Stop**. There's no list when nothing runs. See
[The Background list](../chat/reading-a-chat.md#the-background-list).

### Base

The branch a branch started from and goes back into, such as `main`. A worktree chat counts its commits against it
("3 commits ahead of main"), and its pull request goes into it.

### Branch

The line of commits a chat works on. The chat names it once, on the [context line](#context-line). Click the
branch, there or on the Dashboard, for its menu: its tab, its chat and its pull request.

### Branch states

The one word Ember gives each branch with work in flight. It's the same on the Dashboard, the context line and the
dot on a tab. Most urgent first:

- **Needs you**: something waits for you: an approval, a question or a sign-in in a chat, a chat that stopped
  responding, or red CI, requested changes or conflicts on its pull request.
- **Working**: a chat is working on it, or something a chat started still runs in the background.
- **Waiting**: it waits on something other than you, such as CI that's still running, or a chat you paused.
- **Ready**: the next step is yours when you like: a pull request to merge, a finished chat to read, or commits with
  no pull request yet.
- **Merged**: its pull request merged. Remove its worktree or delete the branch.
- **Idle**: nothing going on.

### Card

A box in the chat with buttons, for something you can act on: an approval, a question, a plan, a stopped turn, a
finished worktree chat. A card that needs you has a gold edge and starts **Needs you**.

### Chat

A conversation with Claude, in the chat panel on the right. Each open chat has its own small tab at the top of that
panel. The list of all of them is **Chats**: see [Chats, Tabs and the Chat List](../chat/chat-tabs.md).

### CI

The checks your repository runs on a pull request, such as tests on GitHub Actions. Ember shows them beside the pull
request: running, passing or failing.

### Commands that always ask

Commands that can do damage that's hard to undo: force pushes, hard resets, recursive deletes, `sudo`, a download
piped into a shell, anything touching SSH keys or credentials. They ask at every level except **Run everything**,
and their card says why. See [Commands that always ask](../chat/approvals.md#commands-that-always-ask).

### Context line

The thin line at the top of a chat, under its tabs. It names the chat's branch, its pull request and its state, and
holds the one next step as a button, such as **Open PR**. See [Where the chat works](../chat/reading-a-chat.md#where-the-chat-works).

### Context window

How much of the chat Claude reads on every turn. The ring beside the send button fills as it does; click the ring for
the details and **Summarize chat**. See [The context ring](../chat/reading-a-chat.md#the-context-ring).

### Continue in a new chat

Starting a fresh chat from a short summary of this one, so a long chat stops slowing down. Ember offers it once, on
a card above the message box, when a chat gets long. It's also in a chat's menu under **Branch off**. Haiku writes
the summary unless **Note for a new chat** in Settings › Chats says Thorough. See
[Continue a long chat in a new one](../chat/reading-a-chat.md#continue-a-long-chat-in-a-new-one).

### Keep / Undo

How you accept or throw away what Claude changed in your files. Claude's edits go into your files straight away;
each changed file then waits for **Keep** or **Undo**, one at a time or all at once with **Keep all** and **Undo
all**. See [Review changes](../editing/review-changes.md).

### Main worktree

Your repository's own folder, the one you cloned. A chat that works there edits the files you have open. Compare
[its own worktree](#its-own-worktree).

### Its own worktree

A worktree other than the main one, usually one Ember made for a chat. A chat that works in its own worktree leaves
your main worktree untouched. See [Worktrees](../worktrees/worktrees.md).

### Message box

The box at the bottom of a chat where you write to Claude. Under what you write are the chat's mode and permission
level, its model and its account; the send button is at the bottom right. See [The Message Box](../chat/composer.md).

### Mode

What a chat may do with your message: **Agent** makes changes, **Plan** writes a plan first and changes nothing, **Ask**
only answers, **Debug** hunts down a bug. Pick it with the mode button under what you write in the message box, or
press Shift+Tab there. See [Pick a mode](../getting-started/first-chat.md#pick-a-mode).

### Needs you

Something waits for your answer. A card that needs you has a gold edge and starts **Needs you** (for example
**Needs you · approval**); the chat's tab, its row in Chats and its branch turn gold. **Needs You** in the
command palette lists every chat that waits on you, in every tab. See [Work across tabs and windows](../worktrees/across-tabs.md).

### Open in tab N

The button on a chat that runs in another tab of the window. A chat stays with the tab it was started in: here you
can read it, and **Open in tab 2** takes you to it to write. See [Work across tabs and windows](../worktrees/across-tabs.md).

### Permission level

How much Claude does without asking: **Ask before running commands**, **Run safe commands** (the default) or **Run
everything**. Settings picks the level new chats start at; the mode button in the message box shows a chat's level
("Agent · Safe commands") and can change it for that chat only. See [Choose a permission level](../chat/approvals.md#choose-a-permission-level).

### PR (pull request)

A request to merge a branch into its base, on GitHub. Ember opens it as a draft with **Open PR** and shows its CI and
review state beside the branch. See [Finish a worktree chat](../worktrees/worktrees.md#finish-a-worktree-chat).

### Question

What Claude asks when it needs you to choose. It appears as a card that starts **Needs you · question**, with lettered
options, **Other…** to answer in your own words, and **Skip**. Picking an option keeps what you typed in **Other…**
(greyed); click back into it and your words are the answer again. Typing in the message box answers it too.

### Review changes

Going through what a chat changed, file by file, beside anything Agent Review found. Click **Review** on the row above
the message box that counts the changed files. See [Review changes](../editing/review-changes.md).

### Rewind to here

The heading in the **⋯** menu of one of your messages: **Edit and resend** takes the chat back to that message, and
**Restore files…** puts your files back as they were then. See [Rewind a Chat](../chat/rewind.md).

### Rule

Instructions Claude reads in every new chat: your `CLAUDE.md` files and rules files. **Settings › Rules and memories**
shows what's loaded. A rule that lets a command run or makes it ask is a permission rule instead: see
[Always run](#always-run) and [Always ask](#always-ask). See [Rules and CLAUDE.md](../knowledge/rules.md).

### Run / Skip

The two answers on an approval: **Run** (Enter) runs the command once; **Skip** (Esc) doesn't run it, and Claude
carries on without it. Writing in the message box while an approval waits also skips it and sends your words to Claude.

### Send now

Sending a message while Claude is still working, so it reads it straight away instead of after the turn. The **Send
now** button sits beside the stop button; a message that waits instead is **queued** above the message box. See
[Send while Claude works](../chat/composer.md#send-while-claude-works).

### Subagent

A helper Claude starts for part of a task, with its own instructions and tools. It shows as a card in the chat, or in
the [Background](#background) list while it runs on the side. See [Subagents](../chat/reading-a-chat.md#subagents).

### Summarize chat

Shrinking a long chat to a summary, so it has room again. It's in the menu of the ring beside the send button; Claude
Code also does it by itself when the chat is nearly full.

### Tab

In the Ember app, each folder you have open is a tab along the top of the window, with a dot for its state. A
worktree opened in its own tab shows that worktree's files, branch and chats. See [How to use workspace tabs](../worktrees/workspace-tabs.md).

### This tab, tab N, not checked out

Where a branch is: **this tab** (the folder in front of you), **tab N** (another tab of the window has it open), the
main worktree, its own worktree, or **not checked out** (no folder has it; opening it makes a worktree first).

### To-do

One step of a plan. A plan lists its to-dos with their state (pending, in progress, done), and Claude ticks them off as
it builds. See [Plans](../plans/plans.md).

### Turn

One message of yours and everything Claude does to answer it. A finished turn ends with a line saying how long it
worked; the stop button stops the turn.

### Watch PR

Letting a chat keep an eye on a pull request: it fixes failing checks, conflicts and review comments until the pull
request is green. It never merges. See [Watch a pull request](../forge/babysit.md).

### Working line

The line under the chat while Claude works. It says what Claude is doing right now (**Running pnpm test**), what it
waits on (**Waiting on you: an approval**), or what still runs once the reply is done (**Working in the background: 1
subagent**). See [When the chat waits on you](../chat/reading-a-chat.md#when-the-chat-waits-on-you).

### Worktree

A second copy of your repository in its own folder, on its own branch, so a chat can work without touching your main
worktree. See [Worktrees](../worktrees/worktrees.md).

## More words

### Agent Blame

Marks beside each line in the editor that say which chat wrote it. See [Agent Blame](../editing/agent-blame.md).

### Agent Review

A read-only check in which Claude looks over changes for bugs (**Check for bugs**). See [Agent Review](../editing/agent-review.md).

### Bonfire

Ember's way of building a plan with several chats at once, off by default. Its words are on its own page:
[Bonfire words](../plans/bonfire-howto.md#bonfire-words).

### Canvas

A small app Claude writes for you, such as a dashboard or a report, that opens beside the chat. See [Canvases](../connect/canvases.md).

### Dashboard

Ember's start page for all your work in flight: what needs you first, what's working and what's done. See
[The Ember Dashboard](../worktrees/dashboard.md).

### Endpoint

A model server you add in **Settings › Models**, such as a local server for Tab predictions. See
[Your own endpoints](../models/own-endpoints.md).

### Forge

Ember's Git view for the folder a tab has open: its branch, changes, history and pull request. See
[How to use Forge](../forge/forge-howto.md).

### Hook

A command Claude Code runs on its own at a set moment, such as before a tool runs. Set them in **Settings › Hooks**.

### MCP server

A program that gives Claude more tools, such as access to a service. Manage them in **Settings › MCP servers**. See
[MCP servers](../claude-code/claude-code-honours.md#mcp-servers).

### Memory

Something you asked Claude to remember, for this project or for every chat. See [Memory](../knowledge/memory.md).

### Model bridge

A helper that lets you use models from other subscriptions in chat next to Claude. See [Model bridge](../models/model-bridge.md).

### Now

The first view in **Ember Work**, the side bar behind the Ember icon: what needs you and what's working. See
[Outside the Dashboard](../worktrees/dashboard.md#outside-the-dashboard).

### Side chat

A quick chat beside the current one, for a question that shouldn't sidetrack it. Start one with **New Side Chat**.
See [Side chats](../chat/chat-tabs.md#side-chats).

### Skill

A procedure Claude picks up on its own when it fits the task. Manage them in **Settings › Skills & Commands**.

### Tab predictions

Next-edit suggestions in the editor from a model you choose; press Tab to take one. See [Tab Predictions](../editing/tab-predictions.md).

---

[All documentation](../README.md)
