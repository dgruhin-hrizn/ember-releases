# Watch a pull request

Let a chat watch a GitHub pull request and fix failing checks, merge conflicts and review comments until it is green. It never merges.

Watch PR keeps an eye on one open GitHub pull request and keeps it moving. About once a minute it checks the pull request.
When something needs work, it sends a turn to a dedicated chat on the PR's branch:

- **Failing checks**: the chat gets the failing part of each failing job's log (the failing tests, their errors and the summary; it reads the whole log with `gh` when it needs more), fixes the code, commits and pushes.
- **Merge conflicts** with the base branch: the chat brings the branch up to date and resolves them.
- **New review comments**: the chat addresses them.

When every check passes, nothing conflicts and nothing new is waiting, the pull request is green: Ember tells you and
stops watching. If it's still a draft, or waiting on a review or a reviewer's changes, the message says so. **It never merges, closes, approves, labels or edits the pull request on its own.** Merging stays yours: merge on GitHub, or ask in its chat ("merge it") and it does what you ask, under your usual permission level.

## Before you start

- Install the GitHub CLI (`gh`) and sign in with `gh auth login`.
- Open a folder whose `origin` remote is the pull request's GitHub repository.
- The pull request must be open, and its branch must be in that same repository. Pull requests from forks can't be
  pushed to from your worktree, so Ember doesn't watch them.

## Start watching

Use whichever fits:

- In a chat, type `/babysit` to watch the pull request of the folder's current branch, or `/babysit 123` (a number or
  the pull request's URL).
- Run **Watch PR…** from the Command Palette and pick an open pull request from the
  list.
- After you push a worktree chat's branch, the chat's note offers **Watch PR** once the pull request exists.
- On the Dashboard ([The Ember Dashboard](../worktrees/dashboard.md)) or the pull request line at the top of Forge, **Fix with Claude** on a pull request that needs work.

Ember opens a new chat on the pull request's branch, named after it (for example "Watch #123 Fix login redirect"):

- If a worktree already has the branch, the chat works there.
- If your folder is on the branch, the chat works in it.
- Otherwise Ember asks to **Create Worktree** for the branch, so your main worktree stays as it is.

A local branch with the same name only counts when it tracks `origin/<branch>`. If it doesn't, Ember says how to set
its upstream and starts nothing.

If a chat already watches the pull request, Ember takes you to its chat instead (and watches again if it had stopped).

## Watch it work

At the right end of the line at the top of the chat, Ember shows what it is doing, for example **Watching #123 · CI running**, **Fixing 2 failed
checks**, **Resolving conflicts**, **Addressing 1 comment**, **Green ✓** or **Stuck**. The same words appear on the
branch's row in the Ember Dashboard, with its **Pause** and **Stop**. Every step is also written into the chat, so you can read what was tried.

Ember waits while the chat is still working (a turn, or a long push running in the background) and while checks are
running, so it doesn't stack fixes on top of each other.

**Stuck** means it stopped trying: the same problem survived 3 attempts, or 10 turns went by without the pull request
going green. Ember notifies you with the reason. Look at the chat, fix what it couldn't, then click **Continue** to watch
again with a fresh count.

Watching survives a window reload: that line comes back and it picks up where it was.

## Choose how conflicts are fixed

[`ember.babysit.updateStrategy`](../settings/settings-other.md#emberbabysitupdatestrategy) decides how the chat brings a conflicting pull request up to date with its
base branch:

- **merge** (default): merge the base branch into the PR branch and push normally.
- **rebase**: rebase the PR branch onto the base branch and push with `--force-with-lease`.

Only `rebase` ever force-pushes, and only with `--force-with-lease`. Plain `--force` is never allowed. These limits are
enforced on the commands of the turns Watch PR sends, not just asked for. A message you send in the chat yourself
isn't held to them.

## Let it reply to review comments

By default the chat changes code and pushes, but never posts on GitHub. Turn on
[`ember.babysit.replyToComments`](../settings/settings-other.md#emberbabysitreplytocomments) to let it reply briefly on GitHub to the review comments it addressed.

Your own comments (as the signed-in `gh` user) are treated as Ember's replies, never as new work. If Ember can't tell
which GitHub user you are, replies stay off for that pull request.

## Pause, resume and stop

Use the buttons beside those words:

- **Pause**: no checks, no turns, until you resume.
- **Continue**: watch again (after a pause, **Green ✓** or **Stuck**).
- **Stop**: stop watching this pull request. The chat stays as it is.

Watching also stops on its own when the pull request is merged or closed, or when you delete its chat.

> **Note:** Comments and CI logs are passed to the chat as data, not instructions. The chat is told to act only on
> review requests that make sense for the pull request, and to say so plainly when something can't be fixed from your
> machine (a flaky runner, a missing secret, a question for a person).

See also [Worktrees](../worktrees/worktrees.md), [Approvals and Permissions](../chat/approvals.md) and [How to use Forge](forge-howto.md).

---

[All documentation](../README.md)
