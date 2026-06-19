# What is Leadbay MCP?

Leadbay MCP gives Claude direct access to your Leadbay account. Once connected, you can ask Claude — in plain language — to pull leads, qualify them, enrich contacts, draft outreach, and log activity. Claude does the work using **your** real data, with **your** permissions, the same as if you'd done it yourself in the app.

{% hint style="info" %}
**MCP** stands for *Model Context Protocol* — an open standard that lets AI assistants like Claude securely connect to external tools and data. The Leadbay MCP server is open source and lives at [github.com/leadbay/leadclaw](https://github.com/leadbay/leadclaw).
{% endhint %}

---

## Why connect Leadbay to Claude?

Instead of switching between the Leadbay app and your workflow, you work conversationally:

> *Pull today's top leads and tell me which two are worth opening this morning.*

> *Research acme.com — is it a fit for us?*

> *I just emailed Jane at Acme. Log it as outreach.*

Claude reads your leads, lenses, and taste profile, reasons over them, and replies with a short, qualified answer — then takes the follow-up action you ask for.

---

## What Claude can do

Leadbay exposes its capabilities to Claude as **tools**, grouped into two flavors:

| Flavor | What it covers | Examples |
|--------|---------------|----------|
| **Read-only** | Pulls data, never changes anything | Pull leads, browse lenses, read lead profiles, look up contacts, check enrichment quota |
| **Write / activate** | Takes action on your account | Qualify leads, enrich contacts, add notes, import leads, report outreach, refine your audience |

Everything is **scoped to your account** — there's nothing destructive at the platform level, and any action Claude takes is one you could take yourself in the app.

{% hint style="info" %}
The full, current list of tools and recommended workflows lives in the [LeadClaw README](https://github.com/leadbay/leadclaw#tools).
{% endhint %}

---

## Where it works

Leadbay MCP works with any AI assistant that supports the Model Context Protocol:

- **Claude Desktop**
- **Claude Code**
- **Claude Cowork**
- **Cursor**
- **ChatGPT**

---

## How sign-in works

You never copy, paste, or rotate API tokens. The first time Claude calls a Leadbay tool, a **Sign in with Leadbay** page opens in your browser — you log in, click **Approve**, and Claude is connected to your account. You can revoke access anytime from **Settings → Connected apps** in Leadbay.

---

## Next step

Ready to connect? Head to the installation guide.

{% content-ref url="installation.md" %}
[installation.md](installation.md)
{% endcontent-ref %}
