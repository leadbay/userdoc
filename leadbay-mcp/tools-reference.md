# Tools reference

When you connect Leadbay to Claude, the server exposes a set of **tools** that Claude calls on your behalf. You never call these directly — you ask in plain language ("pull today's leads", "research acme.com", "log that I emailed Jane") and Claude picks the right tool. This page is a reference for what's available and what each tool does.

Tools come in two groups:

- **Read-only** — pull data, never change anything. Always available.
- **Write / activate** — take action on your account. On by default; an admin can disable them with `LEADBAY_MCP_WRITE=0`.

{% hint style="info" %}
This page covers the tools a normal user sees. There's also an **advanced** set of low-level, single-API-call tools for integrations and power users, hidden behind `LEADBAY_MCP_ADVANCED=1`. Most people never need them. The current source of truth for every tool is the [LeadClaw README](https://github.com/leadbay/leadclaw#tools).
{% endhint %}

---

## Read-only tools

These never modify your account, so they're always safe to allow.

### Discover & follow up

| Tool | What it does |
|------|--------------|
| `leadbay_pull_leads` | Retrieves today's fresh lead batch, scored and ranked |
| `leadbay_pull_followups` | Pulls the leads that need a follow-up action |
| `leadbay_account_status` | Checks your quota, credits, and account state |
| `leadbay_scan_portfolio_signals` | Scans your existing leads for a web signal in one pass ("which of my leads acquired a company since 2025?") — no quota burn |

### Research a company

| Tool | What it does |
|------|--------------|
| `leadbay_research_lead_by_id` | Deep-dive research card for a known lead — bundles details, qualification, and contacts into one response |
| `leadbay_research_lead_by_name_fuzzy` | Looks up a lead by company name or domain when you don't have its ID |
| `leadbay_account_history` | Full history on one account — current AI signals + all notes + the interaction timeline, in one call ("why has this account resurfaced?") |
| `leadbay_prepare_outreach` | Generates a personalized outreach brief for a lead |

### Travel & field sales

| Tool | What it does |
|------|--------------|
| `leadbay_followups_map` | Geo-clusters your follow-ups on a map for travel planning |
| `leadbay_tour_plan` | Builds a visit itinerary for an upcoming trip to a city |

### Campaigns

| Tool | What it does |
|------|--------------|
| `leadbay_list_campaigns` | Lists your existing campaigns |
| `leadbay_campaign_progression` | Shows a campaign's funnel metrics |
| `leadbay_campaign_call_sheet` | Pulls the call sheet for a campaign |

### Lenses & audience

| Tool | What it does |
|------|--------------|
| `leadbay_list_sectors` | Lists the real sector taxonomy labels — so you (and Claude) name sectors correctly |
| `leadbay_recall_ordered_titles` | Recalls the job titles you've previously enriched |
| `leadbay_seed_candidates` | Read-only discovery surface for building a bigger lens |

### Imports & jobs

| Tool | What it does |
|------|--------------|
| `leadbay_import_status` | Checks the status of an import job |
| `leadbay_qualify_status` | Checks the status of a qualification job |
| `leadbay_bulk_enrich_status` | Checks the status of an enrichment job |
| `leadbay_resolve_import_rows` | Maps imported rows back to their lead IDs |
| `leadbay_list_mappable_fields` | Lists the CRM fields you can map an import onto |

### Billing

| Tool | What it does |
|------|--------------|
| `leadbay_create_topup_link` | Generates a Stripe link to top up your quota (you pay in your browser — nothing is charged automatically) |
| `leadbay_open_billing_portal` | Opens your billing dashboard |

---

## Write / activate tools

These take action on your account. They're on by default. Every action is one you could take yourself in the app — there's nothing destructive at the platform level.

### Qualify & enrich

| Tool | What it does |
|------|--------------|
| `leadbay_bulk_qualify_leads` | Triggers AI qualification on a batch of leads |
| `leadbay_enrich_titles` | Enriches contacts by job title |

### Outreach & activity

| Tool | What it does |
|------|--------------|
| `leadbay_report_outreach` | Logs an outreach action (call, email, meeting) against a lead |
| `leadbay_add_note` | Adds a note to a lead |
| `leadbay_like_lead` | Marks a lead as liked — teaches your taste profile |
| `leadbay_dislike_lead` | Marks a lead as disliked — teaches your taste profile |

### Contacts

| Tool | What it does |
|------|--------------|
| `leadbay_add_contact` | Adds a person to a company (name + optional LinkedIn / title / email / phone) |
| `leadbay_remove_contact` | Removes a contact you added |
| `leadbay_pin_contact` | Pins a contact as the priority on a company |
| `leadbay_unpin_contact` | Unpins a contact |
| `leadbay_update_contact` | Edits a contact's details (title, email, LinkedIn…) |

### Lenses & audience

| Tool | What it does |
|------|--------------|
| `leadbay_my_lenses` | Lists, switches, renames, or deletes your lenses |
| `leadbay_new_lens` | Creates a named lens with sector / company-size criteria |
| `leadbay_adjust_audience` | Edits a lens's audience ("stop showing me companies over 50 employees") |
| `leadbay_extend_my_lens` | Fills your current lens with more leads on demand (subject to a daily refill quota) |
| `leadbay_refine_prompt` | Refines the qualification prompt that scores your leads |
| `leadbay_answer_clarification` | Answers a clarification question Leadbay asked about your audience |

### Imports & campaigns

| Tool | What it does |
|------|--------------|
| `leadbay_import_leads` | Imports a list of company domains |
| `leadbay_import_and_qualify` | Imports a list and immediately qualifies it |
| `leadbay_create_custom_field` | Creates a custom CRM field (e.g. to preserve a source-system ID) |
| `leadbay_create_campaign` | Creates a new campaign |
| `leadbay_add_leads_to_campaign` | Adds leads to a campaign |
| `leadbay_remove_leads_from_campaign` | Removes leads from a campaign |

### Feedback

| Tool | What it does |
|------|--------------|
| `leadbay_send_feedback` | Sends a message to the Leadbay team (same inbox as the in-app feedback form) |
| `leadbay_report_friction` | Reports when a tool didn't deliver what you needed — helps improve the product |

---

## How Claude chooses a tool

You don't pick tools — you describe the outcome. A few examples of the mapping:

| You say… | Claude calls… |
|----------|---------------|
| "Show me today's leads" | `leadbay_pull_leads` |
| "Which leads should I follow up with?" | `leadbay_pull_followups` |
| "Tell me about acme.com" | `leadbay_research_lead_by_name_fuzzy` |
| "I'm visiting Lyon next week — plan my visits" | `leadbay_tour_plan` |
| "I just called Jane at Acme — log it" | `leadbay_report_outreach` |
| "Create a lens called Joinery for fintech" | `leadbay_new_lens` |
| "Stop showing me companies over 50 people" | `leadbay_adjust_audience` |

See the [Example prompts](example-prompts.md) page for a fuller library you can copy and paste.

---

## Next step

{% content-ref url="example-prompts.md" %}
[Example prompts](example-prompts.md)
{% endcontent-ref %}
