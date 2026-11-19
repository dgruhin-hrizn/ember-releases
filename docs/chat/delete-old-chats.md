# Delete Old Chats

Clean up a folder's old chats now or on a schedule, keep the ones you pin, and control Claude Code's own transcript cleanup.

Chats pile up. Ember can delete a folder's old chats for you, now or on a schedule. Deleting a chat deletes its
transcript too.

## What is never deleted

- Pinned chats. Pin a chat from its menu in the chat list or its tab (see [The chat list](chat-tabs.md#the-chat-list)).
- Chats that are running.
- The chat you have open.
- Worktree chats whose changes are still only in their worktree.
- Chats open in a tab, chats with changes waiting for review, and chats with unsent text in their message box.
- Chats of another worktree folder that a window has open: close that window (or its tab) first.

## Delete old chats now

1. Run **Delete Old Chats…**, or click **Delete Old Chats…** in **Settings › Chats › Old
   chats**.
2. Ember says how many chats are older than the limit: this folder's, and the ones the chat list shows under this
   repository from its other worktree folders (such as a Bonfire run's to-do chats). Click **Delete**, or **Review…**
   to pick which ones go.

Or, in the chat list, click **⋯** next to the search and pick **Delete Old Chats…**: it's the same command. The same
menu has **Delete Chats Whose Worktree Is Gone…** (see [The list's menu](chat-tabs.md#the-lists-menu)). For one worktree's chats only,
pick **Delete old chats in this worktree…** from that worktree's section's **⋯** in the chat list (see
[Branch cards](chat-tabs.md#branch-cards)).

A chat's age is the time since you last used it. Set the limit in **Delete chats older than**
([`ember.chatCleanup.olderThanDays`](../settings/settings-chats.md#emberchatcleanupolderthandays), 30 days by default).

## Clean up on a schedule

In **Settings › Chats › Old chats**:

- **Clean up automatically** ([`ember.chatCleanup.schedule`](../settings/settings-chats.md#emberchatcleanupschedule)): **Off** (the default), **Daily** or
  **Weekly**.
- **Before deleting** ([`ember.chatCleanup.mode`](../settings/settings-chats.md#emberchatcleanupmode)): **Ask first** asks in the chat on screen, with **Delete**,
  **Review…** and **Not now** (closing it asks again next time); **Delete automatically** deletes, then says how many.

## Claude Code's own cleanup

Claude Code deletes its old transcripts by itself, pinned chats included, after a number of days. **Settings › Chats ›
Claude Code keeps transcripts** shows that number. If it's under a year, **Keep transcripts longer** sets it to 10
years (click it twice to confirm). If your organization sets it, it can't be changed here.

> **Careful:** A chat whose transcript Claude Code deleted can't be continued, even if it's pinned in Ember.

## Delete all Claude Code data for a project

To remove everything Claude Code keeps for this folder (transcripts, tasks, file history and its entry for the
project):

1. In **Settings › Chats › Claude Code data**, click **Show what would be deleted…**. Claude Code lists it; nothing
   is deleted yet.
2. Read the list, then click **Delete permanently…** to delete it, or **Cancel**.

> **Careful:** This can't be undone.

---

[All documentation](../README.md)
