# Settings: Phone

Every setting in Settings › Phone: type, default, values and what it does.

These settings are in **Settings › Phone** (and in your `settings.json`).

### `ember.remote.access`

How your phone reaches Ember's remote. Each option's pros and cons are in Settings › Phone.

- **Type:** one of the values below
- **Default:** `"tailscale"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"tailscale"` | Tailscale: your own devices (HTTPS through Serve when your tailnet has HTTPS certificates, else its IP) |
| `"lan"` | Same Wi-Fi: this Mac's local network address (plain http) |
| `"public"` | Public link through a provider (ngrok, Cloudflare or your own URL) |

### `ember.remote.cloudflareHostname`

The public hostname routed to your Cloudflare tunnel (the tunnel token is kept in secret storage).

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.remote.customUrl`

The HTTPS address of your own reverse proxy in front of Ember's remote port.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.remote.enabled`

Control Ember from your phone (Settings › Phone). Off by default.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.remote.ngrokDomain`

Your free ngrok static domain (the authtoken is kept in secret storage).

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.remote.port`

The local port of Ember's remote (on 127.0.0.1 only; reach it from a phone through the access option in Settings › Phone).

- **Type:** integer
- **Default:** `47821`
- **Range:** 1025 to 65535
- **Scope:** Application (all windows and profiles)

### `ember.remote.publicProvider`

The provider of the remote's public link.

- **Type:** one of the values below
- **Default:** `"ngrok"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"ngrok"` |  |
| `"cloudflare"` |  |
| `"custom"` |  |

### `ember.remote.screenshots`

Show Ember window screenshots on the phone. Ember.app then starts with its debugging port on 127.0.0.1 — any program on this Mac could control Ember. Takes effect at the next start.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
