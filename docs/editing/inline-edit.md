# Inline Edit

Ask Claude to change or write code right where you are, in the editor or in the terminal.

Inline edit changes code without leaving the editor. Select some lines, describe the change, and Claude rewrites
them right there. With nothing selected, Claude writes new code at the cursor. Each edit is one quick call to Claude:
no chat is created.

## Edit code where it is

1. Select the lines you want changed. To write new code instead, put the cursor where it should go.
2. Press <kbd>⌘K</kbd> (<kbd>Ctrl+K</kbd> on Windows and Linux), or click **Quick Edit** on the small toolbar that appears under a selection. With
   nothing selected, that key starts VS Code's own two-key shortcuts as usual (such as ⌘K ⌘S), so press ⌘K ⌘G
   (Ctrl+K Ctrl+G on Windows and Linux) to write new code at the cursor.
3. Type what you want, for example "convert to async/await", and press Enter.

The prompt bar is a small floating card above the lines: the instruction on top, with the model it uses on the right,
and the buttons underneath. The new code streams into the file as Claude writes it, right under the card: the new
lines are tinted, and the lines they replace show just above them. When it is done, the card stays open on the
pending edit and shows its size, for example **+3 −1**:

- **Accept** (Command+Enter on macOS, Ctrl+Enter on Windows and Linux, in the card or in its editor; or
  <kbd>⌘Y</kbd> (<kbd>Ctrl+Y</kbd> on Windows and Linux)) keeps the edit. While the card is open, that key never keeps the whole file.
- **Reject** (<kbd>⌘N</kbd> (<kbd>Ctrl+N</kbd> on Windows and Linux)) puts the code back as it was.
- **Continue in chat** sends your instruction and the lines to the chat panel, where a full agent can carry on.
- Type more, such as "also handle null", and press Enter to revise the same edit.
- Close the card (Esc or **✕**) to leave the edit pending. It then shows with **Keep** and **Undo** like any agent change
  (see [Review changes](review-changes.md)).

Claude sees the file around the selection, the folder's `CLAUDE.md` files and the rules for the file.
Files excluded by `.emberignore` can't be edited this way.

> **Tip:** If you edit the file inside the selection while Claude is still writing, the edit stops and what arrived so
> far stays pending for you to accept or reject.

## Ask a quick question

The prompt bar can also answer a question about the selected code without changing anything. Type the question and
click **Ask** (Option+Enter on macOS, Alt+Enter on Windows and Linux). The answer appears in the card. Click
**Send answer to chat** to carry the question and the answer into the chat panel.

## Send it to the chat instead

Click **Send to chat** in the card (Command+L on macOS, Ctrl+L on Windows and Linux) to
send your instruction and the selected lines to the chat panel, where a full agent can work on it. While an edit is
pending, the same button reads **Continue in chat**.

## Reuse your last instruction

Ember remembers the last instruction you gave in each file. Run
**Open Last Inline Edit Prompt** to reopen the bar with it filled in.

## Choose the model and effort

Inline edits use [`ember.inlineEdit.model`](../settings/settings-models.md#emberinlineeditmodel) (Sonnet unless you change it; a fast model works best here) and
[`ember.inlineEdit.effort`](../settings/settings-models.md#emberinlineediteffort) (empty means the model's default). Change both in Settings › Models, or pick a
model from the model name at the right of the card's prompt line.

## The selection toolbar

When you select text, a small toolbar offers **Add to Chat** and **Quick Edit**. Turn it off with
[`ember.selectionToolbar`](../settings/settings-editor.md#emberselectiontoolbar). The keyboard shortcut works either way.

## Write a terminal command

In a terminal, <kbd>⌘K</kbd> (<kbd>Ctrl+K</kbd> on Windows and Linux) asks "What should the command do?". Describe it, and Claude writes one
command and puts it on the terminal's prompt line. It never runs it: press Enter to run it, or edit it first.

- The command is written for the terminal's shell, operating system and current folder.
- If a program is still running in that terminal, Ember doesn't type into it and shows the command in a message instead.
- If no command arrives within 60 seconds, try again.

Turn this off with [`ember.terminal.commandK`](../settings/settings-editor.md#emberterminalcommandk) (Settings › Editor); the shortcut then clears the terminal as usual.

---

[All documentation](../README.md)
