# Installation

Step-by-step setup for every assistant that works with Leadbay. Pick your client below — each takes a couple of minutes, and **none of them need an API token**. You add one server URL, sign in once with your Leadbay account, and you're connected.

{% hint style="info" %}
**Before you start, you need:**

- A [Leadbay account](https://leadbay.ai/) (the same login you use for the web app).
- One of the assistants below: **Claude.ai**, **Claude Desktop**, **Claude Code**, **ChatGPT**, or **Codex**.

Everywhere a server URL is asked for, it's:

```
https://mcp.leadbay.app/mcp
```

Sign-in is handled by your browser (OAuth) — there are no tokens to copy or paste.
{% endhint %}

{% hint style="warning" %}
**US vs EU accounts.** If your Leadbay account is on the **EU** instance, use `https://mcp.leadbay.app/fr/mcp` instead of `https://mcp.leadbay.app/mcp`. When in doubt, the US URL works for most accounts — a valid login is routed to whichever backend owns it.
{% endhint %}

---

## Claude.ai (web)

Add Leadbay as a **custom connector**.

1. In Claude.ai, open **Settings → Connectors** (you'll be sent to the **Customize → Connectors** page).
2. In the **Connectors** column, click the **+** button next to the search bar (**Add custom connector**).
3. Enter:
   - **Name:** `Leadbay`
   - **URL:** `https://mcp.leadbay.app/mcp`
4. Click **Add**, then open the new **Leadbay** connector and click **Connect**.
5. A **Sign in with Leadbay** page opens — log in and approve. The connector now shows as connected, and the Leadbay tools are available in your chats.

{% hint style="info" %}
Custom connectors require a paid Claude plan (Pro, Max, Team, or Enterprise). On Team/Enterprise, an admin may need to enable custom connectors for the workspace before the **+** button appears.
{% endhint %}

---

## Claude Desktop

Claude Desktop connects to Leadbay over the same remote URL as Claude.ai.

1. Open **Settings → Connectors**.
2. Click **Add custom connector**.
3. Enter:
   - **Name:** `Leadbay`
   - **URL:** `https://mcp.leadbay.app/mcp`
4. Click **Add**, then **Connect** on the new Leadbay connector.
5. A **Sign in with Leadbay** page opens in your browser — log in and approve. Claude Desktop is now connected.
6. Open a new chat and wait a few seconds for the Leadbay tools to load before your first message.

{% hint style="info" %}
If your first message gets _"I don't see any Leadbay tools"_, the tools are still loading. Send any second message (even just _"try again"_) and Claude will pick them up.
{% endhint %}

---

## Claude Code

One command registers Leadbay for every project.

```bash
claude mcp add --scope user --transport http leadbay https://mcp.leadbay.app/mcp
```

Then:

1. Run `/mcp` inside Claude Code.
2. Select **leadbay** → **Authenticate**. Your browser opens for the Leadbay sign-in.
3. Log in and approve — the status flips to **connected** and the Leadbay tools load.

{% hint style="info" %}
If you just ran the `add` command in an open Claude Code session, restart it once so the new server shows up in `/mcp`.
{% endhint %}

Remove it anytime with `claude mcp remove leadbay -s user`.

---

## Codex

Codex has a built-in command for remote MCP servers.

```bash
codex mcp add leadbay --url https://mcp.leadbay.app/mcp
```

Codex detects OAuth automatically and opens your browser for the **Sign in with Leadbay** flow — log in and approve. Confirm it's connected with:

```bash
codex mcp list
```

You should see `leadbay` with **Status: enabled** and **Auth: OAuth**. Remove it with `codex mcp remove leadbay`.

---

## ChatGPT

Add Leadbay as a connector in ChatGPT.

1. Open **Settings → Connectors** (you may need to enable **Developer mode** under **Settings → Connectors → Advanced** to add a custom MCP server).
2. Choose **Create / Add custom connector** and enter:
   - **Name:** `Leadbay`
   - **MCP Server URL:** `https://mcp.leadbay.app/mcp`
   - **Authentication:** OAuth
3. Click **Create / Connect** — a **Sign in with Leadbay** page opens. Log in and approve.
4. In a chat, enable the **Leadbay** connector (composer **+** / tools menu) so ChatGPT can call its tools.

{% hint style="info" %}
Custom MCP connectors in ChatGPT require a paid plan (Plus, Pro, Business, or Enterprise) and may be gated behind Developer mode or an admin setting for your workspace.
{% endhint %}

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
| Connected, but "show me leads" returns an empty list | You're signed in fine — there's just nothing to show right now. Ask _"show me my lenses"_ to check which audience is active, or confirm you're on the right instance (US vs EU). |
| Wrong instance (no leads / 404s) | Sign out and sign back in on the correct instance, or use the `/fr/mcp` URL for EU accounts. |
| Tools don't appear after connecting | Open a new chat and wait a few seconds; send a second message and the tools finish loading. |
| Tools appear but the assistant won't call them | Open the connector settings and set the Leadbay tool groups to **Always allow** (Claude) or enable the connector in the composer (ChatGPT). |
| Custom connector option missing (Claude.ai / Claude Desktop / ChatGPT) | Custom connectors need a paid plan, and your workspace admin may need to enable them. |
| Other issue | File a bug at [github.com/leadbay/mcp/issues](https://github.com/leadbay/mcp/issues). |

---

## Where to next

{% content-ref url="what-is-leadbay-mcp.md" %}
[What is Leadbay MCP?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Tools reference](tools-reference.md)
{% endcontent-ref %}
