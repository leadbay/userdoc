# Quickstart

Connect Leadbay to Claude and get your first qualified leads in about five minutes. This is the fast path — pick your client, install, sign in, and ask. Detailed options and troubleshooting live in the [Installation](installation.md) guide.

{% hint style="info" %}
You'll need a [Leadbay account](https://leadbay.ai/) and an AI assistant that supports MCP (Claude Desktop, Claude Code, Claude Cowork, Cursor, or ChatGPT). That's it — no API tokens to copy or paste.
{% endhint %}

---

## Step 1 — Install

Pick the path that matches your client. (Full details for each are in the [Installation](installation.md) guide.)

| Your client | Fastest path |
|---|---|
| **Claude Desktop** or **ChatGPT** | **Hosted connector** — paste a URL, nothing to install |
| **Claude Code** or **Cursor** | **One-command installer** — `npx -y -p @leadbay/mcp@latest installer` |
| **Claude Cowork** | **Manual `.dxt` extension** — download from releases and install |

**Hosted connector URL** (Desktop / ChatGPT — add it under *Settings → Connectors → Add custom connector*):

| Instance | URL |
|---|---|
| EU / France | `https://leadbay-mcp-prod.fly.dev/fr/mcp` |
| US | `https://leadbay-mcp-prod.fly.dev/mcp` |

**One-command installer** (Code / Cursor — needs [Node.js](https://nodejs.org) 22+):

```bash
npx -y -p @leadbay/mcp@latest installer
```

---

## Step 2 — Sign in (this happens automatically)

You don't set anything up by hand. The moment you install — or the first time Claude uses a Leadbay tool — a **Sign in with Leadbay** page **opens automatically in your browser**:

1. The Leadbay login page appears on its own.
2. Log in (or confirm your existing session).
3. Click **Approve** to connect Claude to your account.
4. The tab closes itself and Claude is ready.

That's the whole connection. No tokens, no config files. Claude is now linked to **your** account, with all the leads and lenses you already have in Leadbay. You can revoke access anytime from **Settings → Connected apps**.

{% hint style="info" %}
If you have both a US and an EU account, sign in on the instance you want Claude to use. You can switch later by signing out and back in on the other instance.
{% endhint %}

---

## Step 3 — Ask for your first leads

Open a new conversation and type:

> *Show me today's leads and tell me which two are worth opening first.*

Claude calls your Leadbay tools and replies with a short, ranked shortlist — company, why it fits, and the best contact to reach.

---

## Step 4 — What you should see

A successful first response looks like a **ranked table of leads**, not a wall of text. For each lead you'll get:

- a **score** (how well it matches your audience),
- a one-line **why it fits**,
- the **best contact** with a link where available.

If Claude replies with leads like that, you're fully connected. 🎉

{% hint style="warning" %}
**Got an empty list or "no leads"?** You're connected, but Claude found nothing to show. Usually that means your active lens has no fresh leads right now, or you're signed in to the wrong instance (US vs EU). Try *"show me my lenses"* to confirm what's active, or see [Troubleshooting](installation.md#troubleshooting).
{% endhint %}

---

## Step 5 — Keep going

Once you've seen your first leads, try these:

> *Research the top one for me — is it a fit?*

> *Draft me an outreach email to them.*

> *I just emailed them. Log it as outreach.*

Claude remembers the leads it surfaced, so you can keep referring to "the top one" without repeating yourself.

---

## Where to next

{% content-ref url="what-is-leadbay-mcp.md" %}
[What is Leadbay MCP?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
