# Ember documentation

These pages are Ember's in-app Help (**Help › Ember Help**), as Markdown. They describe the latest released version; the app's own Help always matches the version you have installed.

New here? Start with [What is Ember?](getting-started/what-is-ember.md), [Install and Update Ember](getting-started/install-update.md), [Sign In with Your Claude Subscription](getting-started/sign-in.md) and [Your First Chat](getting-started/first-chat.md).

In these pages a name in bold after "run" is a command: run it from the Command Palette. A name like `ember.update.mode` is a setting: find it in Ember's Settings, or in the [Settings reference](settings/settings.md).

## Start here

| Page | What it covers |
|---|---|
| [Ember Help](home/home.md) | Start here: what Ember Help covers, how to search it, and where to begin. |

## Getting started

| Page | What it covers |
|---|---|
| [What is Ember?](getting-started/what-is-ember.md) | Ember is a Claude workspace for VS Code and VSCodium: Ember.app, or the Ember extensions in your own editor. |
| [Install and Update Ember](getting-started/install-update.md) | Install Ember.app on macOS, Windows or Linux, and choose how it updates itself. |
| [Sign In with Your Claude Subscription](getting-started/sign-in.md) | Ember runs on your Claude subscription through the local claude CLI. Sign in, check your account, and keep Claude Code healthy. |
| [Use More Than One Claude Account](getting-started/accounts.md) | Sign in to a second Claude account, for example Work beside Personal. Pick which account each folder, window or chat uses, switch without losing anything, and choose what happens when one runs low. |
| [Import Your Settings](getting-started/import-settings.md) | Bring settings, keyboard shortcuts, snippets and extensions from VS Code or VSCodium, and another editor's rules and commands into Claude Code. |
| [Find Your Way Around](getting-started/layout.md) | Where the Chat and Chats views live, one-step layouts, your own layouts, and swapping sides. |
| [Your First Chat](getting-started/first-chat.md) | Send your first message, pick a mode and a model, keep or undo Claude's edits, and build from a plan. |

## Chat

| Page | What it covers |
|---|---|
| [The Message Box](chat/composer.md) | Modes, permission level, models, thinking, Fast and effort; queueing or sending now while Claude works; editing and resending; suggestions; text size and density. |
| [Give Claude Context](chat/context.md) | Point Claude at files, code, problems, terminals, commits and more with @, Add to Chat, quotes of its replies, side chats, attachments and drag and drop. |
| [Chats, Tabs and the Chat List](chat/chat-tabs.md) | Work in several chats at once: tabs, side chats, the chat list, search, find, outline, chats in editor tabs, compare, export and save as a skill. |
| [Read a Chat](chat/reading-a-chat.md) | What you see while Claude works: your messages and its replies, the message ticks for jumping back, folded turns, tool lines, edits, thinking, the working line, notices, the turn footer, subagents and the Background list, hook rows, the context line, the status line, the context ring and continuing a long chat in a new one. |
| [Approvals and Permissions](chat/approvals.md) | Choose how much Claude does on its own, answer approvals, see which commands always ask, and save rules with Always run (and choose which rule). |
| [Usage, Limits and Notifications](chat/usage-limits.md) | Know how much of your Claude plan you've used: limit warnings, the usage dashboard, limit resets, and notifications when a chat finishes or needs you. |
| [Rewind a Chat](chat/rewind.md) | Go back to an earlier message: put your files back as they were, or edit the message and send it again. |
| [Fork a Chat](chat/forks.md) | Branch a chat to try another approach: forks remember where they came from, can run in their own worktree, and can be compared so you keep the best one. |
| [Try It Several Ways, Keep the Best](chat/compare-tries.md) | Send one prompt to two to four models, or to one model several times, each on its own branch in its own worktree, compare their changes side by side against the base, keep the best one, and let Ember remove the others' worktrees. |
| [When Ember Closes Mid-Run](chat/resume.md) | Ember asks before quitting while chats work, and interrupted chats can pick up where they left off. |
| [Bring Chats from Another Folder](chat/move-chats.md) | Moved, renamed or cloned a repository? Bring its chats, plans and Bonfire history to the new folder. |
| [Outputs](chat/outputs.md) | Every canvas and plan Claude made, in one list. Find them by tab, repository or everywhere, open them, see which chat made them, pin, rename, delete and tidy. |
| [Delete Old Chats](chat/delete-old-chats.md) | Clean up a folder's old chats now or on a schedule, keep the ones you pin, and control Claude Code's own transcript cleanup. |

## Editing with Ember

| Page | What it covers |
|---|---|
| [Inline Edit](editing/inline-edit.md) | Ask Claude to change or write code right where you are, in the editor or in the terminal. |
| [Review changes](editing/review-changes.md) | Keep or undo what an agent changed, one change, one file or a whole chat at a time. |
| [Agent Review](editing/agent-review.md) | Have Claude look over your changes, a commit or a chat's edits for bugs and for what you asked that wasn't done, then fix what it finds. |
| [Agent Blame](editing/agent-blame.md) | See which chat wrote a line of code, and jump back to that chat. |
| [Fix Problems, Conflicts and Commit Messages](editing/fix-with-ember.md) | Send an error to Claude to fix, resolve merge conflicts, and write commit messages from Source Control. |
| [Tab Predictions](editing/tab-predictions.md) | Ember Tab suggests your next edit as you type; press Tab to take it. |
| [Diagram, SVG and CSV Previews](editing/previews.md) | See Mermaid diagrams, SVG images and CSV tables rendered, and switch back to the source in one click. |

