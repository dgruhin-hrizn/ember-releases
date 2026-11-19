# @Docs

Fetch a documentation site to this computer. Claude searches it on its own, or mention it with @Docs so Claude reads the matching pages.

@Docs lets Claude answer from a library's or service's own documentation. Ember fetches the docs site once and keeps
it on this computer. Claude searches it on its own when a question is about that library, and when you mention it in
a message, the passages that match your message go to Claude with it.

## Add a docs site

1. Open Settings › Indexing and scroll to **Docs** (**Open Indexing settings**).
2. Click **Add Doc**.
3. Enter the **URL** of the docs page to start from, for example `https://docs.example.com/guide/`.
4. Optionally give it a **Name** (otherwise the page title is used) and a **Prefix**: only pages under this address
   are fetched. By default the prefix is the folder of the URL you gave.
5. Click **Fetch**, then confirm the site and the page limit.

You can also run **Add Docs…** and paste the URL.

Ember respects the site's `robots.txt` and uses its `llms.txt` when it has one. It fetches at most
[`ember.docs.maxPages`](../settings/settings-indexing.md#emberdocsmaxpages) pages per site (100 by default); a site that hit the limit says **reached the page
limit**.

## Use docs in a chat

In the composer, type `@`, choose **Docs**, and pick the site. Then ask your question as usual. Claude gets the
passages from that site that best match your message.

## Claude searches your docs on its own

You don't have to mention docs for Claude to use them. A chat gets a read-only `search_docs` tool that searches every
docs site that is ready. The tool names your docs by the name you gave them (or their site), so Claude reaches for it
when your question is about one of those libraries or APIs. It gets back the best few passages, each with its page's address.

- The search uses the pages Ember already keeps on this computer. Nothing is fetched while Claude searches.
- It never asks for approval, works in every mode, and subagents can use it too.
- A chat gets the tool when it starts with at least one docs site ready. Docs you add or re-fetch later are searched
  too, but the tool names them only from the chat's next start.
- To keep your docs out of Claude's own searches, turn off [`ember.docs.tool`](../settings/settings-indexing.md#emberdocstool). It takes effect for chats started
  afterwards. @Docs mentions keep working.

## Keep docs up to date

Settings › Indexing lists every docs site with its prefix, how many pages it holds and when it was fetched:

- **Re-fetch** downloads the site again, for example after a new release.
- **Rename** changes the name you mention it by.
- **Delete** removes it.

Docs live in Ember's own storage on this computer and are shared with nothing else.

---

[All documentation](../README.md)
