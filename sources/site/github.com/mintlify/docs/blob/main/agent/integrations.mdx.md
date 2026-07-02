# Source: https://github.com/mintlify/docs/blob/main/agent/integrations.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# integrations.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)

[mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

and

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Documentation quality check: address gaps in recently updated pages (](https://github.com/mintlify/docs/commit/cf671d7abf4960d4a748b3df8fcbca14fed675fa) [#…](https://github.com/mintlify/docs/pull/6339)

Open commit detailssuccess

Jul 1, 2026

[cf671d7](https://github.com/mintlify/docs/commit/cf671d7abf4960d4a748b3df8fcbca14fed675fa) · Jul 1, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/agent/integrations.mdx)

Open commit details

History

113 lines (78 loc) · 6.82 KB

## FilesExpand file tree

 main

/

# integrations.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

113 lines (78 loc) · 6.82 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/agent/integrations.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Agent integrations</td></tr><tr><th>description</th><td>Connect Slack, Notion, Linear, Jira, Confluence, and other apps so the agent can pull live context when answering questions and updating content.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">integrations</div></th><th><div dir="auto">Slack</div></th><th><div dir="auto">Notion</div></th><th><div dir="auto">Linear</div></th><th><div dir="auto">Jira</div></th><th><div dir="auto">Confluence</div></th><th><div dir="auto">Salesforce</div></th><th><div dir="auto">Intercom</div></th><th><div dir="auto">Google Calendar</div></th><th><div dir="auto">Google Drive</div></th><th><div dir="auto">HubSpot</div></th><th><div dir="auto">Plain</div></th><th><div dir="auto">context</div></th><th><div dir="auto">Nango</div></th></tr></tbody></table></td></tr></tbody></table>

Agent integrations give the agent access to context from other tools that your team uses. Once connected, the agent can search Slack threads, read Notion pages, look up Linear issues, and pull context from other apps to inform its responses and content updates.

## Connection scope

Integrations connect in one of two ways:

- **Shared integrations** connect once for your entire organization. Anyone on the team can prompt the agent to use them. Slack, Notion, Linear, Jira, Confluence, Salesforce, Intercom, HubSpot, and Plain all connect this way.
- **Personal integrations** connect per user. Each teammate authorizes their own account, and the agent can only use a personal integration on behalf of the user who connected it. Google Calendar and Google Drive are personal.

Personal integrations keep user-specific data, like calendar events, scoped to the user who connected the integration instead of shared across the organization.

## Connect an integration

Admins and editors can connect shared integrations on behalf of the organization.

1. Go to the [Agent integrations](https://app.mintlify.com/settings/organization/integrations) page in your dashboard.
2. Find the integration you want to connect.
3. Click **Connect**.
4. Follow the OAuth prompts to authorize Mintlify to access your account.

Some integrations open an additional configuration step before the connection completes. Jira, Confluence, and Salesforce ask for your workspace URL or subdomain before the OAuth flow begins, and API-key providers like Plain prompt you to paste an API key.

## Supported integrations

| Integration | Scope |
| --- | --- |
| Confluence | Shared |
| Google Calendar | Personal |
| Google Drive | Personal |
| HubSpot | Shared |
| Intercom | Shared |
| Jira | Shared |
| Linear | Shared |
| Notion | Shared |
| Plain | Shared |
| Salesforce | Shared |
| Slack | Shared |

## How the agent uses integrations

The agent uses connected integrations as tools. When you ask the agent a question or give it a task, it can search and retrieve content from your connected apps to build context.

For example:

- "Summarize the Slack thread about the v2 API migration and write it up for the knowledge base."
- "Check the Linear ticket for this feature and document the behavior."
- "What did the team decide about rate limiting? Check Slack."

The agent only accesses integration data when it's relevant to the request. It does not proactively read from connected apps.

## Permissions and access

Each integration requests the OAuth scopes or API-key permissions it needs to search and retrieve content from the connected app. Mintlify requests read-only scopes wherever the provider offers them.

Review the exact scopes during the OAuth consent screen before authorizing the connection. The consent screen lists every permission the agent receives, and you can revoke the connection at any time from the dashboard or from the connected app's own integrations settings.

If your organization restricts which apps users can authorize, ask the relevant admin (such as your Slack or Google Workspace admin) to allow the Mintlify integration before connecting.

### What the agent can read from each app

The agent inherits the access of the account that authorized the connection. It can only read content that the authorizing user (for personal integrations) or the connected workspace account (for shared integrations) already has access to in the source app.

| Integration | Content the agent can access |
| --- | --- |
| Confluence | Pages and attachments in spaces the connected account can read |
| Google Calendar | Events on calendars the connected user can view |
| Google Drive | Files and folders the connected user can view, including shared drives |
| HubSpot | CRM records (contacts, companies, deals, tickets) the connected account can read |
| Intercom | Conversations, contacts, and help center articles the connected account can read |
| Jira | Issues and comments in projects the connected account can read |
| Linear | Issues, projects, and comments in teams the connected account can read |
| Notion | Pages and databases explicitly shared with the Mintlify integration |
| Plain | Threads and customer records accessible with the provided API key |
| Salesforce | Standard and custom objects the connected account can read |
| Slack | Public channels the workspace grants access to, plus private channels you add the Mintlify app to |

To narrow what the agent can see, restrict the connected account's permissions in the source app. For example, invite the Mintlify Slack app only to specific channels, or share only selected Notion pages with the integration.

## Data retention after disconnect

When you disconnect an integration, the agent immediately loses the ability to read from that app. Mintlify doesn't retain a durable copy of integration content. The agent fetches data on each request through the live OAuth token or API key, so disconnecting cuts off future access.

Content that appeared in past agent responses or pull requests stays in place (chat transcripts, published pages, PR history). If you also want that content removed, edit or delete the pages and conversations directly.

## Troubleshoot a failed connection

If an integration stops working or shows an error in the dashboard, the underlying OAuth token has usually expired, been revoked in the connected app, or had its required scopes changed.

To restore access:

1. Go to the [Agent integrations](https://app.mintlify.com/settings/organization/integrations) page in your dashboard.
2. Find the affected integration and click **Configure**.
3. Click **Disconnect**.
4. Click **Connect**.
5. Complete the OAuth flow.

For API-key providers like Plain, generate a new API key in the source app and paste it into the integration's configuration. If the agent still can't access data after reconnecting, confirm that the authorizing user has permission to view the relevant content in the source app.

## Disconnect an integration

1. Go to the [Agent integrations](https://app.mintlify.com/settings/organization/integrations) page in your dashboard.
2. Find the connected integration you want to disconnect.
3. Click **Configure**.
4. Click **Disconnect**.

Disconnecting a shared integration removes it for everyone in your organization, and the agent immediately loses access to that tool.

Disconnecting a personal integration only removes your own connection. Other teammates who have connected the same integration keep their access, and the agent can still use the integration on their behalf.