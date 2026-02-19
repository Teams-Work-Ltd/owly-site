<p align="center">
  <img src="{{ site.baseurl }}/assets/owlyLogo.png" alt="Owly Data Exporter logo" width="120" />
</p>

<h1 align="center">Data Security & Privacy</h1>

<p align="center">
  Owly Data Exporter for Atlassian Data Center – Your data, your control.
</p>

---

**Navigation**

- [← All Products](index.html)
- [Owly for Jira](jira.html)
- [Owly for Confluence](confluence.html)
- [Data Security & Privacy](security.html)

---

## 1. Deployment model – Data stays in your instance

Owly Data Exporter is built for **Atlassian Data Center** (Jira and Confluence).

- ✔ **Local data storage** – All configuration, logs, and analytics data are
  stored in your Atlassian instance database.
- ✔ **No external mirroring** – We do not copy, mirror, or replicate your data
  to external services by default.
- ✔ **Always readable** – Export data and configuration remain readable in your
  database even if your license expires.

Your Atlassian instance (and its infrastructure) remains the **only source of truth**
for your data.

---

## 2. Data storage & access

- ✔ **Local Data Storage** – Owly stores its own configuration and metadata in
  standard application / AO tables within your database.
- ✔ **No external transmission by default** – No content data (issues, pages, comments,
  attachments, or custom fields) is sent outside your infrastructure unless you
  explicitly configure such integrations (e.g., email notifications, webhooks).
- ✔ **Access control via Atlassian** – Access to Owly is governed by your existing
  permissions (System Administrators, global permissions, and any SSO / IdP rules
  you already enforce).

If your organization uses SSO, VPN, or other security layers, Owly respects
those configurations automatically because it runs inside your Atlassian instance.

---

## 3. Optional analytics – helping us improve (when enabled)

Owly may include **optional usage analytics** to help improve product quality
based on real usage patterns.

- ✔ **Fully configurable** – Analytics can be enabled or disabled at any time
  from the Owly admin settings page.
- ✔ **Performance-optimized** – Events are collected and sent in batched,
  lightweight payloads to minimize overhead.
- ✔ **Transparent** – Analytics focuses on feature usage (e.g., which Owly
  views or endpoints are used) and **never** on instance content.

Example characteristics (implementation may vary by version):

- Logged events are stored first in your database in a dedicated
  ActiveObjects table (for example `AO_OWLY_EVENT_AO` or similar).
- When remote analytics is enabled, batched events are transmitted over HTTPS
  with an encoded payload and integrity hash.

**Example (simplified) encoded payload**

```json
{
  "dataEncoded": "eyJkYXRhUm93cyI6W3siSUQiOjEsIkFwcEtleSI6Ii4uLiJ9XX0=",
  "nonce": "7407367046465089664",
  "contentHash": "AEDE7F7A33D5B0A582AB85A8F133D13E379E0000",
  "otp": "318983"
}
```

**Example (simplified) decoded data**

```json
{
  "ID": "1223",
  "ProductTenant": "BWSN-B5B6-32P4-DDL7",
  "Name": "owly.export.tables.propertyentry",
  "ProductVersion": "9.12.15",
  "UpdateDate": "2025-02-13T08:06:44Z",
  "AppVersion": "0.9.9-b301041"
}
```

### Analytics – What is **not** collected

- ✔ No user-generated content (issue summaries, descriptions, pages, comments)
- ✔ No personally identifiable information (PII)
- ✔ No compliance / audit / business-sensitive payloads

Only high-level feature usage and technical metadata are processed.

---

## 4. Configurable privacy controls

Admins can tailor Owly to match organizational policies:

- Enable/disable analytics
- Configure notification channels (e.g. email) or disable them entirely
- Restrict who can access Owly UI and APIs via Atlassian permissions

We recommend that System Administrators review these settings during
on-boarding and periodically as part of security reviews.

---

## 5. Security practices

Owly follows security practices aligned with Atlassian Marketplace expectations:

- ✔ **Atlassian app checks** – App builds are subject to Marketplace review to
  ensure they meet baseline quality and security requirements.
- ✔ **Dependency scanning** – We use tools such as Dependabot / Snyk to track
  vulnerabilities in third-party libraries and keep them updated.
- ✔ **Transparent dependencies** – We maintain a Software Bill of Materials
  (SBOM) within the plugin's `META-INF` resources so administrators can inspect
  which components are used.

---

## 6. Privacy policy & compliance posture

Our handling of user data is designed to align with common privacy regulations
(e.g. GDPR-style principles):

- Data minimization
- Purpose limitation
- Transparency about processing
- Respect for customer retention and deletion policies

Your organization remains in control of:

- how long data is kept,
- who can access your Atlassian instance and Owly,
- which optional integrations or analytics are enabled.

---

## 7. Questions, incidents, or more information

If you have:

- security questions,
- compliance questionnaires,
- incident reports, or
- requests for additional documentation,

please reach out via our support portal:

> 👉 [https://teams-work.atlassian.net/servicedesk/customer/portal/1](https://teams-work.atlassian.net/servicedesk/customer/portal/1)

We are happy to provide additional details, security questionnaires, or
version-specific documentation on request.
