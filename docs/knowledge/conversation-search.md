# Conversation Search

Let Claude look up what was said in your earlier chats in this project.

When you say "like we did last week" or "use the fix from the login chat", Claude can look it up. Ember keeps a
local index of your chats in this project, and Claude searches it with a read-only `search_conversations` tool.

## How Claude uses it

Claude searches by what was said, and gets back the best-matching chats first, each with its title, when it was last
active, and a snippet of where it matched. To read more, it opens that chat's transcript.

- The index covers this project's chats, including chats that ran in its worktrees.
- It is kept on this computer, in Ember's storage, and stays in step with Claude Code's transcripts as chats change.
- The tool only reads. It never asks for approval, and subagents don't get it.
- The excerpts it finds go to the chat's model, like anything else Claude reads.

The **Search chats** box in the chat list searches the same index, so you can look things up yourself.

## Turn it on or off

The tool is on by default. Switch it in Settings › General under **What Claude can use** › **Search past
conversations** ([`ember.searchConversations.tool`](../settings/settings-general.md#embersearchconversationstool)). The change takes effect in new chats.

## Chats on your own models

Chats on your own models (see [Your own endpoints](../models/own-endpoints.md)) don't get the tool by default: it would send excerpts of your
other conversations to that provider. Turn on [`ember.searchConversations.ownModels`](../settings/settings-general.md#embersearchconversationsownmodels) to give it to them
too.

---

[All documentation](../README.md)
