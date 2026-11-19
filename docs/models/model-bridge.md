# Model bridge

Sign in to other subscriptions and use their models in chat next to Claude, through a local bridge that Ember installs, sandboxes and keeps up to date.

The model bridge lets you sign in to other subscriptions — ChatGPT, Gemini, Grok, Kimi, Devin, Meta AI — and pick their models in chat next to Claude. Those chats run through a local bridge (CLIProxyAPI) that starts and stops with Ember. Claude itself never goes through it.

It's in Settings › Models › **Model bridge**.

> **Careful:** Using a consumer subscription outside the provider's own apps may go against its terms, and an account could be limited. Models other than Claude also work less smoothly with Claude Code's tools. Ember asks you to confirm this once, with **I understand**, before you can sign in.

## Turn the bridge on

1. Open Settings › Models and scroll to **Model bridge**.
2. Read the note and click **I understand**.
3. On the **Bridge** row, click **Turn on**.

The **Bridge** row shows its state (for example **Running** and its local port), its version and how the download was checked. Where the system allows it, the bridge runs sandboxed: it can only touch its own files and reach the internet through Ember's allowlist. On Linux only its files are sandboxed; where there is no sandbox, only its environment is limited. The row says which one is used.

The row's buttons: **Restart**, **Show log** and **Turn off**.

## Sign in to a provider

1. Click **Sign in** on the provider's row.
2. Finish signing in in your browser. **Cancel** stops waiting.

Once signed in, the row shows the account, its usage limits where the provider reports them, and **In the model picker**: one **Show** switch per model. A model your subscription doesn't include is marked **Not in your subscription**. **Account** opens the provider's own page, where you can manage or revoke the sign-in.

**Sign out** signs one account out; **Sign out of all** signs out of every provider.

Bridged models then appear in each chat's model picker under the provider's name — see [Choosing models](choosing-models.md). A bridged chat uses that provider's subscription, not your Claude one.

## Updates and cooldown

Ember installs the bridge itself and checks for a new release each time Ember starts. With **Update automatically** on ([`ember.bridge.autoUpdate`](../settings/settings-models.md#emberbridgeautoupdate)), a release is installed only after:

- it has been out for a number of days ([`ember.bridge.updateCooldownDays`](../settings/settings-models.md#emberbridgeupdatecooldowndays), 7 by default) — a bad release is usually pulled within days, and
- its download matches the published checksums.

**Check now** checks straight away. **Show updates and blocked connections** lists what was installed or refused, and any connection the bridge tried that the allowlist blocked.

To run your own copy of CLIProxyAPI instead, set [`ember.bridge.binaryPath`](../settings/settings-models.md#emberbridgebinarypath). Ember never updates a binary set there.

**Open Settings › Models**

---

[All documentation](../README.md)
