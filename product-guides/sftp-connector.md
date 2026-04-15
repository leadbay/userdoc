# SFTP Connector

Automatically import leads from a CSV file hosted on your SFTP server. Leadbay connects to the server, reads the file, and keeps your data in sync.

{% hint style="info" %}
The SFTP connector is only available to **admin** users. See [Team & Organization](team-management.md) for role details.
{% endhint %}

---

## When to Use SFTP

Use the SFTP connector when your CRM or internal system exports lead data as a CSV file to an SFTP server. Instead of downloading and re-uploading the file manually each time, Leadbay connects directly and syncs automatically.

---

## Set Up a Connection

1. From the side menu, navigate to **Data Sources**
2. Click **Add new integration**
3. Select **SFTP** from the list

<figure><img src="../.gitbook/assets/screenshot-sftp-connector.png" alt="SFTP connector form"><figcaption><p>The SFTP connection form</p></figcaption></figure>

Fill in the connection form:

| Field | Description |
|-------|-------------|
| **Host** | SFTP server address (e.g. `sftp.yourcompany.com`) |
| **Port** | Server port (default: `22`) |
| **Username** | Your SFTP login |
| **Password** | Your SFTP password |
| **File Path** | Full path to the CSV file on the server (e.g. `/exports/leads.csv`) |

### Test Before Connecting

Click **Test connection** to verify that Leadbay can reach the server and find the file. A green checkmark confirms the connection is working.

Once the test passes, click **Connect** to create the connector. Leadbay immediately queues a first sync.

---

## How Sync Works

- Leadbay checks the SFTP file periodically
- The file is only re-imported when its content changes (detected via checksum)
- Each sync parses the CSV and imports leads using your field and status mappings — the same mappings used for manual CSV imports

{% hint style="info" %}
Your CSV file must follow the same format as a regular Leadbay CSV import — at minimum a company name column. See [Data Sources](data-sources.md) for column requirements and mapping details.
{% endhint %}

---

## Editing or Removing a Connector

To update connection details, open the connector from your integrations list and modify the fields. To remove it, delete the connector from the same screen.
