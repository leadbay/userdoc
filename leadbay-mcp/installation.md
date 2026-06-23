# Installation

Connecting Leadbay takes about a minute. Pick the path that matches your client:

- **On Claude (Desktop / Cowork):** the **`.dxt` extension** — download one file and double-click to install. Recommended.
- **On Claude Code, Cursor, or Codex:** the **one-command installer**. It also works for Claude Desktop.

Advanced setup and other clients are covered in the [Leadbay MCP README](https://github.com/leadbay/leadclaw#install).

{% hint style="info" %}
The MCP server uses **your** Leadbay account, so any action Claude takes is the same as if you'd done it yourself in the app.
{% endhint %}

---

## What you'll need

- A Leadbay account ([sign up here](https://leadbay.ai/) if you don't have one)
- An AI assistant that supports MCP — Claude, Claude Code, Cursor, or Codex
- One minute

---

## On Claude — `.dxt` extension (recommended)

For **Claude Desktop and Claude Cowork**, the simplest setup is to download a single extension file and double-click it. (Using Claude Code, Cursor, or Codex instead? Skip to the [one-command installer](#one-command-installer-claude-code-cursor-codex) below.)

### Step 1 — Download the latest extension

Open the [LeadClaw releases page](https://github.com/leadbay/leadclaw/releases/latest) and download the latest `.dxt` file (look for a name like `leadbay-X.Y.Z.dxt` under the release's **Assets**).

---

### Step 2 — Double-click to install

**Double-click the downloaded `.dxt` file.** Claude opens with the extension details — click **Install** to confirm, then toggle the extension to **Enabled**. That's it.

{% hint style="info" %}
Prefer to install from inside the app? Go to **Settings → Extensions → Advanced → Install extension** and pick the `.dxt` file instead of double-clicking.
{% endhint %}

---

### Step 3 — Sign in with Leadbay

The first time Claude calls a Leadbay tool, it triggers a one-tap **Sign in with Leadbay** flow:

1. A Leadbay login page opens in your browser
2. Log in (or confirm your existing session)
3. Click **Approve** to grant Claude access to your account
4. The browser tab closes itself and Claude continues the conversation

That's it — no tokens to mint, copy, paste, or rotate. The connection is scoped to your account and you can revoke it anytime from **Settings → Connected apps** in Leadbay.

{% hint style="info" %}
If you have access to both the US and EU instances of Leadbay, sign in on the instance you want Claude to use. You can switch later by signing out from the Leadbay extension and signing back in on the other instance.
{% endhint %}

---

### Step 4 — Allow the tools

Leadbay ships two flavors of tools:

| Flavor | What's in it | Recommended permission |
|--------|--------------|------------------------|
| **Read-only** | Pulls leads, lenses, profiles, contacts, taste profile, enrichment quota — never changes anything | **Always allow** |
| **Write / delete** | Qualifies leads, enriches contacts, adds notes, imports leads, reports outreach, refines audience | **Always allow** |

Both flavors are safe to always-allow because the Leadbay MCP is **scoped to your account** — there's nothing destructive at the platform level. Setting both to "always allow" makes Claude flow without interrupting you for permission on every call.

To configure: in the Leadbay extension's **Configure** screen, set **Always allow** for both the read-only tool group and the write/delete tool group.

---

## One-command installer (Claude Code, Cursor, Codex)

For **Claude Code, Cursor, or Codex**, one command installs Leadbay and signs you in. It also works for **Claude Desktop** if you'd rather automate the setup than install the `.dxt` by hand. You'll need [Node.js](https://nodejs.org) 22 or newer.

```bash
npx -y -p @leadbay/mcp@latest installer
```

This opens a guided wizard that detects your installed clients (Claude Desktop, Claude Code, Cursor, Codex), adds Leadbay to the ones you pick, and runs the **Sign in with Leadbay** flow.

To remove Leadbay later from every client the installer set up:

```bash
npx -y -p @leadbay/mcp@latest installer --uninstall
```

---

## You're connected

That's it — Leadbay is set up. Head to the Quickstart for your first prompt and what a successful result looks like.

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}

---

## Using Leadbay with Claude Desktop

Claude Desktop is slower than Cowork to load MCP tools, so a couple of extra precautions help.

After installing the Leadbay extension, **fully quit and relaunch Claude Desktop** (Cmd-Q on Mac, then reopen — not just closing the window). Open a new chat and wait about **30 seconds** before sending your first message. This gives Claude time to load the Leadbay tools.

If your first message gets a response like *"I don't see any Leadbay tools"* or *"I can't find Leadbay in your setup"*, don't worry — the tools are still loading. Send any second message (even just *"try again"*) and Claude will pick them up. From that point on, the rest of your session works normally.

---

## Updating

For the **`.dxt` extension**, when a new release ships, repeat **Step 1** (download the new `.dxt`) and **Step 2** (Install extension). Claude replaces the old version in place; your sign-in stays valid, so you don't need to re-authenticate.

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
