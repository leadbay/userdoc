# Leadbay MCP for Claude

Give Claude (Desktop, Code, and Cowork) direct access to your Leadbay account. Once installed, Claude can pull leads, qualify them, enrich contacts, log outreach — all using your real data, with your permissions.

This guide covers installation in **Claude Cowork** via the prebuilt `.mcpb` extension. Other clients (Claude Desktop, Cursor, Claude Code) are covered in the [Leadbay MCP README](https://github.com/leadbay/leadclaw#install).

{% hint style="info" %}
The MCP server is open source and lives at [github.com/leadbay/leadclaw](https://github.com/leadbay/leadclaw). It uses **your** Leadbay account, so any action Claude takes is the same as if you'd done it yourself in the app.
{% endhint %}

---

## What you'll need

- A Leadbay account ([sign up here](https://leadbay.ai/) if you don't have one)
- Claude Cowork (or any Claude client that supports MCP extensions)
- One minute

---

## Step 1 — Download the latest extension

Open the [LeadClaw releases page](https://github.com/leadbay/leadclaw/releases/) and grab the latest `.mcpb` file (look for a name like `leadbay-X.Y.Z.mcpb` under the most recent release's **Assets**).

Save it somewhere easy to find — your Downloads folder works.

---

## Step 2 — Install the extension in Cowork

In Claude Cowork, go to:

**Settings → Extensions → Advanced → Install extension**

Pick the `leadbay-X.Y.Z.mcpb` file you downloaded in Step 1.

A dialog opens with the extension details. Click **Install**, then confirm with **Install** again.

Once installed, toggle the extension to **Enabled**.

---

## Step 3 — Sign in with Leadbay

The first time Claude calls a Leadbay tool, it triggers a one-tap **Sign in with Leadbay** flow:

1. A Leadbay login page opens in your browser
2. Log in (or confirm your existing session)
3. Click **Approve** to grant Claude access to your account
4. The browser tab closes itself and Claude continues the conversation

That's it — no tokens to mint, copy, paste, or rotate. The connection is scoped to your account and you can revoke it anytime from **Settings → Connected apps** in Leadbay.

{% hint style="info" %}
If you have access to both the US and EU instances of Leadbay, sign in on the instance you want Claude to use. You can switch later by signing out from the Leadbay extension in Cowork and signing back in on the other instance.
{% endhint %}

---

## Step 4 — Allow the tools

Leadbay ships two flavors of tools:

| Flavor | What's in it | Recommended permission |
|--------|--------------|------------------------|
| **Read-only** | Pulls leads, lenses, profiles, contacts, taste profile, enrichment quota — never changes anything | **Always allow** |
| **Write / delete** | Qualifies leads, enriches contacts, adds notes, imports leads, reports outreach, refines audience | **Always allow** |

Both flavors are safe to always-allow because the Leadbay MCP is **scoped to your account** — there's nothing destructive at the platform level. Setting both to "always allow" makes Claude flow without interrupting you for permission on every call.

To configure: in the Leadbay extension's **Configure** screen, set **Always allow** for both the read-only tool group and the write/delete tool group.

---

## Try it

Open a Cowork conversation and ask:

> *Pull today's top leads and tell me which two are worth opening this morning.*

Claude will call `leadbay_pull_leads`, `leadbay_get_lead_profile`, and friends — and reply with a short, qualified shortlist.

A few more prompts that work out of the box:

- *Research acme.com — is it a fit for us?*
- *Refine my audience to focus on EU companies hiring sales reps.*
- *I just emailed Jane at Acme. Log it as outreach.*

The full list of tools and recommended workflows is in the [LeadClaw README](https://github.com/leadbay/leadclaw#tools).

---

## Updating

When a new release ships, repeat **Step 1** (download the new `.mcpb`) and **Step 2** (Install extension). Cowork replaces the old version in place; your sign-in stays valid, so you don't need to re-authenticate.

---

## Using Leadbay with Claude Desktop

Claude Desktop is slower than Cowork to load MCP tools, so a couple of extra precautions help.

After installing the Leadbay extension, **fully quit and relaunch Claude Desktop** (Cmd-Q on Mac, then reopen — not just closing the window). Open a new chat and wait about **30 seconds** before sending your first message. This gives Claude time to load the Leadbay tools.

If your first message gets a response like *"I don't see any Leadbay tools"* or *"I can't find Leadbay in your setup"*, don't worry — the tools are still loading. Send any second message (even just *"try again"*) and Claude will pick them up. From that point on, the rest of your session works normally.

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| Claude says "not authenticated" or 401 errors | Your sign-in may have expired or been revoked. Trigger any Leadbay tool again and Claude will re-prompt the **Sign in with Leadbay** flow |
| Tools don't appear in Cowork | Make sure the extension toggle is **Enabled** in Settings → Extensions |
| Tools appear but Claude won't call them | Open **Configure** and switch the tool groups to **Always allow** |
| Wrong instance (no leads / 404s) | Sign out from the Leadbay extension and sign back in on the right instance (US or EU) |
| Other issue | File a bug at [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
