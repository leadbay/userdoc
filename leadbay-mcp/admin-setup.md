# Admin setup

**For workspace and organization admins.** This page walks you through adding the
Leadbay connector once, for your whole organization, so every member can connect
without needing admin rights themselves.

If you landed here because a teammate asked you to "add the Leadbay connector" —
you're in the right place. It takes a couple of minutes, there are no API tokens
to hand out, and each member still signs in with **their own** Leadbay account.

> **Are you sure you need this?** Only **organization** plans gate custom connectors behind an admin — **Claude** Team/Enterprise and **ChatGPT** Business/Enterprise. On an individual paid plan (Claude Pro/Max, ChatGPT Plus/Pro) there's no admin step; add the connector yourself via the [Quickstart](quickstart.md) or [Installation](installation.md) guide.

---

## Claude (Team & Enterprise)

As a **primary owner or admin**, add Leadbay as an **organization** custom connector. Once added, it appears in every member's directory and they connect individually.

1. **[Add the Leadbay connector →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Fmcp)** — the form opens with the name and URL prefilled.
2. If Claude offers a scope choice, pick **organization** so every member gets it. Leave Advanced settings as they are (**Individual sign-in** — each member uses their own Leadbay login; you're not sharing one account), then click **Add**.

That's the admin part done — Leadbay now shows up in your members' connector directory. (In a Team/Enterprise workspace members don't have the **Add custom connector** option themselves, which is why this step exists.)

**What your members do next:** in Claude, **Settings → Connectors → search "Leadbay" → Connect**, then sign in with their own Leadbay account. Full walkthrough in the [Quickstart](quickstart.md).

---

## ChatGPT (Business & Enterprise)

On Business and Enterprise workspaces, custom MCP connectors are off until a
**workspace owner or admin** allows them. You don't add Leadbay for everyone here
— you unlock the ability, and each member then adds it themselves.

1. Open your **workspace settings** (workspace menu, bottom-left → **Settings**).
2. Under the connector / apps controls, **allow custom connectors** for the
   workspace (this is the workspace-level switch that gates Developer-mode custom
   apps for members).
3. Let your members know they can now add Leadbay.

### What your members do next

Unlike Claude, ChatGPT members add the app themselves once you've allowed custom
connectors. Send them the **ChatGPT** section of the
[Installation](installation.md) guide — each member:

1. Turns on **Developer mode** (Settings → Apps → Advanced settings).
2. Clicks **Create app** and fills in **Name** `Leadbay MCP`, **Server URL**
   `https://mcp.leadbay.app/mcp`, and **Authentication: OAuth**.
3. Clicks **Sign in with Leadbay MCP** and logs in with their own Leadbay account.
4. Enables the **Leadbay MCP** app from the composer **+** / tools menu, then asks
   for leads.

{% hint style="info" %}
The exact wording and location of the "allow custom connectors" control changes
as ChatGPT's admin console evolves. If you can't find it, search the workspace
settings for **connectors** or **apps**, or check OpenAI's current admin
documentation.
{% endhint %}

{% hint style="info" %}
**Claude Code and Codex need no admin step** — they're per-user CLI clients with
no organization gate. Each member just runs the one-line add command from the
[Installation](installation.md) guide on their own machine.
{% endhint %}

---

## Where to next

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}
