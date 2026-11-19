# Privacy and storage

What Ember keeps on your computer, what leaves it and where it goes, the Storage settings, and how .emberignore keeps files away from Claude.

Ember runs on your computer. It sends your work to a model only when you ask it to, through the services you set up. This page lists what stays local, what leaves and where it goes.

## What stays on your computer

- **Ember's database** — chats, plans, usage, review snapshots, worktrees and which chat wrote each line. It belongs to Ember alone (see Storage settings below).
- **Claude Code transcripts** — in `~/.claude`, where the `claude` CLI keeps them.
- **Codebase indexes** and their vectors, **canvases**, and Ember Help's search vectors — in Ember's storage.
- **API keys and tokens** for your endpoints and remote providers — in your system's secret storage, not in settings files.

## What leaves, and where it goes

| What | Where it goes | When |
| --- | --- | --- |
| Your chats | Anthropic, through the `claude` CLI and your Claude subscription | Every chat on a Claude model. Ember never uses an API key for these. |
| Chats on your own models | The endpoint you added | Only chats that pick one of its models — see [Your own endpoints](../models/own-endpoints.md). |
| Code near your cursor | Your Tab endpoint | While Tab predictions are on. Never `.env` files or files `.emberignore` lists. |
| Chunks of your code, search queries, Ember Help text | Your embeddings (and rerank) endpoint | Only once you set an embeddings role. Without one, codebase search is keyword-only and nothing is sent. |
| Bridged chats | The provider you signed in to, through the local model bridge | Only chats on a bridged model — see [Model bridge](../models/model-bridge.md). Claude never goes through the bridge. |
| What your phone shows | Your phone, through the way in you chose | Only while the remote is on — see [Ember on your phone](../connect/phone.md). With a public link, traffic passes through that provider. |
| A check for a newer Ember | Ember's public releases page | At launch and about every two hours; [`ember.update.mode`](../settings/settings-general.md#emberupdatemode) turns it off. |

Whether Anthropic may use your chats to train its models is a setting on your Anthropic account, not in Ember. Settings › Accounts › **Privacy** links to it and holds Claude Code's own privacy switches.

**Open Settings › Accounts**

## Storage settings

Settings › Storage shows Ember's database:

- **Database** — where the file is and how big it is.
- **Compact** — rebuilds the file without its unused space and shows how much can be reclaimed. Click twice to confirm.
- **Which chat wrote each line** — what Ember remembers about the lines it wrote. **Forget which chat wrote each line** clears it.
- **What it holds** — a count of chats, plans, usage rows, review snapshots, worktrees and the rest.

If Ember can't open its database, the page says nothing is being saved until it can. If the file was damaged, Ember sets it aside, says where, and starts a fresh one.

To delete old chats, see [Delete Old Chats](../chat/delete-old-chats.md).

**Open Settings › Storage**

## .emberignore

A `.emberignore` file at your folder's root (gitignore syntax) keeps files away from Claude's file tools:

- reading or editing a matching file is refused, and so are searches aimed at one; a search of the whole folder skips them;
- @-mentions, diffs and generated commit messages leave them out;
- Tab never sends them, and the codebase index leaves them out;
- with Ember's way of working with files, shell commands Ember understands (such as `cat`, `head`, `grep` on a file or `cp`) are refused on them too.

`.env` files (not templates like `.env.example`) are kept from Claude the same way, and from any shell command that names one — except at the **Run everything** permission level, where Claude reads them like any other file.

> **Careful:** `.emberignore` doesn't cover other shell commands, file names a file listing shows, or searches with their own file filter.

Settings › General › **.emberignore** shows whether a file is active and how many patterns it has. Ember re-reads the file whenever it changes.

### Also block in Claude Code

`.emberignore` is Ember's. To keep the `claude` terminal out of the same files, use **Also block in Claude Code** under it in Settings › General:

1. Choose where to save the rules.
2. Click **Preview** to see them; lines that can't be carried over say why.
3. Click **Add rules**. Each pattern becomes a Read and an Edit deny rule.

**Open Settings › General**

---

[All documentation](../README.md)
