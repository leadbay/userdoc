# Example prompts

Leadbay MCP works best when you talk to Claude the way you'd talk to a colleague — describe the outcome, not the tool. Below is a library of prompts that work out of the box, grouped by what you're trying to do. Copy, tweak, and make them yours.

{% hint style="info" %}
You don't need to name tools or IDs. "Pull today's leads", "research acme.com", "log that I emailed Jane" — Claude picks the right tool. Every action is scoped to your account; how much your client asks before each one depends on its tool-permission settings.
{% endhint %}

---

## Start your day

> *Show me today's leads.*

> *What's in my inbox this morning?*

> *Pull my best new prospects and tell me which two are worth opening first.*

> *Give me an overview of my prospecting — where am I, what should I do next?*

Claude pulls your fresh batch, ranks it, and offers a short shortlist. It won't take any action until you ask.

---

## Follow up & re-engage

> *Which leads should I follow up with this week?*

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

> *I'm visiting Jacksonville in 3 days — plan my visits.*

> *I'm flying to Berlin Thursday — who should I meet while I'm there?*

> *Show my follow-ups around Lyon on a map.*

> *Give me 3 existing customers, 3 qualified leads, and 3 new prospects near Limoges, on one map.*

These render on a map where your client supports it, with the best contact and a one-line reason per stop.

---

## Draft & log outreach

> *Draft me an outreach email for JAX PARTY COMPANY LLC.*

> *Write a cold-call opener for Acme — I'm selling field-service software.*

> *I just emailed Jane at Acme. Log it as outreach.*

> *I called Acme this morning and left a voicemail — record that.*

Drafting is read-only. Logging writes the activity to your account.

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

Claude carries context across the conversation — once it's surfaced a lead, you can keep referring to "the top one" or "that company" without repeating yourself.

---

## Next step

New here? Start with the overview, then connect.

{% content-ref url="what-is-leadbay-mcp.md" %}
[What is Leadbay MCP?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="quickstart.md" %}
[Quickstart](quickstart.md)
{% endcontent-ref %}
