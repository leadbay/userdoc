# Admin setup

**For workspace and organization admins.** This page walks you through adding the
Leadbay connector once, for your whole organization, so every member can connect
without needing admin rights themselves.

If you landed here because a teammate asked you to "add the Leadbay connector" —
you're in the right place. It takes a couple of minutes, there are no API tokens
to hand out, and each member still signs in with **their own** Leadbay account.

{% hint style="info" %}
**Are you sure you need this?** Only **organization** plans gate custom connectors
behind an admin:

- **Claude** — Team and Enterprise workspaces.
- **ChatGPT** — Business and Enterprise workspaces.

On an individual paid plan (Claude Pro/Max, ChatGPT Plus/Pro), there's no admin
step — you can add the connector yourself. Just follow the
[Quickstart](quickstart.md) or [Installation](installation.md) guide.
{% endhint %}

---

## Claude (Team & Enterprise)

As a **primary owner or admin**, you add Leadbay as an **organization** custom
connector. Once it's added, it appears in every member's connector directory and
they connect to it individually.

**1. Click the link below to open the Add custom connector form.** The name and
URL are already filled in:

{% hint style="info" %}
[**Add the Leadbay connector →**](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Fmcp)
{% endhint %}

**2. Add it for the organization, then click Add.** If Claude offers a choice of
scope (organization vs. just you), choose the **organization** scope so every
member gets it. Leave the Advanced settings as they are — **Individual sign-in**
is what you want. Each member authenticates with their own Leadbay login; you are
**not** sharing one account across the team.

<figure><img src="../.gitbook/assets/claude-01-add-custom-connector-form.png" alt="Add custom connector form with Leadbay name and URL prefilled"><figcaption><p>Name and URL are prefilled — set organization scope, then click Add</p></figcaption></figure>

That's the admin part done — Leadbay now shows up in your members' connector
directory.

{% hint style="info" %}
**Members can't add it themselves.** In a Team or Enterprise workspace, members
don't have the **Add custom connector** option — that's exactly why this admin
step exists.
{% endhint %}

### What your members do next

Once you've added the connector, send your team these three steps (no admin
rights needed — each person signs in with their own Leadbay account):

**1. Find the Leadbay connector.** In Claude, open **Settings → Connectors** and
search "Leadbay" — it appears under **Custom connectors**. Open it.

**2. Click Connect and sign in.** A **Sign in with Leadbay** page opens in the
browser — log in and click **Approve**. The tab closes and the connector shows as
connected.

<figure><img src="../.gitbook/assets/claude-04-connect.png" alt="Leadbay connector with the Connect button"><figcaption><p>Click Connect, then sign in with Leadbay</p></figcaption></figure>

**3. Ask for leads.** Open a new chat and try _"Show me today's leads."_ Claude
replies with a ranked shortlist — that means it's fully connected. 🎉

The full member walkthrough (with the first-message tips) lives in the
[Quickstart](quickstart.md).

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
