# Settings: Tab

Every setting in Settings › Tab: type, default, values and what it does.

These settings are in **Settings › Tab** (and in your `settings.json`).

### `ember.roles.tab`

Ember Tab's endpoint and model (Settings › Models › Roles): `{ endpoint, model, wire }` — `wire` is `completions`, `fim` or `fim-prompt`.

- **Type:** object or null
- **Default:** `null`
- **Scope:** Application (all windows and profiles)

### `emberTab.debounceMs`

Wait this long after typing before asking for a prediction.

- **Type:** number
- **Default:** `50`
- **Range:** 0 to 1000
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.disabledLanguages`

Language ids with no predictions (for example `markdown`, `plaintext`). The status bar menu adds and removes the current file's language.

- **Type:** array
- **Default:** `[]`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.enabled`

Show next-edit predictions.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.endpoint`

> **Deprecated.** Set in **Ember Settings › Tab**: Ember Tab uses the Tab role's endpoint and model.

OpenAI-compatible **completions** endpoint (oMLX default; Ollama: `http://localhost:11434/v1/completions`). Must not apply a chat template.

- **Type:** string
- **Default:** `"http://localhost:8000/v1/completions"`
- **Scope:** Application (all windows and profiles)
- **Extension:** Ember Tab

### `emberTab.maxTokens`

Maximum tokens per prediction.

- **Type:** number
- **Default:** `512`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.model`

> **Deprecated.** Set in **Ember Settings › Tab**: Ember Tab uses the Tab role's endpoint and model.

Model id or alias on the server (Zeta 2.1).

- **Type:** string
- **Default:** `"zeta-2.1"`
- **Scope:** Application (all windows and profiles)
- **Extension:** Ember Tab

### `emberTab.prependBos`

Prepend the model's BOS token to the prompt (enable if your server does not add it).

- **Type:** boolean
- **Default:** `false`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.relatedFiles`

Show the model short excerpts of related files: files this one imports, recently edited or viewed files and other open editors in the same workspace folder. Files excluded by `.emberignore` or ignored by git, secrets, and files outside the workspace are never included.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.suggestInComments`

Show predictions while the cursor is inside a comment.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.temperature`

Sampling temperature.

- **Type:** number
- **Default:** `0`
- **Scope:** User or workspace
- **Extension:** Ember Tab

### `emberTab.whitespaceOnlySuggestions`

Show predictions that only change whitespace.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace
- **Extension:** Ember Tab

---

[All documentation](../README.md)
