# Settings: Issues

Every setting in Settings › Issues: type, default, values and what it does.

These settings are in **Settings › Issues** (and in your `settings.json`).

### `ember.issues.github`

List the open issues of the folder's GitHub repository in Ember: Issues (through the GitHub CLI, `gh auth login`).

- **Type:** boolean
- **Default:** `true`
- **Scope:** User, workspace or folder

### `ember.issues.jira.email`

The email you sign in to Jira with (used with your API token).

- **Type:** string
- **Default:** empty
- **Scope:** User, workspace or folder

### `ember.issues.jira.query`

Which Jira issues Ember: Issues lists: a project key (its open issues), or JQL. Empty: your open issues.

- **Type:** string
- **Default:** empty
- **Scope:** User, workspace or folder

### `ember.issues.jira.site`

Your Jira Cloud site, e.g. `https://your-team.atlassian.net`. The API token is kept in secret storage, for this site only.

- **Type:** string
- **Default:** empty
- **Scope:** User, workspace or folder

### `ember.issues.sync`

Tracker sync: when you start work on a ticket its Jira issue moves to `ember.issues.syncInProgress`; when its pull request opens, to `ember.issues.syncInReview`, with the pull request's link commented; GitHub issues get `Fixes owner/repo#N` in the pull request's description. Only through the project's own transitions. Off until you turn it on.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.issues.syncInProgress`

Tracker sync: the Jira status a ticket moves to when work on it starts (your project's own word).

- **Type:** string
- **Default:** `"In Progress"`
- **Scope:** Application (all windows and profiles)

### `ember.issues.syncInReview`

Tracker sync: the Jira status a ticket moves to when its pull request opens (your project's own word).

- **Type:** string
- **Default:** `"In Review"`
- **Scope:** Application (all windows and profiles)

---

[All documentation](../README.md)
