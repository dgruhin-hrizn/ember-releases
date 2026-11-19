# Settings: Bonfire

Every setting in Settings › Bonfire: type, default, values and what it does.

These settings are in **Settings › Bonfire** (and in your `settings.json`).

### `ember.bonfire.animations`

Bonfire's light and extinguish animations on its tab: the fire climbing when a build is lit and burning down when it's extinguished. Off: a quick fade (as with reduced motion).

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.bonfire.enabled`

Offer **Bonfire**: building a plan's independent to-dos at the same time, one chat and worktree each. Off by default: Build runs here or in a new chat, and no Bonfire menus, views or tools show.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.bonfire.maxParallel`

Bonfire: how many of a plan's to-dos work at the same time, each an ordinary chat in its own worktree. A to-do that waits for others starts once their pull requests have merged.

- **Type:** integer
- **Default:** `4`
- **Range:** 1 to 64
- **Scope:** Application (all windows and profiles)

### `ember.plans.defaultBuild`

What a plan's Build button does. The other ways stay in its ▾ menu.

- **Type:** one of the values below
- **Default:** `"here"`
- **Scope:** User or workspace

| Value | Meaning |
|---|---|
| `"here"` | Build here: one to-do after another in the plan's chat. |
| `"newChat"` | Build in a new chat, with the plan as context. |
| `"bonfire"` | Light Bonfire: independent to-dos at the same time. With fewer than two independent to-dos, its preview says so before anything starts. |

---

[All documentation](../README.md)
