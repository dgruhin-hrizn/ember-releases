# Agent Blame

See which chat wrote a line of code, and jump back to that chat.

Agent Blame remembers which chat wrote each line Ember changed, so you can find the conversation behind a piece of
code later. It keeps track of those lines as you edit around them and after you commit them.

A line counts as Ember's once you keep the change that wrote it (see [Review changes](review-changes.md)). Your own commits
carry the record along, including amends and rebases. Nothing is written into the commits themselves: the record
stays on this computer, in Ember's storage.

## See who wrote a line

- **Hover** a line Ember wrote. The hover says **Written by Ember**, with the chat's title, the model and when.
  Click **Open Chat** to open that chat, or **Show Message** to jump to the message that asked for it.
- **Status bar:** when the cursor is on a line Ember wrote, the status bar shows the chat's title. Click it to open
  the chat. Turn this off with [`ember.blame.statusBar`](../settings/settings-editor.md#emberblamestatusbar).
- **Gutter:** turn on [`ember.blame.gutter`](../settings/settings-editor.md#emberblamegutter), or run
  **Toggle Agent Blame**, to mark Ember's lines with a thin bar, one colour per chat.

If the chat has since been deleted, the hover says the line came from a deleted chat. While a change is still pending,
the hover is the review's instead: who wrote it, "not yet kept", and **Keep** and **Undo** for that change (see
[Review changes](review-changes.md)).

These switches are in Settings › Editor under **Which chat wrote a line**.

## Let Claude ask

With [`ember.blame.tool`](../settings/settings-editor.md#emberblametool) on, Claude gets a read-only `agent_blame` tool. It can ask which chat wrote
lines of a file and then look up why, for example before it changes code another chat wrote.

## Forget the record

Settings › Storage shows how many rows Agent Blame keeps under **Which chat wrote each line**. Click
**Forget which chat wrote each line** (twice, to confirm) to delete them all, or run
**Clear Agent Blame**. Ember keeps no other copy. Deleting a chat doesn't remove its rows.

---

[All documentation](../README.md)
