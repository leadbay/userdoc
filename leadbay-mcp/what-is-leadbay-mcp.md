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

## Key concepts

A few Leadbay terms show up in prompts and responses. You don't need to manage any of them to get started — Claude handles the details — but knowing what they mean helps:

| Term | What it means |
|------|---------------|
| **Lens** | Your saved audience — the sector, company size, and criteria that define which leads Leadbay surfaces. You can have several and switch between them ("switch to my Joinery lens"). |
| **Score** | A 0–100 firmographic fit score on every lead — how well it matches your audience. Shown as a bar in lead tables. |
| **AI score** | A deeper qualification score on the top leads in each batch, from targeted web research against your qualification questions. Most leads ship with the basic score; the best get AI-qualified. |
| **Taste profile** | What Leadbay learns from your likes, dislikes, and outreach — it tunes future scoring to your judgement. Liking a lead in chat teaches it. |
| **Read vs write** | **Read** tools only pull data (leads, profiles, contacts) and never change anything. **Write** tools take action (qualify, enrich, log outreach, edit lenses). Both are scoped to your account, and Claude confirms before anything that writes. |

These are covered in depth in the [Lenses](../product-guides/lenses.md) and [AI Assistant](../product-guides/ai-assistant.md) product guides.

---

## How sign-in works

You never copy, paste, or rotate API tokens. The first time Claude calls a Leadbay tool, a **Sign in with Leadbay** page opens in your browser — you log in, click **Approve**, and Claude is connected to your account. You can revoke access anytime from **Settings → Connected apps** in Leadbay.

---

## Next step

Ready to connect? The Quickstart gets you to your first leads in about five minutes.

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}
