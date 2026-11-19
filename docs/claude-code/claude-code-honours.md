# What Ember honours from Claude Code

Every chat runs Claude Code with your own settings files, so CLAUDE.md, skills, hooks, subagents, MCP servers, plugins, permissions and the rest work in Ember as in the terminal.

Every Ember chat is a Claude Code session, started through the Claude Agent SDK on the `claude` CLI you signed in
to. Ember starts it with Claude Code's own setting sources (your user settings, the project's settings and your
local project settings), and Claude Code adds your organization's managed settings on top. So what you set up for
Claude Code in the terminal counts in Ember too, and what you change in Ember's Settings is saved where the
terminal reads it.

This page lists each part, what Ember does with it, and where you manage it. For what Ember adds or does
differently, see [What Ember changes, and why](claude-code-changes.md).

## Settings files

Claude Code reads its settings from these files, the first one winning a clash:

| Where | File | Who it affects |
| --- | --- | --- |
| Set by your organization | managed settings | Everyone on this computer; can't be changed in Ember |
| This project, only me | `.claude/settings.local.json` | Only you, only in this folder |
| This project, shared with the team | `.claude/settings.json` | Everyone who uses the repository |
| Me, all projects | `~/.claude/settings.json` | Only you, in every project |

Settings › Accounts › **Settings files in effect** lists the files for the folder Settings shows, with
"(none)" for the ones that don't exist yet.

Wherever a Settings row writes a Claude Code setting, it shows which file the value comes from and lets you pick
where to save it. Settings › **All Claude Code settings** lists every Claude Code setting with the value in
effect, the file that decides it and what it overrides, and lets you change it in the file you choose.

**Open All Claude Code settings**

### Your organization's settings

If your organization manages Claude Code on this computer, its `managed-settings.json` (and the files in
`managed-settings.d/`) win over every other file. Settings › Accounts › **Managed by your organization**
lists the keys it sets, each with **Open file**. Values your organization sets can't be changed in Ember.
Its block (deny) rules always win, over any allow rule in your own files, and Ember's own file reads, @-mentions and
@Web keep to them too. Settings › Permissions lists them, locked, under **Blocked by your organization**.
If one of your organization's files can't be read, or isn't valid JSON, none of its settings are in effect (in Ember
and in the terminal), and Settings › Permissions shows a warning naming the file.

**Open Settings › Accounts**

## CLAUDE.md and rules

Claude Code loads `CLAUDE.md`, `CLAUDE.local.md`, your own instructions for all projects and the rule files in
`.claude/rules` into every chat, as it does in the terminal. Settings › **Rules and memories** lists them in the order
Claude Code loads them, with their size and buttons to create the ones you don't have. See [Rules and CLAUDE.md](../knowledge/rules.md) and
[Memory](../knowledge/memory.md).

**Open Rules and memories**

## Skills and slash commands

Your skills and custom slash commands (from your user folder, the project, plugins, MCP servers and claude.ai)
work in Ember's chats: type `/` in the message box. Settings › **Skills & Commands** lists them by where they come
from, and lets you create, edit and delete your own and the project's.

Each skill has a **Claude sees** choice: **Name and description**, **Name only**, **Only when you type /name** or
**Hidden**. It's the same setting `/skills` changes in the terminal:

- **Save skill visibility in** picks the settings file these choices are saved in. Open chats pick a change up at
  once.
- Under **Other skills**, **Another skill** hides a skill by name (as you type it after `/`), for example a
  built-in one. Type the name and click **Hide it**.

**Open Skills & Commands**

## Hooks

Hooks you set up in Claude Code run in Ember's chats: before and after tools, when a turn ends, and at the other
hook events. Settings › **Hooks** lists them from every settings file, with every hook type, and lets you add,
edit, test and remove them. New chats pick up changes.

**Turn off all hooks** saves Claude Code's `disableAllHooks`. Plugins' hooks and the status line stop too. Saved for
"This project, only me", it turns hooks off in this folder only. Your organization's managed hooks keep running:
only its own settings can turn them off.

