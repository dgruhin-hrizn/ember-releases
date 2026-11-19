# Rules and CLAUDE.md

Give Claude standing instructions: CLAUDE.md, project rules, your own user rules, and rule files other editors write.

Rules are standing instructions Claude keeps to without being told each time: your coding conventions, how to run the
tests, what never to touch. Ember reads them from several files and shows which ones each turn used.

## CLAUDE.md and Claude Code's rules

Ember runs Claude Code, so everything Claude Code loads counts here too, and the terminal loads the same files:

- `CLAUDE.md` in the project (and in parent and sub folders).
- `CLAUDE.local.md`: your private notes for this project, not committed.
- Your own instructions for all projects, in your Claude Code folder.
- Rule files in the project's `.claude/rules` folder. A rule can list paths, so it loads only when Claude works on
  matching files.

Settings › Rules and memories lists these files in the order Claude Code loads them, with their size, and has buttons to
create the ones you don't have yet: **Create my instructions (all projects)**, **Create my private notes for this
project**, **New project rule…**, and **Have Claude write project instructions** (a new chat runs `/init` to write
`CLAUDE.md`). **Don't load** next to a file keeps Claude Code from loading it.
**Open Rules and memories**

> **Tip:** When you correct Claude the same way three times, Ember offers to save it as a rule for you. See
> [Learn from your corrections](memory.md#learn-from-your-corrections).

## The Rules view

Open the **Rules** view in the **Ember Work** side bar. It shows:

- **Last turn**: the rules the chat's last turn used, and why (for example **always**, **glob match** or
  **@-mentioned**).
- Every rule, grouped by when it's used: **Always**, **Auto attached**, **Agent requested**, **Manual**,
  **User rules** and **Memories**.

For each rule you can:

- Turn it off or on with its switch.
- Click its name to open the file.
- Click **@** to attach it to your next message.

## Create a rule

1. Click **New Rule** in the Rules view's title bar, or run **New Rule**.
2. Give it a **Name** and pick a **Rule type**:
   - **Always**: in every chat.
   - **For specific files**: when Claude works on files matching the **Files** patterns, such as `src/**/*.ts`.
     Separate patterns with commas. A comma inside braces stays part of its pattern, so `*.{ts,tsx}` is one pattern;
     so does one written `\,`. Editing a rule rewrites only what you changed.
     If a pattern matches no file in the workspace, the form says so under the field. You can still save it, for
     files you haven't made yet.
   - **When Claude decides**: Claude reads the description and decides when it is relevant.
   - **Only when mentioned**: only when you @-mention it.
3. Write the rule and click **Create rule**.

**Always** and **For specific files** rules are saved in `.claude/rules`, so Claude Code and the terminal
load them too. The other two kinds only work in Ember.

### From a selection

Select some text in the editor, right-click, and choose **Create Rule from Selection**
(**Create Rule from Selection**). The new rule form opens with the selection
already in it.

## User rules

User rules go to every Ember chat, in every project. Add them to [`ember.rules.userRules`](../settings/settings-memories.md#emberrulesuserrules), one rule per
item. They show under **User rules** in the Rules view.

## Rule files from other editors

Ember also reads the project rule files other editors write, and `AGENTS.md` files, so a project set up elsewhere
works here without changes. They appear in the Rules view like any other rule. Ember reads them in the project, in its
sub folders and in the folders above it, and picks up a change to any of them within a second, without a reload.

When a `CLAUDE.md` imports one of these files (`@AGENTS.md`), Claude Code loads it by that import, so Ember doesn't
send it a second time. The Rules view still lists the file and says so. The same goes for `AGENTS.md` in a project
with no `CLAUDE.md`, `.claude/CLAUDE.md` or `CLAUDE.local.md` of its own: Claude Code loads those files itself, in the
project, its sub folders and the folders above it. An `AGENTS.md` with the same text as the `CLAUDE.md` beside it (a
copy or a link) isn't sent either. Claude Code's own `instructionFiles` option (in your user settings, under
`pluginConfigs` › `cc-plugin-agents-md@builtin`) changes this: with `claude-md`, Claude Code never loads `AGENTS.md`,
so Ember sends it; with `claude-md-and-agents-md` Claude Code always loads it; with `managed-only` it leaves the
project's instruction files out, and Ember does too.

When the project has such rule files, the Rules view offers **Convert to Claude rules…**. It shows a preview of
where each rule would go in `.claude/rules` (and which ones have to stay, and why). Nothing changes until you click
**Convert**.

---

[All documentation](../README.md)
