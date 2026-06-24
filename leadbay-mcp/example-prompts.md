# Example prompts

Leadbay MCP works best when you talk to Claude the way you'd talk to a colleague — describe the outcome, not the tool. Below is a library of prompts that work out of the box, grouped by what you're trying to do. Copy, tweak, and make them yours.

{% hint style="info" %}
You don't need to name tools or IDs. "Pull today's leads", "research acme.com", "log that I emailed Jane" — Claude picks the right tool. Every action is scoped to your account; how much your client asks before each one depends on its tool-permission settings.
{% endhint %}

{% hint style="success" %}
**Better in Claude chat.** The rich outputs below — ranked lead tables, interactive trip maps, and ready-to-send draft cards — render natively there. Other MCP clients work too, but fall back to plain text where they don't support these views.
{% endhint %}

---

## Start your day

> *Show me today's leads.*

> *What's in my inbox this morning?*

> *Pull my best new prospects and tell me which two are worth opening first.*

> *Give me an overview of my prospecting — where am I, what should I do next?*

Claude pulls your fresh batch, ranks it, and offers a short shortlist. It won't take any action until you ask:

<figure><img src="../.gitbook/assets/mcp-pull-leads-shortlist.png" alt="A ranked table of prospects — fit, why-it-qualifies, and contact — followed by Claude's pick of the two worth opening first"><figcaption><p>"Pull my best new prospects and tell me which two are worth opening first." Claude returns a ranked table — fit, why each qualifies, and the best contact — then calls the top two with a reason for each.</figcaption></figure>

---

## Follow up & re-engage

> *Which leads should I follow up with this week?*

<figure><img src="../.gitbook/assets/mcp-pull-followups.png" alt="Claude's follow-up plan — leads grouped into do-first, do-next, and lower-priority, with the concrete action for each"><figcaption><p>"Which leads should I follow up with this week?" Claude reads your Monitor view and orders it into <strong>do first</strong> (act today), <strong>do next</strong> (enrich a contact first), and <strong>lower priority</strong> — then ends with the exact moves: who to call, who to email, who to enrich.</figcaption></figure>

> *Who have I contacted that I should circle back to?*

> *What's the full history on this account — is it worth another visit?*

> *Which of my leads acquired a company since 2025?*

> *Scan my portfolio for funding signals.*

The portfolio-scan prompts filter your existing leads by a web signal in one pass — no need to research each one individually.

---

## Research a company

> *Tell me about jaxpartycompany.com — is it a fit for us?*

> *Research Acme Corp and summarise why they score the way they do.*

> *Pull the contacts and qualification for this lead.*

Claude returns a research card with the company's score, why it fits, and the best contact to reach.

---

## Plan a trip / field sales

> *I'm going to NYC in 2 days — plan a prospecting tour.*

> *I'm visiting Jacksonville in 3 days — plan my visits.*

> *I'm flying to Berlin Thursday — who should I meet while I'm there?*

> *Show my follow-ups around Lyon on a map.*

> *Give me 3 existing customers, 3 qualified leads, and 3 new prospects near Limoges, on one map.*

These render on a map where your client supports it, with the best contact and a one-line reason per stop. Here's the NYC tour above, planned and mapped in a single reply:

<figure><img src="../.gitbook/assets/mcp-tour-plan-nyc.png" alt="Claude planning a two-day NYC prospecting tour — an interactive map with a Day 1/Day 2 route and a stop-by-stop itinerary card"><figcaption><p>"I'm going to NYC in 2 days — plan a prospecting tour." Claude picks the best-scoring accounts, lays out a two-day Brooklyn-to-Harlem route on an interactive map, and groups it into a <strong>NYC Tour</strong> campaign — qualified accounts plus high-scoring new discoveries, each with timing and contact.</figcaption></figure>

---

## Draft & log outreach

> *Draft me an outreach email for Brooklyn Brewery.*

> *Draft me an outreach email for JAX PARTY COMPANY LLC.*

> *Write a cold-call opener for Acme — I'm selling field-service software.*

> *I just emailed Jane at Acme. Log it as outreach.*

> *I called Acme this morning and left a voicemail — record that.*

