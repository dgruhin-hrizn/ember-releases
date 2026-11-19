# Settings: Usage pricing

Every setting in Settings › Usage pricing: type, default, values and what it does.

These settings are in **Settings › Usage pricing** (and in your `settings.json`).

### `ember.usageDashboard.prices`

Your own API prices (USD per million tokens) for the usage dashboard, by model id: `{ "claude-opus-5-5": { "input": 4, "output": 20, "write5m": 5, "write1h": 8, "cacheRead": 0.2 } }`. Edit them in Ember Settings › Usage pricing.

- **Type:** object
- **Default:** `{}`
- **Scope:** User or workspace

### `ember.usageDashboard.statusBar`

Show the Claude account item in the status bar: the chat's account (its name only when you have several) and its weekly limit (**Week 84%**), or the 5-hour limit when that's nearer. Click it for every account's limits, to switch this chat to another account, the Usage dashboard and Settings › Accounts. Without a limit to show, it shows today's Claude Code tokens · API-equivalent cost.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

---

[All documentation](../README.md)
