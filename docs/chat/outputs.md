# Outputs

Every canvas and plan Claude made, in one list. Find them by tab, repository or everywhere, open them, see which chat made them, pin, rename, delete and tidy.

**Outputs** lists what Claude made that Ember keeps for you outside your repository: **canvases** and **plans**, from every chat, newest first. They never clutter git, and they stay after a chat's worktree is removed.

It isn't the files Claude edits in your repository. Those are in Changes and Agent Review.

## Where it is

Outputs is a view in **Ember Work**, Ember's side bar, beside Now, Issues and Rules. Its **⋯** menu has **Move Outputs to…**: the left side bar, the right side bar beside the chat, or anywhere else VS Code offers, such as the bottom panel. You can also drag its title. VS Code remembers where you put it.

## Finding an output

- **This tab**, **This repo** or **Everywhere**: this tab's folder, every worktree of its repository, or every folder.
- The buttons along the top filter by kind and show how many of each there are.
- Search matches titles, the chat that made it, its branch, and the text inside the files.
- Pinned outputs stay on top.

Each row says what it is, which chat made it, and when it last changed. The chat's name is a link that opens that chat. A canvas Claude saved before Ember kept track of this says "no chat on record". One whose chat was deleted says "a deleted chat".

## Opening one

Click a row. It opens the way it always does:

- A **canvas** runs beside the chat. A canvas from another folder runs in that folder's window, so here its source opens.
- A **plan** opens in the plan editor.

In a canvas's or a plan's title bar, the **…** menu has **Open Chat** (the chat that made it), **Reveal in Finder** and **Copy Path**. **Show Canvas Source** is there too, for a canvas.

## Pin, rename, delete

Hover over a row:

- **Pin** keeps it on top, and Tidy never deletes it.
- **Rename** changes the name Outputs shows. The file itself stays as it is.
- **Delete** first shows a preview of every file that goes, with its size. Nothing happens until you confirm, and the files go to the Trash.

Ember deletes only what it keeps in its own storage and its plans folder (`~/.ember/plans`), never anything in a
repository. A pinned output has no Delete. Neither does a plan you keep in your own plans folder (Claude Code's `plansDirectory`), or one a chat or a Bonfire run is building in any window; hover over it to see why.

When you confirm, Ember checks again. An output pinned in another window since the preview, one changed since a Tidy preview, or a plan a build started on stays, and the line that appears after says what went and what was kept and why. An output's pin and name are forgotten only once its files are in the Trash.

## Tidy

The footer shows how many outputs there are in the scope and the space they take. **Tidy…** offers two choices, each with how many it would delete:

- **Delete outputs of deleted chats**;
- **Delete outputs untouched for 30 days**.

Each shows a preview first: what goes, and what's kept and why. Pinned outputs are always kept.

## In the chat

When the chat in front made something, its context line at the top of the chat has an **✦ Outputs** button with the count. Click it for a row of cards; a card opens that output, and **Show all in Outputs** lists every output of that chat in the Outputs view. **Chats** shows **✦** and a count beside each chat that made something.

> **Note:** Reviews, browser screenshots, visual-check baselines, chat exports and notes for a new chat aren't listed. Ember either doesn't keep them as files of their own, keeps them in your project, or can't tell which chat made them.

---

[All documentation](../README.md)
