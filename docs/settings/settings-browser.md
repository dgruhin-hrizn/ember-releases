# Settings: Browser

Every setting in Settings › Browser: type, default, values and what it does.

These settings are in **Settings › Browser** (and in your `settings.json`).

### `ember.browser.engine`

What Ember's browser runs on.

- **Type:** one of the values below
- **Default:** `"auto"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"auto"` | The editor's built-in browser tab when this editor has one, else headless Chrome. |
| `"builtin"` | The editor's built-in browser tab: a real browser you sign in to once, shared with Claude. |
| `"headless"` | Ember's own headless Chrome on a separate profile, shown in Ember's Browser tab. |

### `ember.browser.path`

Chromium-based browser the headless engine runs (with its own profile). Empty: Google Chrome, Chromium, Microsoft Edge or Brave, whichever is installed.

- **Type:** string
- **Default:** empty
- **Scope:** Machine (this computer, never synced)

### `ember.browser.tools`

Let Claude use Ember's browser: read pages and take screenshots freely; navigating, clicking and typing ask first (or do as your permission rules say). Takes effect in new chats.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.browser.userAgent`

The user agent pages see in the editor's built-in browser tabs.

- **Type:** one of the values below
- **Default:** `"chrome"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"chrome"` | Pages in the built-in browser see a plain Chrome user agent, so Google, Microsoft and other sign-ins work. |
| `"app"` | Pages see the editor's own user agent (it names the editor and Electron). |

### `ember.browser.visualBaselines`

Where Claude's visual-check baselines, diffs and recordings are kept.

- **Type:** one of the values below
- **Default:** `"project"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"project"` | In the project's .ember/visual folder, which git ignores until you delete its .gitignore. |
| `"storage"` | In Ember's own storage, one folder per project: nothing is written into the project. |

### `ember.canvas.enabled`

Let Claude build canvases: single-file React apps in Ember's storage that open beside the chat (compiled locally, no network). Claude is told how in each new chat.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
