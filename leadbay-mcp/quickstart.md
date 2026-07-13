# Quickstart

Connect Leadbay to Claude and get your first qualified leads in about five minutes. This guide uses **Claude** (Claude.ai or Claude Desktop) — the simplest path. Using a different assistant? See [Installation](installation.md) for step-by-step setup of Claude Code, ChatGPT, and Codex.

{% hint style="info" %}
You'll need a [Leadbay account](https://leadbay.ai/) and Claude (Pro, Max, Team, or Enterprise). That's it — no API tokens to copy or paste; you add one URL and sign in with your browser.
{% endhint %}

---

## Step 1 — Add the Leadbay connector

**[Add the Leadbay connector →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Fmcp)** — the **Add custom connector** form opens with the name (`Leadbay`) and URL (`https://mcp.leadbay.app/mcp`) already filled in. Click **Add**.

{% hint style="info" %}
Custom connectors require a paid Claude plan. **If you're not an admin of your organization**, you can't add the connector yourself — either send your workspace admin the [Admin setup](admin-setup.md) guide so they add it, or, on **Claude Desktop**, skip the connector entirely and install the [`.dxt` extension](installation.md#fallback-install-the-extension) yourself (a per-user, no-admin install). See [Installation](installation.md) for every client.
{% endhint %}

---

## Step 2 — Sign in

1. Open the new **Leadbay** connector and click **Connect**.
2. A **Sign in with Leadbay** page opens in your browser — log in (or confirm your existing session) and click **Approve**.
3. The tab closes itself and Claude is connected.

That's the whole connection — no tokens, no config files. Claude is now linked to **your** Leadbay account, with all the leads you already have. You can revoke access anytime from **Settings → Connected apps**.

---

## Step 3 — Ask for your first leads

Open a new conversation and type:

> _Show me today's leads and tell me which two are worth opening first._

Claude calls your Leadbay tools and replies with a short, ranked shortlist — company, why it fits, and the best contact to reach.

{% hint style="info" %}
First message gets _"I don't see any Leadbay tools"_? The tools are still loading. Send any second message (even just _"try again"_) and Claude will pick them up.
{% endhint %}

---

## Step 4 — What you should see

A successful first response looks like a **ranked table of leads**, not a wall of text. For each lead you'll get:

- a **score** (how well it matches your audience),
- a one-line **why it fits**,
- the **best contact** with a link where available.

If Claude replies with leads like that, you're fully connected. 🎉

<figure><img src="../.gitbook/assets/mcp-pull-leads-shortlist.png" alt="A ranked table of prospects with fit, why-it-qualifies, and contact, plus Claude's pick of the top two to open first"><figcaption><p>A successful first reply: a ranked table of prospects, then the two worth opening first.</figcaption></figure>

---

## Step 5 — Keep going

Once you've seen your first leads, try these:

> _Research the top one for me — is it a fit?_

> _Draft me an outreach email to them._

> _I just emailed them. Log it as outreach._

Claude remembers the leads it surfaced, so you can keep referring to "the top one" without repeating yourself.

---

## Using another assistant?

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}

Step-by-step setup for **Claude.ai**, **Claude Desktop**, **Claude Code**, **ChatGPT**, and **Codex** — they all use the same `https://mcp.leadbay.app/mcp` endpoint.

---

## Where to next

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
