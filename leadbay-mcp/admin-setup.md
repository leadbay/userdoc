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

**1. Open the Add custom connector form.** Use this link (or in Claude, go to
**Settings → Connectors**, then the **+** next to the search bar → **Add custom
connector**):

{% hint style="info" %}
[https://claude.ai/customize/connectors?modal=add-custom-connector](https://claude.ai/customize/connectors?modal=add-custom-connector)
{% endhint %}

<figure><img src="../.gitbook/assets/claude-02-connectors-plus-menu.png" alt="Connectors + menu with Add custom connector"><figcaption><p>The + menu → Add custom connector</p></figcaption></figure>

**2. Add it for the organization.** Fill in the fields, and if Claude offers a
choice of scope (organization vs. just you), choose the **organization** scope so
every member gets it:

- **Name:** `Leadbay`
- **URL:** `https://mcp.leadbay.app/mcp`

Leave the Advanced settings as they are — **Individual sign-in** is what you want.
Each member authenticates with their own Leadbay login; you are **not** sharing
one account across the team.

<figure><img src="../.gitbook/assets/claude-01-add-custom-connector-form.png" alt="Add custom connector form with Leadbay name and URL"><figcaption><p>Name it Leadbay, paste the URL, click Add</p></figcaption></figure>

**3. Click Add.** That's the admin part done — Leadbay now shows up in your
members' connector directory.

{% hint style="info" %}
**Members can't add it themselves.** In a Team or Enterprise workspace, members
don't have the **Add custom connector** option — that's exactly why this admin
step exists. Once you've added it, they just search "Leadbay", open it, click
**Connect**, and sign in.
{% endhint %}

**What your members do next:** point them at the [Quickstart](quickstart.md). They
open the **Leadbay** connector, click **Connect**, and sign in with their own
Leadbay account — no further admin involvement needed.

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

**What your members do next:** each member follows the **ChatGPT** section of the
[Installation](installation.md) guide — turn on Developer mode, **Create app**
with **Name** `Leadbay MCP`, **Server URL** `https://mcp.leadbay.app/mcp`, and
**OAuth**, then sign in with their own Leadbay account.

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
