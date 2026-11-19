# Accessibility

Use Ember with the keyboard alone, with a screen reader, and with reduced motion.

Ember runs inside VS Code, so the editor's own accessibility features work as usual. This page covers what Ember's panels add.

## Keyboard-only use

Ember's main work has keys: the chat panel, the message box, the model picker, approvals, reviewing changes and plans. [Keyboard shortcuts](../shortcuts/keyboard-shortcuts.md) lists them. Every Ember shortcut is also in the editor's own Keyboard Shortcuts, where you can change it — Settings › Keyboard › **Open Keyboard Shortcuts** takes you there.

**Open Settings › Keyboard**

> **Tip:** When Claude asks for approval, focus stays in the message box; a key takes you to the approval. The screen reader announcement (below) names it, and [In the message box](../shortcuts/keyboard-shortcuts.md#in-the-message-box) lists it.

## Screen readers

Ember's panels label their buttons and controls, so icon-only buttons are read by name.

The chat has a polite live region that announces, without moving your focus:

- **Claude is working** when a turn starts;
- **Finished**, with how long Claude worked, when it ends;
- that an approval is waiting (or how many), and the key to review it;
- **Queue paused** when queued messages are held;
- when Claude proposes switching to another mode.

Elsewhere:

- A question from Claude reads out the question (and which one of how many) as it appears.
- Errors in Settings and other panels are announced as alerts; status lines, such as a test result or a Bonfire step in progress, are announced politely.
- In Settings, Tab goes from the search box to the sections, where Up, Down, Home and End move between them. A row
  of buttons for a few choices is a radio group: the arrow keys pick one.
- Settings controls carry their row's hint as their description, so it's read with the control. A button that needs a second click to confirm says so.

## Reduced motion

When your system asks for reduced motion, Ember's panels tone down their animations.

Bonfire's fire — climbing the Bonfire page when a run is lit and burning down when you extinguish it — becomes a quick fade. You can also turn these animations off yourself with [`ember.bonfire.animations`](../settings/settings-bonfire.md#emberbonfireanimations).

## VS Code's accessibility features

VS Code has its own walkthrough of screen reader mode, accessible views, audio cues, high-contrast themes and zoom: open the **Help** menu and choose **Get Started with Accessibility Features**.

---

[All documentation](../README.md)
