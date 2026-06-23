# What is Leadbay MCP?

**Leadbay MCP connects Claude to your Leadbay account, so you can work your leads by simply asking.**

Pull leads, qualify them, draft outreach, log activity — in plain language. Claude acts on your real data, with your permissions, just as you would in the app.

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

## Where it works

Leadbay MCP works with any AI assistant that supports the Model Context Protocol:

- **Claude Desktop**
- **Claude Cowork**
- **Claude Code**
- **Cursor**
- **Codex**

---

## Key concepts

A few Leadbay terms show up in prompts and responses. You don't need to manage any of them to get started — Claude handles the details — but knowing what they mean helps:

| Term | What it means |
|------|---------------|
| **Lens** | Your saved audience — the sector, company size, and criteria that define which leads Leadbay surfaces. You can have several and switch between them ("switch to my Joinery lens"). |
| **Score** | A 0–100 firmographic fit score on every lead — how well it matches your audience. Shown as a bar in lead tables. |
| **AI score** | A deeper qualification score on the top leads in each batch, from targeted web research against your qualification questions. Most leads ship with the basic score; the best get AI-qualified. |
| **Taste profile** | What Leadbay learns from your likes, dislikes, and outreach — it tunes future scoring to your judgement. Liking a lead in chat teaches it. |
| **Read vs write** | **Read** tools only pull data (leads, profiles, contacts) and never change anything. **Write** tools take action (qualify, enrich, log outreach, edit lenses). Both are scoped to your account — every write is something you could do yourself in the app, with nothing destructive at the platform level. You control how much your client asks before each action through its tool-permission settings. |

These are covered in depth in the [Lenses](../product-guides/lenses.md) and [AI Assistant](../product-guides/ai-assistant.md) product guides.

---

## Next step

Ready to connect? The Quickstart gets you to your first leads in about five minutes.

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}
