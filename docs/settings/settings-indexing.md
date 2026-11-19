# Settings: Indexing

Every setting in Settings › Indexing: type, default, values and what it does.

These settings are in **Settings › Indexing** (and in your `settings.json`).

### `ember.docs.maxPages`

The most pages Ember fetches for one docs site (Settings › Indexing › Docs).

- **Type:** number
- **Default:** `100`
- **Range:** 1 to 1000
- **Scope:** User or workspace

### `ember.docs.tool`

Give Claude a read-only `search_docs` tool that searches the docs you added (Settings › Indexing › Docs) on its own, without an @Docs mention. Only chats started while a doc is ready get it. It never asks for approval and fetches nothing. @Docs mentions work either way.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.index.auto`

Index every folder you open and every chat worktree for codebase search, and keep the indexes current (up to 10,000 files each; larger folders sync from Settings › Indexing). Indexes stay in Ember's storage on this computer and always support keyword search; with an embeddings model (Settings › Models › Roles) they add meaning-based search, and chunks go only to that endpoint.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.index.embedConcurrency`

Embedding requests the codebase index keeps in flight (1 or 2). Two keep the embeddings server busy while Ember writes vectors; more don't help, the server is the limit.

- **Type:** number
- **Default:** `2`
- **Range:** 1 to 2
- **Scope:** User or workspace

### `ember.index.embedExclude`

Files that stay keyword-only in the codebase index — searchable by words, never embedded (gitignore-style globs, e.g. `legacy/`, `*.sql`). Lockfiles, minified code, source maps, snapshots, generated code and data files over 64 KB are keyword-only already.

- **Type:** array
- **Default:** `[]`
- **Scope:** User or workspace

### `ember.index.maxTotalGb`

Soft cap (GB) on the space codebase indexes take in Ember's storage. Past it, at start, the least recently used indexes of folders not open anywhere are deleted, then the least recently used vectors of the shared vector cache (a text whose vector is evicted is embedded again only if it is needed). 0 = no cap.

- **Type:** number
- **Default:** `5`
- **Range:** 0 to …
- **Scope:** User or workspace

### `ember.index.reconcileMinutes`

How often (in minutes) every open codebase index re-checks its whole folder for changes the file watcher missed. Unchanged files are skipped. At least 1; 0 turns it off.

- **Type:** number
- **Default:** `10`
- **Range:** 0 to …
- **Scope:** User or workspace

### `ember.index.tool`

Give Claude a read-only `codebase_search` tool over this folder's codebase index (once the folder has one). Takes effect in new chats.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

### `ember.index.yieldToChats`

Pause the codebase index's embedding while a chat uses the same embeddings endpoint, when that endpoint runs on this computer — so the chat stays responsive. Keyword indexing never pauses.

- **Type:** boolean
- **Default:** `true`
- **Scope:** User or workspace

---

[All documentation](../README.md)
