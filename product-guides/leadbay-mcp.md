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
- Two minutes

---

## Step 1 — Download the latest extension

Open the [LeadClaw releases page](https://github.com/leadbay/leadclaw/releases/) and grab the latest `.mcpb` file (look for a name like `leadbay-X.Y.Z.mcpb` under the most recent release's **Assets**).

Save it somewhere easy to find — your Downloads folder works.

---

## Step 2 — Mint a Leadbay bearer token

The extension needs a token to talk to Leadbay on your behalf.

1. Open a terminal
2. Run:

   ```bash
   npx -y @leadbay/mcp@latest login --email you@yourcompany.com --region us
   ```

   - Replace `you@yourcompany.com` with your Leadbay login email
   - Use `--region us` if you signed up on the US instance, `--region fr` for the French instance

3. You'll be prompted for your password (it's used once to authenticate, then discarded)
4. The CLI prints a **bearer token** (starts with `u.`). Copy it — you'll paste it in Step 4

{% hint style="warning" %}
Treat the token like a password. Anyone with this token can act on your Leadbay account.
{% endhint %}

---

## Step 3 — Install the extension in Cowork

In Claude Cowork, go to:

**Settings → Extensions → Advanced → Install extension**

Pick the `leadbay-X.Y.Z.mcpb` file you downloaded in Step 1.

A dialog opens with the extension details. Click **Install**, then confirm with **Install** again.

Once installed, toggle the extension to **Enabled**.

---

## Step 4 — Configure the token

Still in **Settings → Extensions**, find Leadbay in the list and click **Configure**.

- Paste your bearer token in the `LEADBAY_TOKEN` field
- Set the `LEADBAY_REGION` field to match the one you used at login (`us` or `fr`)
- Save

---

## Step 5 — Allow the tools

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

When a new release ships, repeat **Step 1** (download the new `.mcpb`) and **Step 3** (Install extension). Cowork replaces the old version in place; your token and permissions stay configured.

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| Claude says "not authenticated" or 401 errors | The token may have expired. Repeat **Step 2** to mint a fresh one and paste it in **Configure** |
| Tools don't appear in Cowork | Make sure the extension toggle is **Enabled** in Settings → Extensions |
| Tools appear but Claude won't call them | Open **Configure** and switch the tool groups to **Always allow** |
| Wrong region (no leads / 404s) | Confirm `LEADBAY_REGION` matches where you signed up (`us` vs `fr`) |
| Other issue | File a bug at [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
