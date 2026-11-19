# Settings: Chats

Every setting in Settings › Chats: type, default, values and what it does.

These settings are in **Settings › Chats** (and in your `settings.json`).

### `ember.chatCleanup.mode`

What a scheduled cleanup does when it finds old chats.

- **Type:** one of the values below
- **Default:** `"ask"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"ask"` | Ask first, in the chat: Delete, Review… or Not now. |
| `"automatic"` | Delete without asking, then say how many. |

### `ember.chatCleanup.olderThanDays`

**Delete Old Chats** and scheduled cleanup delete this folder's chats older than this many days. Pinned chats are always kept.

- **Type:** integer
- **Default:** `30`
- **Range:** 1 to 36500
- **Scope:** Application (all windows and profiles)

### `ember.chatCleanup.schedule`

Clean up this folder's old chats on a schedule (older than `ember.chatCleanup.olderThanDays` days; pinned chats are always kept).

- **Type:** one of the values below
- **Default:** `"off"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"off"` | Only when you run Delete Old Chats. |
| `"daily"` | Check once a day. |
| `"weekly"` | Check once a week. |

### `ember.chats.handoverNote`

Who writes the note a fresh chat starts from when you continue a long chat in a new one.

- **Type:** one of the values below
- **Default:** `"quick"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"quick"` | Haiku writes it from a copy of the chat cut to what the note needs: the first message, everything you typed, the plan, the files changed, failures, the last 40 tool calls and the last 120 messages, all without tool output. A note that leaves something out is written thoroughly instead. |
| `"thorough"` | The chat's own model writes it from the whole chat, which reads all of it again without the chat's cache. |

### `ember.chats.resumeInterrupted`

A chat that was working when Ember closed (quit, crash or reload) can pick up where it left off when Ember opens again.

- **Type:** one of the values below
- **Default:** `"ask"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"ask"` | Each interrupted chat offers Continue. |
| `"always"` | Continue up to 3 interrupted chats automatically (most recent first); the rest offer Continue. |
| `"never"` | Leave interrupted chats as they are. |

### `ember.chats.suggestHandover`

Suggest carrying a long chat on in a fresh chat once, when it nears Claude Code's own compaction (72% of the way there). Off: the card never shows. Don't suggest again on the card turns this off too.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.chats.suggestHandoverAtBreaks`

Also suggest a fresh chat earlier, once a chat holds 150k tokens (or 15% of its window), at a good point to start fresh: a pull request opened, merged or closed, another branch, a Bonfire run ended, or a long break. Needs `ember.chats.suggestHandover`.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.quitGuard`

Ember app: ask before quitting while chats are still working (a running turn, background subagents or commands).

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