When a hook runs before or after a tool, the chat can show a row for it. Choose which runs show with
[`ember.chats.showHookRuns`](../settings/settings-general.md#emberchatsshowhookruns): **All**, **Only blocks, changes and failures** (the default) or **Off**.

**Open Settings › Hooks**

## Subagents

Your subagents (from `~/.claude/agents/`, `.claude/agents/` and plugins) and Claude Code's built-in ones are
available in every chat; a subagent shows as a card in the chat while it works. Settings › **Subagents** lists
them, creates and edits your own, and has **Start chats as agent…**, which makes new chats and the terminal run as
that agent.

**Open Settings › Subagents**

## MCP servers

The MCP servers Claude Code knows for this folder start in Ember's chats too: yours, the project's `.mcp.json`,
plugins' servers and your claude.ai connectors. Settings › **MCP servers** shows each one's status and lets you add,
remove, turn off for this folder, reconnect and sign in. Changes reach new chats; **Update open chats** gives them
to open chats without a restart.

- **Approve all project servers**: servers in a project's `.mcp.json` run commands from the repository, so Claude
  Code asks before it starts them. Turn this on to approve every one (saved for "This project, only me"); its tag
  names the settings file that decides it, or `default`.
  **Forget my allow / don't-allow choices** makes Claude Code ask again.
- **Worktrees**: on macOS and Linux, Claude Code keeps your allow / don't-allow answers in the repository's main
  worktree, so a server you answered there isn't asked about again in its worktrees (on Windows each worktree keeps
  its own answers). Ember tells you a server waits for approval once per repository in a window, not in every chat.
  Settings opened from a worktree saves your answer where Claude Code reads it: in the main worktree, for the whole
  repository, and each server's row says so. A server whose definition on this branch differs from the main
  worktree's is answered for this worktree only, so your answer never decides the other program. If a branch changes
  a server you approved in the main worktree, Claude Code still starts it (approvals go by name): Ember says so once,
  with **Review**.
- **Advanced** › **Load my claude.ai connectors**: servers you connected on claude.ai appear in Settings and in
  chats. Turning it off saves a setting that turns them off for you; if any settings file turns them off, they stay
  off.
- **Advanced** › **Blocked servers** and **Allowed servers**: Claude Code's own server lists. Blocked wins.
- **Advanced** › **Only organization-allowed servers**: when your organization turns this on in its managed
  settings, only the servers it allows can start. Only your organization can turn it on, so Ember shows it without
  a switch.

**Open Settings › MCP servers**

## Plugins and marketplaces

Claude Code plugins add skills, commands, agents, hooks and MCP servers, and they load in Ember's chats. Settings ›
**Plugins** runs `claude plugin` for you:

- The **Plugins** tab turns plugins on and off, installs and uninstalls them, and has **Update all** and
  **Disable all plugins**.
- The **Marketplaces** tab adds, updates and removes the marketplaces plugins come from, each with **Update
  automatically**.

New chats pick up changes. In a chat, `/reload-plugins` and `/reload-skills` load them into that chat at once.

**Open Settings › Plugins**

## Output styles

Your output style decides how Claude writes its replies. Settings › General › **How Claude answers** › **Output
style** picks it (Claude Code's `outputStyle`, so the terminal uses it too). Below it, **Output styles** lists the
built-in styles, your own (`~/.claude/output-styles/` and `.claude/output-styles/`) and plugins' styles, and creates
and edits style files. New chats use a change.

## Status line

Claude Code's `statusLine` command can show its line in Ember too. Turn on **Show my status line** in Settings ›
General ([`ember.statusBar.statusLine`](../settings/settings-general.md#emberstatusbarstatusline)); Ember then runs your command for the chat on screen and shows its
output under the message box. The **Status line** row below it edits the command, padding and refresh for the
settings file you pick, with **Preview** and **Ask Claude to write one**. It doesn't run while **Turn off all hooks**
is on.

## Permissions

Claude Code's permission rules count in every chat, from every settings file:

- **Allow** rules: what Claude runs without asking. Settings › **Permissions** › **Always run** lists them, and an
  approval card's **Always run** adds to them.
- **Ask** rules: what Claude asks about every time, whatever the permission level. Settings › Permissions ›
  **Always ask**.
- **Deny** rules block a tool or command in Ember's chats as in the terminal. Ember also keeps to `Read` deny rules
  in its own features: the codebase index leaves those files out and Ember's browser won't open them. Deny rules
  for web tools cover **@Web** too. Edit deny rules in the settings files: Settings › Permissions › **Advanced**
  opens each one.
- **Working directories** (Claude Code's extra folders) and the **sandbox** are under Permissions › **Advanced**.

If your organization allows only its own rules, Settings › Permissions says so and lists your rules as ignored.

`disableBypassPermissionsMode` is honoured as well: where any settings file (your organization's or your own) turns
Bypass permissions off, the **Run everything** level isn't available and chats run safe commands only. See
[Approvals and Permissions](../chat/approvals.md).

**Open Settings › Permissions**

## Everything else

Other Claude Code settings in your files (the model, environment variables, sign-in settings, privacy switches and
the rest) still count. Rows for many of them are spread through Ember's Settings where they fit; every one of them
is in Settings › **All Claude Code settings**.

---

[All documentation](../README.md)
