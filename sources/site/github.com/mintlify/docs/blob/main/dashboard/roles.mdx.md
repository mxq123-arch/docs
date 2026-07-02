# Source: https://github.com/mintlify/docs/blob/main/dashboard/roles.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# roles.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/dashboard/roles.mdx)

History

48 lines (41 loc) · 2.43 KB

## FilesExpand file tree

 main

/

# roles.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

48 lines (41 loc) · 2.43 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/dashboard/roles.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>Roles</td></tr><tr><th>description</th><td>Assign admin, editor, or viewer roles to team members to control access levels, editing permissions, and deployment capabilities in Mintlify.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">RBAC</div></th><th><div dir="auto">role-based access control</div></th><th><div dir="auto">admin</div></th><th><div dir="auto">editor</div></th><th><div dir="auto">viewer</div></th><th><div dir="auto">permissions</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Role-based access control (RBAC) is available on \[Enterprise plans\]([https://mintlify.com/pricing?ref=rbac](https://mintlify.com/pricing?ref=rbac)).

Mintlify provides three dashboard access levels: viewer, editor, and admin.

| | Viewer | Editor | Admin |
| --- | :-: | :-: | :-: |
| View content in the editor | ✅ | ✅ | ✅ |
| View dashboard and analytics | ✅ | ✅ | ✅ |
| Ask the [Slack agent](https://github.com/mintlify/docs/blob/main/agent/slack) questions | ✅ | ✅ | ✅ |
| Make changes with the Slack agent | ❌ | ✅ | ✅ |
| Edit content in the web editor | ❌ | ✅ | ✅ |
| Publish changes | ❌ | ✅ | ✅ |
| Create, rename, and delete pages | ❌ | ✅ | ✅ |
| Reorder navigation | ❌ | ✅ | ✅ |
| Upload media | ❌ | ✅ | ✅ |
| Trigger deployments | ❌ | ✅ | ✅ |
| Create and delete API keys | ❌ | ✅ | ✅ |
| Configure integrations | ❌ | ✅ | ✅ |
| Configure assistant | ❌ | ✅ | ✅ |
| Configure add-ons | ❌ | ✅ | ✅ |
| Invite editors and viewers | ❌ | ✅ | ✅ |
| Update user roles | ❌ | ❌ | ✅ |
| Invite admins | ❌ | ❌ | ✅ |
| Delete users | ❌ | ❌ | ✅ |
| Manage billing | ❌ | ❌ | ✅ |
| Manage SSO | ❌ | ❌ | ✅ |
| Update custom domain | ❌ | ❌ | ✅ |
| Update Git source | ❌ | ❌ | ✅ |
| Delete organization | ❌ | ❌ | ✅ |

Limit admin access to only the people who need to perform admin tasks.

## Add members to your organization

By default, the person who creates your Mintlify organization has admin access. Add additional members in the [Members](https://app.mintlify.com/settings/organization/members) page of your dashboard.

You can invite any number of members to your organization.