## Plans and Bonfire

| Page | What it covers |
|---|---|
| [Plans](plans/plans.md) | Have Claude plan a larger change first, review and edit the plan, then build it here, in a new chat or with Bonfire. |
| [How to build a plan with Bonfire](plans/bonfire-howto.md) | Build a plan's independent to-dos at the same time: each one a chat in its own worktree with its own pull request, the ones that depend on others starting once those merge. |
| [Plan from GitHub and Jira issues](plans/issues.md) | List your open GitHub and Jira issues in one list, pick some and plan from them in a Plan-mode chat, or let Claude suggest groups that each make one Bonfire plan. |

## Worktrees, windows and tabs

| Page | What it covers |
|---|---|
| [Worktrees](worktrees/worktrees.md) | Run a chat in its own git worktree and branch, so several chats can work at once without touching your main worktree. |
| [The Ember Dashboard](worktrees/dashboard.md) | One page for your work in flight, sorted by whose move it is: what needs you now, your move, what Ember is working on, what waits on others, this week and what's done. |
| [How to use workspace tabs](worktrees/workspace-tabs.md) | In Ember.app, keep several repositories and worktrees as tabs in one window's title bar, and move tabs between windows. |
| [Work across tabs and windows](worktrees/across-tabs.md) | See what needs you in every tab and window, and jump to a chat or file in any of them. |

## Forge (Git)

| Page | What it covers |
|---|---|
| [How to use Forge](forge/forge-howto.md) | Ember's git for this worktree: its branch and pull request, stage and commit, browse history, file and line history, compare any two refs, open diffs in the editor, switch branches, sync and get out of a paused merge. |
| [Watch a pull request](forge/babysit.md) | Let a chat watch a GitHub pull request and fix failing checks, merge conflicts and review comments until it is green. It never merges. |

## Browser, canvases and your phone

