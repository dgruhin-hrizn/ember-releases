# Import Your Settings

Bring settings, keyboard shortcuts, snippets and extensions from VS Code or VSCodium, and another editor's rules and commands into Claude Code.

Ember can copy what you set up in another editor so you don't start from scratch. There are two imports: one for the
editor itself, one for Claude Code.

## Import settings, shortcuts, snippets and extensions

Ember looks for VS Code, VSCodium and other VS Code–based editors on this computer.

1. Start the import in one of these ways:
   - On the Welcome page, click **Import…** in the **Import** card.
   - In **Settings › General › Import and layout**, click **Import…** next to **Import from another editor**.
   - **Import settings**
2. If Ember found more than one editor, pick the one to import from.
3. Pick what to import: **Settings**, **Keyboard shortcuts**, **Snippets**, **Extensions**. Nothing you already have
   is replaced.
4. Ember says how many of each it will bring over. Click **Show Preview** to read every change first, or **Import**
   to go ahead.

Ember backs up every file it changes before writing it, and installs the extensions from this editor's extension
gallery. When it's done, the chat on screen says what was imported (a notification, with no chat open); **Open backup
folder** shows the backups, and from Cursor **Import rules and commands…** brings its rules into Claude Code. Extensions
the gallery doesn't have are listed there too.

> **Note:** Close or save any settings, keybindings or snippets file with unsaved changes first: Ember won't import
> over it. The import works only in a local window, not one connected to another machine.

To stop the Welcome page offering the import, click **Don't show again** on its card.

## Import rules and commands into Claude Code

Claude Code can bring another editor's rules and commands into its own config files, so your Ember chats and the
terminal both use them. Ember shows this row in **Settings › General › Import and layout** when there is something it
can import from.

1. Next to **Import into Claude Code config**, click **Preview…**. Claude Code reads the other editor's config and
   writes nothing yet.
2. Read the preview: **Rules**, **Commands**, **Also imported** and **MCP servers**, each with where it will land.
   **Not imported** lists what Claude Code left out and why.
3. Click **Import** to import exactly this preview, or **Cancel**.

Afterwards, Ember lists each file Claude Code wrote; click one to open it. MCP servers you already have are left as
they are; to update those, use **Settings › MCP servers**.

## See also

- [Rules and CLAUDE.md](../knowledge/rules.md): rules in Ember and Claude Code.
- [Settings: General](../settings/settings-general.md): every General setting.

---

[All documentation](../README.md)
