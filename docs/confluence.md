<p align="center">
  <img src="{{ site.baseurl }}/assets/owlyLogo.png" alt="Owly Confluence Data Exporter logo" width="150" />
</p>

<h1 align="center">Owly Confluence Data Exporter</h1>

<p align="center">
  Explore Confluence Data Center database tables via a simple, read-only REST API.
</p>

---

**Navigation**

- [← All Products](index.html)
- [Owly for Jira](jira.html)
- [Data Security & Privacy](security.html)

---

## Where to find Owly in Confluence

Owly is configured from the Confluence administration section:

- **Confluence admin URL:**  
  `/plugins/servlet/owly-exporter/settings`
- **Required permissions:** Confluence **System Administrator**

From this page you can:

- enable or disable Owly,
- configure access / authentication,
- manage licensing (Atlassian or Teams, Work custom license),
- configure optional analytics (if available in your build).

---

## What Owly does

Owly exposes a **read-only REST API** over selected Confluence database tables
(including application tables and ActiveObjects tables) so that admins and
integrators can:

- discover what tables are available,
- page through rows,
- fetch records by ID,
- perform safe batch reads for integrations, backups, or migrations.

> ✅ Owly **does not write** to Confluence via this REST API.  
> All operations are read-only.

---

## Quick REST entry points

> Replace `https://your-confluence.example.com` with your Confluence base URL.

### 1. List available tables

**GET**

```http
GET https://your-confluence.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables
```

Returns all visible tables Owly can see.  
Use this to discover AO / application tables before drilling into data.

---

### 2. Page through a table

Example for the `propertyentry` table:

**GET**

```http
GET https://your-confluence.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables/propertyentry?offset=0&limit=100
```

Parameters:

- `offset` – starting row index (0-based)
- `limit` – page size (e.g. 100, 500, 1000)

---

### 3. Lookup by ID

**GET**

```http
GET https://your-confluence.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables/propertyentry/1
```

Fetch a single row by numeric ID.

---

### 4. Batch lookup by IDs

Fetch multiple entities by ID in a single request.

**POST**

```http
POST https://your-confluence.example.com/rest/restrepo/1.a7c3/d4e1/repo/tables/propertyentry/batch
Content-Type: application/json

{
  "ids": [1, 2, 3]
}
```

Use this from curl, Postman, or scripts to iterate over batches instead of
calling one ID at a time.

---

## Licensing & Teams, Work

Owly supports multiple licensing paths:

- Atlassian Marketplace license (standard DC licensing)
- **Teams, Work license (custom licensing)** – for:
    - extended or overlapping support windows,
    - custom contracts and SLAs,
    - bundled services (consulting, migrations, integrations).

When a valid **Teams, Work** license is present, it can take precedence over
the Atlassian license, depending on your configuration.

For commercial questions or custom licensing options, please contact us via:

> 👉 Support portal:  
> [https://teams-work.atlassian.net/servicedesk/customer/portal/1](https://teams-work.atlassian.net/servicedesk/customer/portal/1)

---

## Confluence Data Center lifecycle & long-term support

Atlassian has announced end-of-life dates for Confluence Data Center versions.

Owly, together with **Teams, Work**, aims to:

- keep your Confluence data **accessible and explorable** even after Atlassian
  support ends for specific DC versions,
- provide **extended support contracts** via Teams, Work licensing,
- support **additional Confluence versions on request** (older, LTS, or future).

If you need support for:

- older DC versions, or
- future unreleased versions / long-term plans

please contact us via the support portal above and we will confirm support
timelines or offer custom builds.
