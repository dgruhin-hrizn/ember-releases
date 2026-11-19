# Settings: Permissions

Every setting in Settings › Permissions: type, default, values and what it does.

These settings are in **Settings › Permissions** (and in your `settings.json`).

### `ember.agentPermissionMode`

> **Deprecated.** No longer used. How much a new chat does on its own is **How much can Claude do on its own?** (`ember.permissions.level`) in Settings › Permissions; Claude Code's `permissions.defaultMode` only decides whether a new chat opens in Plan.

Claude Code's `permissions.defaultMode` decides only whether a new chat opens in Plan. How much a chat does on its own is `ember.permissions.level` (Settings › Permissions).

- **Type:** one of the values below
- **Default:** `"claude"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"claude"` | Same as Claude Code: a new chat opens in Plan when Claude Code's permissions.defaultMode is plan. |

### `ember.permissions.allowBypass`

> **Deprecated.** Replaced by **How much can Claude do on its own?** (`ember.permissions.level`) in Settings › Permissions: pick **Run everything** there. An earlier value is read once to choose your level.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.permissions.alwaysAllowScope`

Where the approval card's "Always run" saves the rule (a Claude Code permissions.allow rule).

- **Type:** one of the values below
- **Default:** `"user"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"local"` | This project, just you (.claude/settings.local.json) |
| `"project"` | This project, shared (.claude/settings.json) |
| `"user"` | All projects (~/.claude/settings.json) |

### `ember.permissions.level`

**How much can Claude do on its own?** The level every new chat starts at, in every mode; a chat's mode pill can pick its own level for that chat. Edits never ask (Keep or Undo them afterwards). Below Run everything, destructive commands — force pushes, recursive deletes, `sudo`, piping a download into a shell, anything touching SSH keys or credentials — and pushes to protected branches always ask. **Run everything**: nothing asks.

- **Type:** one of the values below
- **Default:** `"safe"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"ask"` | Ask before running commands: edits run (review them with Keep or Undo); every command asks. |
| `"safe"` | Run safe commands: reads, tests, builds, linters and read-only git run on their own; every other command asks. |
| `"all"` | Run everything: nothing asks — every command runs, destructive ones (force pushes, recursive deletes, sudo…) and pushes to protected branches included. Claude's own questions still show. |

---

[All documentation](../README.md)
