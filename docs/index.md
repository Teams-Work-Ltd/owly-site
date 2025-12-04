<p align="center">
  <img src="assets/pluginLogo.png" alt="Owly Jira Data Exporter logo" width="150" />
</p>

# Owly Jira Data Exporter

Explore Jira Data Center database tables via a simple REST API.

You are viewing the public product documentation for **Owly Jira Data Exporter**.

---

## Where to find Owly in Jira

Owly is configured from the Jira administration section:

- **Jira Admin URL:**  
  `/secure/admin/OwlyExporterSettings.jspa`

Required permissions: **Jira System Administrator**.

---

## What Owly does

Owly exposes a **read-only REST API** over selected Jira database tables
(including application tables and ActiveObjects tables) so that admins and
integrators can:

- discover what tables are available,
- page through rows,
- fetch records by ID,
- perform safe batch reads for integrations, backups, or migrations.

Owly **does not** modify Jira data through this REST API.

---

## Quick REST entry points

> Replace `https://your-jira.example.com` with your Jira base URL.

### 1. List available tables

**GET**

```http
GET https://your-jira.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables
```

Returns all visible tables Owly can see.
Use this to discover AO / application tables before drilling into data.

### 2. Page through a table

Example for the propertyentry table:

**GET**

```http
GET https://your-jira.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables/propertyentry?offset=0&limit=100
```

### Licensing & Teams, Work

Owly supports two licensing paths:
- Atlassian Marketplace license
- Standard Data Center licensing.
- Teams, Work license (custom licensing)
Designed for customers who want flexible commercial terms (e.g. longer support window, custom contracts, or bundled services).


### Important notes on Jira Data Center lifecycle & long-term support

Atlassian has announced end-of-life dates for Jira Data Center versions.
Owly, together with Teams, Work, aims to:
- keep your Jira data accessible and explorable even after Atlassian support
for specific DC versions ends,
- provide extended support contracts via Teams, Work licensing,
- support additional Jira versions on request.

If you need support for:
- older DC versions, or
- future unreleased versions / long-term plans
→ contact us and we will confirm support timelines or offer custom builds.
https://teams-work.atlassian.net/servicedesk/customer/portal/1