Drafting is read-only. Logging writes the activity to your account. A draft comes back as a few ready-to-send variants, each taking a different angle:

<figure><img src="../.gitbook/assets/mcp-outreach-draft-brooklyn.png" alt="Claude drafting an outreach email to Brooklyn Brewery with three strategy variants — warm intro, sustainability + ops angle, and direct ask"><figcaption><p>"Draft me an outreach email for Brooklyn Brewery." Claude returns three strategy variants — a warm intro, a sustainability + ops angle, and a direct ask — each personalized with subject and body, ready to open in your mail client.</figcaption></figure>

---

## Import & qualify a list

> *I have 400 event attendees — import them and rank the most promising.*

> *Here's a CSV of domains. Import and qualify the top 50.*

> *Qualify the top 10 leads in my batch.*

> *What's the status of my import?*

Claude maps your file's columns, imports the rows, and can immediately run AI qualification on the most promising ones.

---

## Manage your audience (lenses)

> *Show me my lenses and switch to the Joinery one.*

> *Create a lens called Joinery for the fintech sector.*

> *Stop showing me companies with more than 50 employees.*

> *I prefer EU companies that are actively hiring sales reps — refine my audience.*

> *I want more leads on this lens — give me a bigger batch today.*

Lens changes are reversible and reflected immediately in your next pull.

---

## Build a team campaign

> *Set up a prospecting campaign for my team.*

> *Create a campaign for the leads I just qualified and add the top 20.*

> *Show me how the Q3 campaign is progressing.*

> *Give me the call sheet for the Lyon campaign.*

Campaigns persist a hand-picked cohort of leads your team can work through together.

---

## Manage contacts

> *Acme has no contacts — add Jane Doe, VP Eng, here's her LinkedIn.*

> *Pin Jane Doe as the main contact on this company.*

> *Update Jane Doe's title to SVP Engineering.*

> *Remove Jane Doe — I added her by mistake.*

---

## Housekeeping & feedback

> *How much enrichment quota do I have left?*

> *Top up my quota.*

> *Send feedback to the team: lead scores feel off this week.*

---

## Chaining it together

You can ask for a whole sequence in one message, or build it up turn by turn:

> *Pull today's leads, research the top one, and draft me an email to them.*

> *Show me my follow-ups near Madrid, put them on a map, and prep outreach for the closest three.*

Claude carries context across the conversation — once it's surfaced a lead, you can keep referring to "the top one" or "that company" without repeating yourself. Here's that first prompt running end to end:

<figure><img src="../.gitbook/assets/mcp-chain-1.png" alt="Today's leads as a ranked table with score bars, linked companies, why-it-fits, and linked contacts"><figcaption><p><strong>1. Pull today's leads.</strong> A ranked table with score bars, why each fits, and the best contact — Claude picks YouFit LLC as the top scorer to research next.</figcaption></figure>

<figure><img src="../.gitbook/assets/mcp-chain-2.png" alt="A deep research card on YouFit LLC — business signals, prospecting clues, and strategic positioning"><figcaption><p><strong>2. Research the top one.</strong> A deep-dive card on YouFit: business signals, prospecting clues, and strategic positioning, each sourced.</figcaption></figure>

<figure><img src="../.gitbook/assets/mcp-chain-3.png" alt="YouFit's contacts — name and title, with one marked recommended and 152 more in the system"><figcaption><p><strong>…with the right person surfaced.</strong> Contacts ranked by relevance — Kriston Tomlinson (Director of Operations) flagged as the recommended reach.</figcaption></figure>

<figure><img src="../.gitbook/assets/mcp-chain-4.png" alt="An email draft to Kriston Tomlinson with two strategy variants — expansion hook and facilities-focused"><figcaption><p><strong>3. Draft the email.</strong> A personalized draft to Kriston, in two angles (expansion hook / facilities-focused), tied to YouFit's Boynton Beach expansion — ready to open in your mail client.</figcaption></figure>

---

## Next step

New here? Start with the overview, then connect.

{% content-ref url="what-is-leadbay-mcp.md" %}
[What is Leadbay MCP?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}
