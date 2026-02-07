# Data Sources

Leadbay works best when it knows about your past leads. Import your CRM data via CSV files or connect tools via Zapier.

---

## Import a CSV File

{% hint style="info" %}
Imports are only available to admin users.
{% endhint %}

### During Onboarding

The first time you set up Leadbay, you'll be asked to upload a CSV with your past leads. See [Onboarding](onboarding.md) for the step-by-step.

### Adding More Data Later

From the side menu, navigate to **Data Sources** and click **Add new data source**. The process is the same as during onboarding:

1. **Upload your CSV** — any file with company data (name, location, status, etc.)
2. **Map fields** — Leadbay auto-detects columns. Verify or correct the mapping.
3. **Map statuses** — Tell Leadbay which of your status values mean won, lost, wanted, etc.

**Tips:**

- The **Status** field is the most important: it tells the AI which leads performed well
- More data = better recommendations, but even a small file helps
- You can import multiple files over time

### Importing Only Contacts

If you want to add personal contact data (phones, emails) for existing leads without changing their status: during import, skip the status column mapping and leave the default status empty. Your contact data will be added to Lead Profiles without affecting statuses.

### Custom Fields (Beta)

You can define custom fields for additional data specific to your business (e.g., product line, contract type). Navigate to Data Sources and click **Add new custom field**, then map it during your next import.

---

## Zapier Connection

Zapier automates data flow between Leadbay and thousands of other apps — including your CRM.

### Enable the Connection

1. Open the Leadbay-Zapier invitation: [Leadbay Zapier Invitation](https://zapier.com/developer/public-invite/186700/31de3445b74ad2736aa150f9f07f4bd3/)
2. Click **Accept Invite and Build a Zap**

### Import Data to Leadbay (CRM → Leadbay)

1. Go to [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger**: select your CRM (e.g., HubSpot, Salesforce) and pick an event (new company, status change)
3. **Action**: search for **Leadbay**, sign in when prompted
4. Map your CRM fields to Leadbay fields (name, location, status, etc.)
5. Click **Publish**

### Export Data from Leadbay (Leadbay → CRM)

1. Go to [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger**: search for **Leadbay**, pick the export event
3. **Action**: select your CRM and choose "Create Company" (or equivalent)
4. Map Leadbay fields to your CRM columns
5. Click **Publish**

{% hint style="info" %}
You only need to authorize the Leadbay-Zapier connection once. After that, all your Zaps can use it.
{% endhint %}
