# Plan from GitHub and Jira issues

List your open GitHub and Jira issues in one list, pick some and plan from them in a Plan-mode chat, or let Claude suggest groups that each make one Bonfire plan.

Ember: Issues lists the open issues of your folder's GitHub repository and of your Jira Cloud site in one list. Pick
one or more and press **Plan from N picked**: a Plan-mode chat opens with the issues in its message box. Or press
**Suggest groupings** and Claude proposes groups of issues that make sense to plan and build together, each as one
Bonfire plan.

Open it with <kbd>⌘K ⇧I</kbd> (<kbd>Ctrl+K Shift+I</kbd> on Windows and Linux) (outside an editor or the terminal), **Ember: Issues**
from the Command Palette, or **Issues** in the **Ember Work** side bar. The chat's `@` menu has **Issues** too, to
attach one issue to a message.

## Issues in the side bar

The **Ember Work** side bar shows **Issues** under Now and Outputs. Tickets you already work on in Ember come first, under **In
progress**: each shows its branch's state as a coloured dot (rest the pointer on it for Needs you, Working, Waiting or
Ready), then its pull request and next step, for example **#41 ✓ · Merge #41**. Click one to open its chat, in
whichever tab or window it lives, or with no chat on it, its branch in its tab. **Assigned to me** comes next: the open
issues assigned to you, most with **no work yet**. For GitHub that's the account `gh` signs in as (`gh api user`); for
Jira, the account your API token signs in as, whatever **Which issues** lists. If Ember can't tell who you are on a
source, it says so and shows none of that source's issues as yours. With nothing in progress and nothing assigned to
you, it says **Nothing assigned to you** with a link to every open issue. Click an issue, **+N more** or **Open the
full list** for the full list. **Refresh** reads the lists again.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-side.dark.webp">
    <img alt="Issues in the side bar: tickets with work in Ember first, with their state, pull request and next step, then the ones assigned to you" src="../images/issues-side.light.webp" width="820">
  </picture>
  <br><em>Issues in the side bar: tickets with work in Ember first, with their state, pull request and next step, then the ones assigned to you</em>
</p>

## Work in Ember

The full list leads with **Key**, **Title**, **Status** and **Work in Ember**. The Work in Ember column shows the
branch that names the ticket (a Jira key like `ABC-128`, or `gh-212` for GitHub issue #212) the way the branches board
does: its state's dot, then branch · pull request with CI · next step, for example
`feat/ABC-123-infra · #41 ✓ · Merge #41`. Short of room, the branch shortens first. Rest the pointer on it for its
state word; click it to open the chat working on it, or, with no chat on it, the branch in its tab. A GitHub issue only
matches branches of the repository you're reading its issues from; a Jira key matches in any repository.

## Start on one ticket

In the issue's column at the right, under **Start work on this ticket**, each way says what it does and names the
branch it would make. **Start in a new worktree** also names where it starts, by the same rule a new worktree
uses: your tab's branch, or, when Claude Code's `worktree.baseRef` is `fresh`, the remote's default branch (for
example `origin/main`); `head` means the tab's branch as it is. For a ticket with no work yet, **Start in a new
worktree** is the highlighted next step:

