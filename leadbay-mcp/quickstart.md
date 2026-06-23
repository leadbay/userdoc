# Quickstart

Connect Leadbay to Claude and get your first qualified leads in about five minutes. Pick your client, install, sign in, and ask — no coding, no tokens to copy.

{% hint style="info" %}
You'll need a [Leadbay account](https://leadbay.ai/) and an AI assistant that supports MCP (Claude Desktop, Claude Cowork, Claude Code, or Cursor — Codex too). That's it — no API tokens to copy or paste. _ChatGPT support is coming soon._
{% endhint %}

---

## Step 1 — Install

**On Claude (Desktop / Cowork) — `.dxt` extension** (recommended):

1. **[⬇ Download the Leadbay extension (.dxt)](https://github.com/leadbay/leadclaw/releases/latest/download/leadbay-latest.dxt)** — this downloads the latest version directly.
2. **Double-click the downloaded `.dxt`.** Claude opens with the extension details — click **Install**, then toggle the extension to **Enabled**.

{% hint style="info" %}
Doesn't open Claude? Install it from inside the app: **Settings → Extensions → Advanced → Install extension**, then pick the `.dxt` file.
{% endhint %}

**On Claude Code, Cursor, or Codex — one-command installer** (needs [Node.js](https://nodejs.org) 22+). It also works for Claude Desktop if you'd rather automate the setup:

```bash
npx -y -p @leadbay/mcp@latest installer
```

This opens a guided wizard that detects your installed clients, adds Leadbay to the ones you pick, and runs the sign-in flow.

---

## Step 2 — Sign in (this happens automatically)

You don't set anything up by hand. The moment you install — or the first time Claude uses a Leadbay tool — a **Sign in with Leadbay** page **opens automatically in your browser**:

1. The Leadbay login page appears on its own.
2. Log in (or confirm your existing session).
3. Click **Approve** to connect Claude to your account.
4. The tab closes itself and Claude is ready.

That's the whole connection. No tokens, no config files. Claude is now linked to **your** account, with all the leads you already have in Leadbay. You can revoke access anytime from **Settings → Connected apps**.

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

<figure><img src="../.gitbook/assets/mcp-pull-leads-shortlist.png" alt="A ranked table of prospects with fit, why-it-qualifies, and contact, plus Claude's pick of the top two to open first"><figcaption><p>A successful first reply: a ranked table of prospects, then the two worth opening first.</figcaption></figure>

---

## Step 5 — Keep going

Once you've seen your first leads, try these:

> *Research the top one for me — is it a fit?*

> *Draft me an outreach email to them.*

> *I just emailed them. Log it as outreach.*

Claude remembers the leads it surfaced, so you can keep referring to "the top one" without repeating yourself.

---

## Using Leadbay with Claude Desktop

Claude Desktop is slower than Cowork to load MCP tools, so a couple of extra precautions help.

After installing the Leadbay extension, **fully quit and relaunch Claude Desktop** (Cmd-Q on Mac, then reopen — not just closing the window). Open a new chat and wait about **30 seconds** before sending your first message. This gives Claude time to load the Leadbay tools.

If your first message gets a response like *"I don't see any Leadbay tools"* or *"I can't find Leadbay in your setup"*, don't worry — the tools are still loading. Send any second message (even just *"try again"*) and Claude will pick them up. From that point on, the rest of your session works normally.

---

## Updating

For the **`.dxt` extension**, when a new release ships, repeat **Step 1** (download the new `.dxt`, double-click, Install). Claude replaces the old version in place; your sign-in stays valid, so you don't need to re-authenticate.

The **one-command installer** always runs the latest version — there's nothing to update.

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| Claude says "not authenticated" or 401 errors | Your sign-in may have expired or been revoked. Trigger any Leadbay tool again and Claude will re-prompt the **Sign in with Leadbay** flow |
| Tools don't appear after install | Make sure the extension toggle is **Enabled** in Settings → Extensions |
| Tools appear but Claude won't call them | Open **Configure** and switch the tool groups to **Always allow** |
| Connected, but "show me leads" returns an empty list | You're signed in fine — there's just nothing to show right now. Ask *"show me my lenses"* to confirm which audience is active and switch if needed, or check you're on the right instance (US vs EU) |
| Wrong instance (no leads / 404s) | Sign out from the Leadbay extension and sign back in on the right instance (US or EU) |
| Other issue | File a bug at [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |

---

## Where to next

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
