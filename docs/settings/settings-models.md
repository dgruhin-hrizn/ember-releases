# Settings: Models

Every setting in Settings › Models: type, default, values and what it does.

These settings are in **Settings › Models** (and in your `settings.json`).

### `ember.autoTitleModel`

Model used for auto titles.

- **Type:** string
- **Default:** `"haiku"`
- **Scope:** User or workspace

### `ember.bridge.autoUpdate`

Keep the model bridge (CLIProxyAPI, for ChatGPT, Gemini, Grok and other sign-ins) up to date. Checked each time Ember starts; a release is installed only after it has been out for `ember.bridge.updateCooldownDays` days and its download matches the published checksums.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.bridge.binaryPath`

Use your own CLIProxyAPI binary instead of the one Ember installs. Ember never updates a binary set here.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.bridge.updateCooldownDays`

How long a model bridge release must have been out before Ember installs it. Hijacked releases are usually pulled within days.

- **Type:** integer
- **Default:** `7`
- **Range:** 0 to 60
- **Scope:** Application (all windows and profiles)

### `ember.commitMessage.model`

Model that writes commit messages from Source Control (on your Claude subscription).

- **Type:** string
- **Default:** `"haiku"`
- **Scope:** User or workspace

### `ember.customModels`

Your own endpoints — Anthropic-compatible chat providers and OpenAI-compatible endpoints for Tab, embeddings and rerank (manage them in Ember Settings › Models). API keys and header values are kept in secret storage (your system keychain), not here.

- **Type:** array
- **Default:** `[]`
- **Scope:** Application (all windows and profiles)

### `ember.inlineEdit.effort`

Effort for inline edits (⌘K, or Ctrl+K on Windows and Linux). Empty = the model's default.

- **Type:** one of the values below
- **Default:** empty
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `""` |  |
| `"low"` |  |
| `"medium"` |  |
| `"high"` |  |
| `"xhigh"` |  |
| `"max"` |  |

### `ember.inlineEdit.model`

Model for inline edits (⌘K, or Ctrl+K on Windows and Linux; fast is better here).

- **Type:** string
- **Default:** `"sonnet"`
- **Scope:** User or workspace

### `ember.model`

Fallback model for new chats when remembering is off or no model selection is stored (e.g. `opus`, `sonnet`). Empty = Claude Code's default. The panel's model picker overrides this per session.

- **Type:** string
- **Default:** empty
- **Scope:** User or workspace

### `ember.plans.buildModel`

The model a plan's Build starts with (each plan remembers its own pick). Empty = the chat's default model.

- **Type:** string
- **Default:** empty
- **Scope:** User or workspace

### `ember.rememberLastModel`

Start new chats with the model you last selected in a chat.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.roles.embeddings`

The embeddings endpoint and model (Settings › Models › Roles): `{ endpoint, model, dimensions?, queryPrefix? }`.

- **Type:** object or null
- **Default:** `null`
- **Scope:** Application (all windows and profiles)

### `ember.roles.rerank`

The rerank endpoint and model (Settings › Models › Roles): `{ endpoint, model }`.

- **Type:** object or null
- **Default:** `null`
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
