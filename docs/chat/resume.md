# When Ember Closes Mid-Run

Ember asks before quitting while chats work, and interrupted chats can pick up where they left off.

Quitting, a crash or reloading the window stops any chat that is working. Ember helps you not lose that work.

## Ask before quitting

In Ember.app, quitting while chats are still working (running a turn or background subagents) asks first:
**1 chat is still working** (or how many), with **Quit** and **Cancel**.

The dialog's **Resume them next time** box decides whether those chats carry on when you open Ember again.

Turn the question off in **Settings › Chats › Ask before quitting** ([`ember.quitGuard`](../settings/settings-chats.md#emberquitguard)).

## Pick up interrupted chats

A chat that was working when Ember closed shows **Ember closed before this turn finished.** with **Continue** at the end
of its last turn when Ember opens again. Click **Continue** and Claude carries on where it stopped. In the chat list, its dot reads
**Interrupted when Ember closed**.

Choose what happens in **Settings › Chats › Interrupted chats** ([`ember.chats.resumeInterrupted`](../settings/settings-chats.md#emberchatsresumeinterrupted)):

| Choice | What happens |
|---|---|
| **Offer Continue** (the default) | Each interrupted chat offers **Continue**. |
| **Continue automatically (up to 3)** | Up to 3 interrupted chats continue automatically, most recent first; the rest offer **Continue**. |
| **Leave them** | Interrupted chats are left as they are. |

On the [The Ember Dashboard](../worktrees/dashboard.md), an interrupted chat or one whose turn failed shows under **Needs you**,
with the reason and **Continue**. After a crash, **Continue 2 interrupted chats** carries on every interrupted chat, in every window.

> **Note:** Plans being built with Bonfire are carried on by their Bonfire run, not by **Continue**.

## When the disk is full

Claude Code saves each chat's history (its transcript) and its own settings file, `~/.claude.json`, to disk. If the disk
fills up or your disk quota runs out, Claude Code 2.1.318 and later say what they couldn't save, and Ember tells you in
the chat: which chat's history is incomplete, or that settings changed in that session (such as
MCP servers or trusted folders) may need setting again. Free up disk space so new messages are saved.

A chat whose history lost lines says so again when you resume it, because Claude may not remember all of the
conversation. If it matters, start a new chat and give it what it needs.

---

[All documentation](../README.md)