- **Start in a new worktree**: a new chat set to work in its own worktree and branch, named from the ticket with
  your branch prefix ([`ember.agentBranchPrefix`](../settings/settings-worktrees.md#emberagentbranchprefix), for example `ember/ABC-128-csv-export`). This tab doesn't change.
- **Start here, on a new branch**: this tab switches to that branch when you send.
- **Plan it first**: a Plan-mode chat with the ticket, on the Claude account picked in the view, as **Plan from N
  picked** does. Big tickets go to Bonfire from there.

The ticket waits in the new chat's message box, marked as information for Claude rather than instructions; add what
you know, then send it.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-start.dark.webp">
    <img alt="A ticket with no work yet: its line, its description and three ways to start, naming the branch from the repository's template and where it starts (here worktree.baseRef fresh: the remote's default branch); three tickets picked to plan from" src="../images/issues-start.light.webp" width="820">
  </picture>
  <br><em>A ticket with no work yet: its line, its description and three ways to start, naming the branch from the repository's template and where it starts (here worktree.baseRef fresh: the remote's default branch); three tickets picked to plan from</em>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-list.dark.webp">
    <img alt="Ember: Issues — open GitHub and Jira issues in one list, each with its work in Ember, two picked to plan from" src="../images/issues-list.light.webp" width="820">
  </picture>
  <br><em>Ember: Issues — open GitHub and Jira issues in one list, each with its work in Ember, two picked to plan from</em>
</p>

## Connect GitHub

Ember reads GitHub issues through the GitHub CLI. It never asks for a GitHub token.

1. Install the GitHub CLI (`gh`).
2. Run `gh auth login` in a terminal.
3. Open a folder whose `origin` remote is on GitHub. Ember lists that repository's open issues.

Turn GitHub issues off with **GitHub issues** in **Settings › Issues**.

## Connect Jira

Ember works with Jira Cloud and signs in with your email and an API token.

1. Create an API token at id.atlassian.com › Security › API tokens.
2. In **Settings › Issues**, fill in:
   - **Site**: your Jira address, for example `https://your-team.atlassian.net`.
   - **Email**: the email you sign in to Jira with.
   - **API token**: paste the token. Ember keeps it in your editor's secret storage. The Settings page only ever shows
     that one is saved, never the token itself.
   - **Which issues**: a project key such as `PROJ` lists that project's open issues. You can also type any JQL. Leave
     it empty to list the open issues assigned to you.
3. Press **Test connection**. Ember tells you who Jira knows you as, and changes nothing in Jira.

The token is saved for that site only. If you change the site, enter the token again. Ember never takes a redirect
with your token, so a site address that redirects somewhere else is refused.

The site, email and issues setting can also be set per folder in that folder's `.vscode/settings.json`, for example
when two projects use different Jira projects. Because a repository can carry that file, Ember asks before it saves
your token for a site the folder's settings chose, and Settings › Issues says so.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-empty.dark.webp">
    <img alt="No tracker connected yet: how to connect GitHub and Jira" src="../images/issues-empty.light.webp" width="820">
  </picture>
  <br><em>No tracker connected yet: how to connect GitHub and Jira</em>
</p>

## Find, sort and filter issues

Each row shows the issue's key, its whole title (on up to two lines; hover for the rest), its status and its work in
Ember, then, when the window is wide enough, its type, priority, assignee, labels and when it last changed. A narrower
table (a small window, or with an issue open beside it) keeps the first four. The header stays put while the list
scrolls.

- **Sort**: click a column's header to sort by it; click again to reverse. ▲ or ▼ shows the column and direction.
  Ember remembers the sort for each folder. Issues without an assignee or priority stay at the bottom.
- **Search**: the search box matches the key, title, labels, assignee, priority and the description's text. Every word
  you type must match.
- **Filter**: the **Type**, **Status**, **Assignee**, **Label** and **Source** menus each take several values (Source
  shows when both GitHub and Jira are connected). Each value shows how many issues have it.
- The count at the right says how many issues are shown, for example **Showing 6 of 8**. **Clear filters** clears the
  search and every filter.
- **Refresh**, at the top right, reads the lists again. Ember reuses a list for up to 45 seconds while you search and
  filter.

GitHub issues take their priority from a label such as `P1` or `priority: high`. Jira issues use Jira's priority.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-filtered.dark.webp">
    <img alt="Sorted by priority and filtered to stories and bugs, with the shown-of-total count" src="../images/issues-filtered.light.webp" width="820">
  </picture>
  <br><em>Sorted by priority and filtered to stories and bugs, with the shown-of-total count</em>
</p>

If a source can't be read (gh signed out, a wrong token, a JQL error), a line at the top says why and what to do. The
other source keeps working.

## Look at an issue without leaving Ember

Click a row, or move with **↑** and **↓** in the list, to show that issue in the column at the right:

- its key, type, status and priority on one line, its whole title and the start of its description
- its work in Ember, if any, and the three ways to start on it
- its assignee, when it changed, and all its labels
- its description, formatted
- its latest comments (up to 5)
- its links: the issue itself, and on Jira its linked issues

Ember reads the description and comments the first time you look at an issue, and keeps them while the issue doesn't
change. Nothing is written to GitHub or Jira. **Open in GitHub** or **Open in Jira** opens the issue in your browser,
as does clicking its key. **Esc** or **×** closes the pane.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-detail.dark.webp">
    <img alt="The issue you're on, in the column at the right: its ticket line, its work in Ember and three starts, then its description, labels, latest comments and links" src="../images/issues-detail.light.webp" width="820">
  </picture>
  <br><em>The issue you're on, in the column at the right: its ticket line, its work in Ember and three starts, then its description, labels, latest comments and links</em>
</p>

## Pick issues

- Tick an issue's box, or press **Space** on the issue you're on, to pick it. The header's box picks every issue shown.
  The count beside the filters says how many are picked, with **Clear**.
- Clicking a row shows it in the pane; it doesn't pick it.

## Plan from N picked

Press **Plan from N picked**, at the top right, with one or more issues picked (up to 50 in one plan). Ember reads each issue again, then opens a new chat in
Plan mode with them in its message box: each issue's key, title, link, type, status and description. Long
descriptions are cut to a sensible size.

Nothing is sent yet. Add what you know (constraints, the parts of the code you care about), then send it. Claude reads
the code and writes a plan with to-dos that Bonfire can build.

With more than one Claude account, pick the account for the plan's chat just before the button.

Issue text comes from outside Ember, so it goes to Claude marked as information, not instructions to carry out.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-plan-chat.dark.webp">
    <img alt="Plan from N picked: a Plan-mode chat with the issues in its message box, ready for what you know" src="../images/issues-plan-chat.light.webp" width="820">
  </picture>
  <br><em>Plan from N picked: a Plan-mode chat with the issues in its message box, ready for what you know</em>
</p>

A link can do the same: `ember://ember.ember-agent/plan?issues=PROJ-12,%234` opens a Plan-mode chat for those issues
(`%23` is `#`; in VS Code or VSCodium the link starts with `vscode://` or `vscodium://`). A link plans at most 10
issues. GitHub issues come from the
folder's repository.

## Suggest groupings

Press **Suggest groupings**. Next to it, choose which issues Claude reads: **all** open issues, the ones your search
and filters **show**, or the ones you **picked**. Claude reads their titles, labels, type, status and the start of
each description, and may look at the repository to see which code they touch. It only reads; it changes nothing.

Claude reads at most the 120 most recently updated of the issues you chose; the box says so when there were more.

While it works, the box shows:

- how long it has been running
- what Claude is doing right now, for example **Reading src/export/csv.ts**, and how many steps it has taken
- which issues it reads, and why that many
- placeholder groups where the results will appear. They pulse gently, stay still if your system reduces motion, and
  pause while the tab is hidden.

It usually takes a minute or two. **Stop** ends it: the box says **Stopped. Nothing was grouped.** with **Retry**.
If it fails, the box says why, also with **Retry**.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-grouping-running.dark.webp">
    <img alt="Suggest groupings at work: the time so far, Claude's current step, what it reads, and where the groups will land" src="../images/issues-grouping-running.light.webp" width="820">
  </picture>
  <br><em>Suggest groupings at work: the time so far, Claude's current step, what it reads, and where the groups will land</em>
</p>

When it's done, the groups slide in, best first, each with a one-line reason. Press **Plan this group** to open a
Plan-mode chat with that group's issues. Suggesting again on the same issues shows the same groups at once.

Groupings run on your default chat model and use your plan's usage like any other Claude turn.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../images/issues-groupings.dark.webp">
    <img alt="Suggested groupings: Claude's groups of open issues, each one plan with a reason" src="../images/issues-groupings.light.webp" width="820">
  </picture>
  <br><em>Suggested groupings: Claude's groups of open issues, each one plan with a reason</em>
</p>

## Tracker sync

Off until you turn it on with **Tracker sync** in **Settings › Issues**
([`ember.issues.sync`](../settings/settings-issues.md#emberissuessync)). It's your setting only: a repository's own settings can't turn it on. Then:

- **Starting work** on a ticket (**Start in a new worktree** or **Start here, on a new branch**, once you send the
  chat's first message) moves its Jira issue to **In Progress** ([`ember.issues.syncInProgress`](../settings/settings-issues.md#emberissuessyncinprogress)).
- **When its pull request opens**, from a chat's **Open PR**, the Jira issue moves to **In Review** ([`ember.issues.syncInReview`](../settings/settings-issues.md#emberissuessyncinreview)) and gets a comment with the
  pull request's link (once). A chat's GitHub issues get `Fixes owner/repo#N` at the top of the description, so they
  close when it merges.

Ember moves an issue only through a transition its Jira project offers into the status you named; if there's none, it
says so and changes nothing. It never moves an issue backwards: one that's already in review or done stays where it
is when work on it starts again, and one already in the status you named is left alone. Use your project's own words
for the statuses (for example **Code Review**). What it did shows in the chat's or Bonfire's note.

## Good to know

- Ember lists up to 100 open GitHub issues and 200 Jira issues, newest first.
- Only Jira Cloud is supported. Jira Server and Data Center are not.
- Ember: Issues reads the folder of the chat you have open. Switch chats (or open another folder) to see another
  repository's issues.

---

[All documentation](../README.md)
