# Fix Problems, Conflicts and Commit Messages

Send an error to Claude to fix, resolve merge conflicts, and write commit messages from Source Control.

Ember adds a few one-click shortcuts that hand everyday problems to Claude: errors and warnings in your code, merge
conflicts, and the commit message for your changes.

## Fix an error or warning

Every error and warning gets two extra quick fixes, in the editor's lightbulb menu and in the Problems panel:

- **Fix with Ember** sends the problem to the chat, with the lines around it, and Claude starts fixing it right away.
  The chat switches to Agent mode for this. If the current chat is working, Ember starts a new one.
- **Add to Chat** adds the problem to the composer as context and sends nothing, so you can add your own words first.

1. Put the cursor on the squiggle, or right-click the problem in the Problems panel.
2. Open the quick fixes (the lightbulb, or VS Code's Quick Fix key).
3. Choose **Fix with Ember** or **Add to Chat**.

The fix shows up as a pending change you can keep or undo (see [Review changes](review-changes.md)).

## Resolve merge conflicts

When a merge or rebase stops on conflicts, the Source Control view lists them under **Merge Changes**. Click
**Resolve Conflicts with Ember** on that group (or right-click a conflicted file), or run
**Resolve Conflicts with Ember**.

Ember starts a chat in Agent mode with every conflicted file attached. Claude resolves each conflict keeping the
intent of both sides, removes the conflict markers, and runs the project's quick checks if there are obvious ones.
It does not commit and does not stage the files: you review the result and finish the merge yourself.

Files excluded by `.emberignore` are left out; Ember tells you which ones to resolve by hand.

## Generate a commit message

In the Source Control view, click the **Generate Commit Message** button in the title bar, or run
**Generate Commit Message**. Claude reads your staged changes (or all changes when
nothing is staged) and the repository's recent commit subjects, then writes a message into the commit box. Edit it
if you like, then commit as usual.

- The message is written by [`ember.commitMessage.model`](../settings/settings-models.md#embercommitmessagemodel) (Haiku unless you change it), on your Claude
  subscription.
- Changes to files excluded by `.emberignore` are never sent.
- Click **Cancel** on the progress notification to stop. If nothing arrives within 60 seconds, try again.
- The message never names Claude and carries no co-author line while [`ember.git.keepClaudeOut`](../settings/settings-other.md#embergitkeepclaudeout) is on
  (it is on by default). Turn it off and attribution lines your Claude settings add go into the message too.

## Keep Claude out of commits and pull requests

With [`ember.git.keepClaudeOut`](../settings/settings-other.md#embergitkeepclaudeout) on (the default), nothing Claude writes in Ember names Claude in your
repository's history or on GitHub:

- A commit, tag or merge message, or a pull request's title or description, that names Claude or Anthropic is sent
  back to Claude to write again. The call shows as **Blocked** in the chat. This holds at every permission level,
  including Run everything, and for subagents. It covers `git commit`, `git merge` and `git tag` messages,
  `gh pr create`, `gh pr edit` and `gh pr merge`, and GitHub tools that open pull requests or commit files.
- Ember's chats add no `Co-Authored-By` line to commits and no "Generated with" footer to pull requests, whatever
  your own `attribution` setting says.
- A name inside a path, a branch or a package (`CLAUDE.md`, `.claude/rules`, `claude/my-branch`,
  `@anthropic-ai/claude-agent-sdk`) is fine; Claude or Anthropic as a word, a co-author line, an email or a link is not.

Turn it off in **Settings › Chats › Git** to let your own attribution settings decide again.

---

[All documentation](../README.md)
