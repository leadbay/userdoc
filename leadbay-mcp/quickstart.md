# Quickstart

Connect Leadbay to Claude and get your first qualified leads in about five minutes. This is the fast path — pick your client, install, sign in, and ask. Detailed options and troubleshooting live in the [Installation](installation.md) guide.

{% hint style="info" %}
You'll need a [Leadbay account](https://leadbay.ai/) and an AI assistant that supports MCP (Claude Desktop, Claude Code, Claude Cowork, Cursor, or ChatGPT). That's it — no API tokens to copy or paste.
{% endhint %}

---

## Step 1 — Install

The recommended path is the **`.dxt` extension** — download one file and install it. (Full details and the other options are in the [Installation](installation.md) guide.)

| Your client | Recommended path |
|---|---|
| **Claude Desktop** or **Claude Cowork** | **`.dxt` extension** — download from releases and install |
| **Claude Code**, **Cursor**, or **Codex** | **One-command installer** — `npx -y -p @leadbay/mcp@latest installer` |

**`.dxt` extension** (recommended): download the latest `leadbay-X.Y.Z.dxt` from the [LeadClaw releases page](https://github.com/leadbay/leadclaw/releases/latest), then **double-click it** to install in Claude.

**One-command installer** (alternative — Code / Cursor / Codex, needs [Node.js](https://nodejs.org) 22+):

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

---

## Step 5 — Keep going

Once you've seen your first leads, try these:

> *Research the top one for me — is it a fit?*

> *Draft me an outreach email to them.*

> *I just emailed them. Log it as outreach.*

Claude remembers the leads it surfaced, so you can keep referring to "the top one" without repeating yourself.

---

## Where to next

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
