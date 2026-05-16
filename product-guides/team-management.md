# Team & Organization

Manage your organization settings and team members from the side menu.

---

## Organization Info

Open the side menu (hamburger icon, top-left) and go to **My Organization**.

<figure><img src="../.gitbook/assets/screenshot-team-organization.png" alt=""><figcaption><p>Organization settings</p></figcaption></figure>

Here you can:

- View and update your **organization name**

---

## Team Members

The Members section shows all members and a seats counter (e.g. *"100,000 seats available including 0 managers"*). Each row contains:

| Column | Description |
|--------|-------------|
| **Name** | Display name |
| **Email** | Login email |
| **Verified** | Whether the user confirmed their email |
| **Role** | Admin or Member |
| **Manager** | The user's manager (set when inviting or editing a member) |

### Adding Members

Click **+ Add new member** to invite someone by email. The dialog asks for:

1. **Email**
2. A **Role** — `Admin` or `Member` (with a one-line description of what each can do)
3. If you pick `Member`, an optional **Manager** dropdown to assign their manager from existing members

The invitee receives an email invitation to join your organization.

### Roles

| Role | Capabilities |
|------|-------------|
| **Admin** | Full access: manage team, organization settings, data sources, billing, lenses |
| **Member** | Use Leadbay: discover, like, enrich, export, activate. Cannot manage org settings or billing |
| **Manager** | A Member who is the manager of one or more other members. Gets visibility into their reports' activity in the [Manager Dashboard](manager-dashboard.md). Doesn't change app permissions — only changes who shows up under whom |

Use the action menu (three dots) on each row to change a member's role, set/change their manager, or remove them.

{% hint style="info" %}
Only admins can import data, manage billing, and change organization settings.
{% endhint %}
