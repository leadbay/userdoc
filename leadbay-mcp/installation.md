# Installation

Pick your client below. Each takes a couple of minutes and **none of them need an API token** — you add one server URL, sign in once with your Leadbay account in the browser, and you're connected.

Everywhere a server URL is asked for, use the one for your region:

| Region | Server URL |
|---|---|
| 🇺🇸 US (default) | `https://mcp.leadbay.app/mcp` |
| 🇫🇷 France / EU | `https://mcp.leadbay.app/fr/mcp` |

Use the URL that matches the Leadbay instance your account is on. The steps below show the US URL — French users just swap in `/fr/mcp`.

You need a [Leadbay account](https://leadbay.ai/) (the same login as the web app) and one of the assistants below.

---

## Claude.ai (web)

Add Leadbay as a **custom connector**.

1. **[Add the Leadbay connector →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Fmcp)** — the form opens with the name and URL prefilled. Leave the Advanced settings as they are, then click **Add**.
2. Open the **Leadbay** connector in the directory (search "Leadbay" under **Custom connectors**), click **Connect**, and sign in.

The Leadbay tools become available in your chats. You can scope them per-project in Claude Projects.

> **Not an org admin?** Members can't add a custom connector — your workspace admin adds it once (step 1), then you **Connect** (step 2). See [Admin setup](admin-setup.md). Custom connectors require a paid Claude plan (Pro, Max, Team, or Enterprise).

---

## Claude Desktop

Same **custom connector** as Claude.ai, same URL.

1. **Settings → Connectors → + → Add custom connector**
2. **Name:** `Leadbay` · **URL:** `https://mcp.leadbay.app/mcp` → click **Add**
3. Open the **Leadbay** connector, click **Connect**, sign in.

If your first message gets _"I don't see any Leadbay tools"_, the tools are still loading — send any second message and Claude picks them up. Not an org admin? The admin adds the connector first (see [Admin setup](admin-setup.md)), or use the extension fallback below.

### Fallback: install the extension

No **Add custom connector** option, or not an org admin? Skip the connector and install Leadbay as a **`.dxt` extension** — a per-user double-click install with no admin gate.

1. **[⬇ Download the Leadbay extension (.dxt)](https://github.com/leadbay/mcp/releases/latest/download/leadbay-latest.dxt)**
2. Double-click it → **Install** → toggle to **Enabled**.
3. Open a new chat, click **Connect** on the extension, sign in.

Double-click didn't open Claude? Install from inside the app: **Settings → Extensions → Advanced → Install extension**, then pick the downloaded `.dxt`. On a new release, download and install again — Claude replaces it in place and your sign-in carries over.

---

## Claude Code

One command registers Leadbay for every project:

```bash
claude mcp add --scope user --transport http leadbay https://mcp.leadbay.app/mcp
```

1. Run `/mcp` inside Claude Code.
2. Select **leadbay → Authenticate** — your browser opens for sign-in.
3. Log in and approve. The status flips to **connected** and the tools load.

Ran `add` in an open session? Restart it once so the server shows up in `/mcp`. Remove it anytime with `claude mcp remove leadbay -s user`.

---

## Codex

Codex has a built-in command for remote MCP servers:

```bash
codex mcp add leadbay --url https://mcp.leadbay.app/mcp
```

Codex detects OAuth automatically and opens your browser for the **Sign in with Leadbay** flow — log in and approve. Confirm with `codex mcp list` (you should see `leadbay` with **Status: enabled**, **Auth: OAuth**). Remove it with `codex mcp remove leadbay`.

---

## ChatGPT

Add Leadbay as a custom app (MCP connector).

1. **Settings → Apps → Advanced settings → turn on Developer mode** (from the bottom-left workspace menu).
2. Back on **Apps**, click **Create app**.
3. **Name:** `Leadbay MCP` · **Connection:** Server URL `https://mcp.leadbay.app/mcp` · **Authentication:** OAuth. Check **I understand and want to continue** → **Create**.
4. Click **Sign in with Leadbay MCP**, log in, and approve.

In a chat, enable the **Leadbay MCP** app from the composer **+** / tools menu so ChatGPT can call its tools.

> Custom MCP connectors require a paid ChatGPT plan (Plus, Pro, Business, or Enterprise). On Business/Enterprise an admin may need to allow custom connectors first. If the app disconnects, reconnect it: **Settings → Apps → Leadbay MCP → ⋯ → Reconnect**, then sign in again.

---

## After you connect — your first leads

Whichever client you used, open a new conversation and try:

> _Show me today's leads and tell me which two are worth opening first._

A successful reply is a **ranked shortlist** — each lead with a fit score, a one-line "why it fits", and the best contact. If you see that, you're fully connected. 🎉

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| "Not authenticated" / 401 errors | Your sign-in expired or was revoked. Trigger any Leadbay tool again and approve the **Sign in with Leadbay** prompt. |
| Connected, but "show me leads" returns an empty list | You're signed in fine — there's just nothing to show right now. Ask _"show me my lenses"_ to check which audience is active. |
| Tools don't appear after connecting | Open a new chat and wait a few seconds; send a second message and the tools finish loading. |
| Tools appear but the assistant won't call them | Open the connector settings and set the Leadbay tool groups to **Always allow** (Claude) or enable the connector in the composer (ChatGPT). |
| Custom connector option missing (Claude.ai / Claude Desktop / ChatGPT) | Custom connectors need a paid plan, and your workspace admin may need to enable them — see [Admin setup](admin-setup.md). On **Claude Desktop** you can skip the connector entirely with the [`.dxt` extension fallback](#fallback-install-the-extension). |
| Other issue | File a bug at [github.com/leadbay/mcp/issues](https://github.com/leadbay/mcp/issues). |

---

## Where to next

{% content-ref url="what-is-leadbay-mcp.md" %}
[What is Leadbay MCP?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
