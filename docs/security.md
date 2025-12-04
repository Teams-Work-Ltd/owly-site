### Data Security and Privacy Statement
### Your Data, Your Control

### Cat the Compliant is built for Jira Data Center, ensuring all compliance and audit data remains within your instance - never stored, mirrored, or transmitted externally. You maintain full control, even if your license expires.

### Data Storage & Access

✔ Local Data Storage – Compliance records, audit logs, and configurations stay within your Jira database.

✔ No External Transmission – No customer data leaves your infrastructure unless explicitly enabled for specific integrations (e.g., email notifications).

✔ Always Accessible – Audit data remains readable and available, even if your subscription lapses.

### Optional Analytics – Helping Us Improve

Owly includes optional usage analytics to help us refine the product based on real user interactions.

✔ Fully Configurable – Enable or disable analytics anytime in the app settings.

✔ Performance-Optimized – Data is collected in high-efficiency batches, ensuring no performance impact.

✔ Transparency – Analytics data logs product usage patterns (e.g., accessed pages) but never captures user-generated content (UGC) or personally identifiable information (PII).

✔ Stored in Your Database – View logged events in your Jira database table: AO_E701B1_CAT_EVENT_AO.

✔ Secure Transmission – When enabled, analytics data is securely transmitted over HTTPS using encoded payloads to ensure data integrity.

### How Analytics Data is Sent

When analytics is enabled, data is securely encoded and transmitted over HTTPS in batches. The transmission includes an encoded payload and a cryptographic hash for validation.

Example Raw Encoded Transmission:

{
"dataEncoded": "eyJkYXRhUm93cyI6W3siSUQiOjEsIkFwcEtleSI......nROYW1lMiJ9XX0=",
"nonce": "7407367046465089664",
"contentHash": "AEDE7F7A33D5B0A582AB85A8F133D13E379E0000",
"otp": "318983"
}
Example Decoded Data on Our End:

{ "ID": { "N": "1223" }, "ProductTenant": { "S": "BWSN-B5B6-32P4-DDL7" }, "Name": { "S": "cat.project.compliance.audit.all.projects" }, "ProductVersion": { "S": "9.12.15" }, "UpdateDate": { "S": "2025-02-13T08:06:44Z" }, "AppVersion": { "S": "0.9.9-b301041" } }
Analytics - What’s NOT Collected? #

✔ No user-generated content (UGC)

✔ No personally identifiable information (PII)

✔ No compliance or audit data

### Configurable Privacy Settings

Analytics and email notifications are fully configurable via App Settings, allowing you to tailor the experience to your organization’s policies.

### Access Control

Access to Owly inside Jira is governed by your existing Jira permissions. Only users with the appropriate roles can view or modify compliance data. If your organization implements SSO or other security layers, Owly respects those configurations.

For more details see Access, Roles & Permissions.

### Regular Security Audits

✔ Atlassian App Reviews: Owly undergoes regular checks by Atlassian to ensure it meets Marketplace standards.

✔ Dependabot & Snyk Scanning: We rely on these tools to keep our codebase free of critical, high, or medium vulnerabilities.

✔ Transparent Dependencies: We provide a Software Bill of Materials (SBOM) within the plugin’s META-INF folder, so you can easily validate which components we use.

### Privacy Policy Compliance

Our handling of user data aligns with prevailing privacy regulations. We’re committed to maintaining clear, transparent practices that respect your organization’s policies and obligations.

### Conclusion

Your trust is essential to us. With Owly, your data remains under your control - from initial installation to long after your license expires. By leveraging secure architecture and robust security measures, we aim to provide a reliable and compliant solution that fits right into your Jira instance.

Should you have any questions or need more information, please reach out to our support team via support portal. We’re happy to help.