| Page | What it covers |
|---|---|
| [Ember's browser](connect/browser.md) | A browser you and Claude share: open pages, add an element to a chat, let Claude read and test pages, and manage the sites it's signed in to. |
| [Visual checks](connect/visual-checks.md) | Claude checks UI changes in Ember's browser: it saves a baseline screenshot, compares after a change (what changed and where, with a diff image) and records animations to catch layout jumps. |
| [Canvases](connect/canvases.md) | Small React apps Claude builds for you — dashboards, reports, trackers — that open beside the chat, keep their state, and can be fixed by Claude when they break. |
| [Ember on your phone](connect/phone.md) | Watch and guide your chats from your phone: turn on Settings › Phone, choose how the phone reaches Ember, and pair it with a one-time code. |
| [Talk to Ember and hear it](connect/voice.md) | Ember says out loud when a chat or Bonfire needs you, by name, and you answer by voice into that chat. Your own speech and transcription endpoints (oMLX with Kokoro, mlx-audio, OpenAI) or macOS's British voice. |

## Rules, memory, index and docs

| Page | What it covers |
|---|---|
| [Rules and CLAUDE.md](knowledge/rules.md) | Give Claude standing instructions: CLAUDE.md, project rules, your own user rules, and rule files other editors write. |
| [Memory](knowledge/memory.md) | Have Claude remember facts across chats: memories you add, and the notes Claude Code keeps on its own. |
| [Codebase Index](knowledge/codebase-index.md) | Ember indexes your code so Claude can search it by words, and by meaning with an embeddings model. |
| [@Docs](knowledge/docs.md) | Fetch a documentation site to this computer. Claude searches it on its own, or mention it with @Docs so Claude reads the matching pages. |
| [Conversation Search](knowledge/conversation-search.md) | Let Claude look up what was said in your earlier chats in this project. |

## Models

| Page | What it covers |
|---|---|
| [Choosing models](models/choosing-models.md) | Pick a model and effort for each chat, see where a default comes from, set what new chats start on, and choose the models for titles, commit messages, inline edits and subagents. |
| [Your own endpoints](models/own-endpoints.md) | Add model endpoints — local servers, hosted providers and gateways — and choose which model does Tab, embeddings, rerank, speech and transcription. |
| [Model bridge](models/model-bridge.md) | Sign in to other subscriptions and use their models in chat next to Claude, through a local bridge that Ember installs, sandboxes and keeps up to date. |

## Ember and Claude Code

| Page | What it covers |
|---|---|
| [What Ember honours from Claude Code](claude-code/claude-code-honours.md) | Every chat runs Claude Code with your own settings files, so CLAUDE.md, skills, hooks, subagents, MCP servers, plugins, permissions and the rest work in Ember as in the terminal. |
| [What Ember changes, and why](claude-code/claude-code-changes.md) | How Ember's permission levels map onto Claude Code's modes, the commands that always ask, Ember's own tools for Claude, API-key removal, worktrees, memories, and the small model calls Ember makes. |
| [Where Ember writes, and using the CLI alongside](claude-code/claude-code-files.md) | Which files Ember writes for Claude Code, what goes in a project's .ember folder, what Ember keeps in its own storage, and how chats move between Ember and the claude CLI. |

## What Ember changes in VS Code

| Page | What it covers |
|---|---|
| [What Ember changes in VS Code](vs-code/vs-code-changes.md) | Every change Ember.app makes to the editor it is built on: what you see, why, and what stock VS Code or VSCodium does instead. |
| [Ember in stock VS Code or VSCodium](vs-code/ember-in-stock-vscode.md) | What works the same when you install Ember's extensions into your own VS Code or VSCodium, and what you get instead of Ember.app's editor changes. |

## Settings reference

| Page | What it covers |
|---|---|
| [Settings reference](settings/settings.md) | Every Ember setting, grouped the way Settings shows them. |
| [Settings: General](settings/settings-general.md) | Every setting in Settings › General: type, default, values and what it does. |
| [Settings: Accounts](settings/settings-account.md) | Every setting in Settings › Accounts: type, default, values and what it does. |
| [Settings: Editor](settings/settings-editor.md) | Every setting in Settings › Editor: type, default, values and what it does. |
| [Settings: Chats](settings/settings-chats.md) | Every setting in Settings › Chats: type, default, values and what it does. |
| [Settings: Rules and memories](settings/settings-memories.md) | Every setting in Settings › Rules and memories: type, default, values and what it does. |
| [Settings: Permissions](settings/settings-permissions.md) | Every setting in Settings › Permissions: type, default, values and what it does. |
| [Settings: Subagents](settings/settings-subagents.md) | Every setting in Settings › Subagents: type, default, values and what it does. |
| [Settings: Bonfire](settings/settings-bonfire.md) | Every setting in Settings › Bonfire: type, default, values and what it does. |
| [Settings: Issues](settings/settings-issues.md) | Every setting in Settings › Issues: type, default, values and what it does. |
| [Settings: MCP servers](settings/settings-mcp.md) | Every setting in Settings › MCP servers: type, default, values and what it does. |
| [Settings: Worktrees](settings/settings-worktrees.md) | Every setting in Settings › Worktrees: type, default, values and what it does. |
| [Settings: Models](settings/settings-models.md) | Every setting in Settings › Models: type, default, values and what it does. |
| [Settings: Tab](settings/settings-tab.md) | Every setting in Settings › Tab: type, default, values and what it does. |
| [Settings: Voice](settings/settings-voice.md) | Every setting in Settings › Voice: type, default, values and what it does. |
| [Settings: Usage pricing](settings/settings-usage.md) | Every setting in Settings › Usage pricing: type, default, values and what it does. |
| [Settings: Indexing](settings/settings-indexing.md) | Every setting in Settings › Indexing: type, default, values and what it does. |
| [Settings: Browser](settings/settings-browser.md) | Every setting in Settings › Browser: type, default, values and what it does. |
| [Settings: Phone](settings/settings-remote.md) | Every setting in Settings › Phone: type, default, values and what it does. |
| [Settings: Only in settings.json](settings/settings-other.md) | Every setting in Settings › Only in settings.json: type, default, values and what it does. |

## Keyboard shortcuts

| Page | What it covers |
|---|---|
| [Keyboard shortcuts](shortcuts/keyboard-shortcuts.md) | Every Ember shortcut on macOS, Windows and Linux, the VS Code essentials, and the VS Code keys Ember changes. |

## Commands reference

| Page | What it covers |
|---|---|
| [Commands reference](commands/commands.md) | Every Ember command as the Command Palette names it, with its ID and keys. |

## Privacy, storage and integrations

| Page | What it covers |
|---|---|
| [Privacy and storage](privacy/privacy-storage.md) | What Ember keeps on your computer, what leaves it and where it goes, the Storage settings, and how .emberignore keeps files away from Claude. |

## Troubleshooting

| Page | What it covers |
|---|---|
| [Troubleshooting](troubleshooting/troubleshooting.md) | Fixes for common problems — a waiting card you can't see, a blank window when a worktree opens, approvals that keep asking, a notice that went, claude not found, sign-in, a stuck index — and where to find logs and diagnostics. |

## Accessibility

| Page | What it covers |
|---|---|
| [Accessibility](accessibility/accessibility.md) | Use Ember with the keyboard alone, with a screen reader, and with reduced motion. |

## Glossary

| Page | What it covers |
|---|---|
| [Glossary](glossary/glossary.md) | The words you meet on the way from a first chat to a merged pull request, in plain words, with where you see each one. |

---

[Back to Ember](../README.md) · [Download](https://github.com/dgruhin-hrizn/ember-releases/releases/latest) · [Release notes](https://github.com/dgruhin-hrizn/ember-releases/releases)
