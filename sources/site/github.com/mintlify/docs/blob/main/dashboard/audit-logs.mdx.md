# Source: https://github.com/mintlify/docs/blob/main/dashboard/audit-logs.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# audit-logs.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![paaatrrrick](https://avatars.githubusercontent.com/u/88113528?v=4&size=40)](https://github.com/paaatrrrick) [paaatrrrick](https://github.com/mintlify/docs/commits?author=paaatrrrick)

[Rename workflows to automations across docs (](https://github.com/mintlify/docs/commit/65f6e60f31a5ebe9505e608f1b6fc1e70f5aa75a) [#6227](https://github.com/mintlify/docs/pull/6227) [)](https://github.com/mintlify/docs/commit/65f6e60f31a5ebe9505e608f1b6fc1e70f5aa75a)

success

Jun 18, 2026

[65f6e60](https://github.com/mintlify/docs/commit/65f6e60f31a5ebe9505e608f1b6fc1e70f5aa75a) · Jun 18, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/dashboard/audit-logs.mdx)

Open commit details

History

65 lines (50 loc) · 3.43 KB

## FilesExpand file tree

 main

/

# audit-logs.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

65 lines (50 loc) · 3.43 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/dashboard/audit-logs.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Audit logs</td></tr><tr><th>description</th><td>Review audit logs to track actions performed by organization members, including deployments, configuration changes, and permission updates.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">monitoring</div></th><th><div dir="auto">activity tracking</div></th><th><div dir="auto">security</div></th><th><div dir="auto">compliance</div></th></tr></tbody></table></td></tr></tbody></table>

Audit logs are available on \[Enterprise plans\]([https://mintlify.com/pricing?ref=audit-logs](https://mintlify.com/pricing?ref=audit-logs)).

Use audit logs to monitor and track actions performed by members of your organization. Audit logs provide a record of activities for security, compliance, and troubleshooting purposes.

- **Monitor security**: Track authentication attempts and permission changes.
- **Ensure compliance**: Maintain records of all organizational activities.
- **Troubleshoot issues**: Investigate failed actions and their causes.
- **Track changes**: Review who made specific changes and when.

## View audit logs

Go to the [Audit log](https://app.mintlify.com/settings/organization/audit-logs) page of your dashboard to view audit logs.

Click any log entry to expand it and view detailed information, including:

| Field | Description |
| --- | --- |
| Timestamp | Date and time when the action occurred |
| Actor | The email address of the user who performed the action |
| Action | What action the user performed |
| Category | Type of resource affected |
| Outcome | Whether the action succeeded or failed |
| Metadata | Additional context about the action |

### Filter logs

Filter audit logs to find specific activities.

**Date range**: Select a preset date range to view logs over a specific period.

**Category**: Filter logs by the type of action.

| Category | Description |
| --- | --- |
| Organization | Organization settings updates and deletion requests. |
| Member | Team member invitations, removals, and role changes. |
| Deployment | Deployment configuration changes including custom domains, authentication, Git sources, and MCP client credentials. |
| Preview deployment | Preview deployment creation, updates, and authentication changes. |
| API key | API key and discovery API key creation and deletion. |
| Assistant | Assistant setting updates like deflection email, web search sites, and starter questions. |
| PDF export | PDF export generation and deletion. |
| Integration | GitHub and Slack installations and removals. |
| Billing | Subscription updates, add-on purchases, and invoice views. |
| Quota | Overage policy and alert configuration changes. |
| User | Individual user notification settings. |
| Automations | Automation configurations and repository management. |
| Audit log | Audit log views and exports. |
| Auth | Login attempts, logouts, and session creations. |

## Export audit logs

Export audit logs to CSV for analysis, compliance reporting, or long-term archival.

1. Navigate to the [Audit log](https://app.mintlify.com/settings/organization/audit-logs) page of your dashboard.
2. Optionally, apply filters to narrow down the logs you want to export.
3. Click **Export CSV**.
4. Mintlify sends you an email with a download link when the export is ready.