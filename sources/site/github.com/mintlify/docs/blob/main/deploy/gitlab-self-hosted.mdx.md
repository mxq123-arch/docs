# Source: https://github.com/mintlify/docs/blob/main/deploy/gitlab-self-hosted.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# gitlab-self-hosted.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/gitlab-self-hosted.mdx)

History

108 lines (77 loc) · 7.31 KB

## FilesExpand file tree

 main

/

# gitlab-self-hosted.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

108 lines (77 loc) · 7.31 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/gitlab-self-hosted.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Self-hosted GitLab OAuth</td></tr><tr><th>description</th><td>Connect a self-hosted GitLab instance to Mintlify via OAuth so automations can clone repositories, push commits, and open merge requests on your behalf.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">GitLab</div></th><th><div dir="auto">self-hosted</div></th><th><div dir="auto">OAuth</div></th><th><div dir="auto">automations</div></th><th><div dir="auto">enterprise</div></th></tr></tbody></table></td></tr></tbody></table>

Mintlify supports OAuth-based authorization for self-hosted GitLab instances, in addition to gitlab.com. OAuth lets the Mintlify agent act as a GitLab user during automation runs: cloning repositories, pushing commits, opening merge requests, and registering project webhooks.

You must configure OAuth authorization for self-hosted GitLab instances to support [automations](https://github.com/mintlify/docs/blob/main/automations).

Unlike gitlab.com, where Mintlify ships a single OAuth application that every customer authorizes against, each self-hosted instance must register its own OAuth application. Create the application on your GitLab instance, share its credentials with Mintlify, and then go through an OAuth authorization to connect a user.

This guide is only for the \*\*OAuth\*\* integration that powers automations. You must configure the deployment-side connection (used for content sync and previews) separately with a deploy token, see the \[GitLab guide\](/deploy/gitlab). The OAuth integration depends on the deployment-side connection.

## Prerequisites

- Admin access to your self-hosted GitLab instance.
- Your GitLab instance must be reachable from `https://app.mintlify.com`. Instances behind a VPN or behind a firewall that blocks public ingress do not work.
- A Mintlify organization that has the self-hosted GitLab feature enabled. Contact support if you don't see the **Self-hosted GitLab** section in your [Git settings](https://app.mintlify.com/settings/deployment/git-settings) dashboard page.

## Set up the connection

In your self-hosted GitLab, sign in as an admin and navigate to \*\*Admin Area\*\* \\> \*\*Applications\*\* \\> \*\*Add new application\*\*.

```
Configure the application with these values:

- **Name**: `Mintlify`
- **Redirect URI**: `https://app.mintlify.com/api/gitlab-oauth/callback`
- **Trusted**: leave **unchecked**. Trusting the application skips the consent screen for every user; leaving it unchecked surfaces a normal authorization prompt the first time each user connects.
- **Confidential**: **checked**. Mintlify is a server-side client and keeps the secret confidential.
- **Scopes**: select `api`, `read_repository`, and `write_repository`. The agent uses these to read project metadata, clone repositories, and push commits.

Click **Save application**.

<Tip>
  Editing an OAuth application on GitLab can rotate the client secret silently. If you make changes later, click **Renew secret** and update the new value in Mintlify.
</Tip>
```

After saving, GitLab displays the application's \*\*Application ID\*\* and \*\*Secret\*\*. Keep this page open—the secret is only shown once. In your Mintlify dashboard, open \*\*Settings\*\* \\> \*\*Git settings\*\* and find the \*\*Self-hosted GitLab\*\* section under \*\*GitLab OAuth\*\*.

```
Click **Connect Self-Hosted GitLab** and enter:

- **GitLab instance URL**: the public URL of your GitLab instance, for example `https://gitlab.your-company.com`. Mintlify reaches your instance through this URL when exchanging tokens and calling the GitLab API.
- **OAuth application client ID**: the **Application ID** from the previous step.
- **OAuth application client secret**: the **Secret** from the previous step.

Click **Save instance**. Mintlify encrypts the secret at rest and never returns it to the browser after saving.
```

Click \*\*Authorize self-hosted GitLab\*\*. You'll be redirected to your GitLab instance, prompted to sign in if needed, and shown a consent screen listing the requested scopes.

```
After you click **Authorize** on GitLab, you'll be redirected back to Mintlify and the new connection appears in the installations list, badged with your instance hostname.
```

Expand the connection in the dashboard. Mintlify lists every group your authorizing user has Maintainer or higher access to, plus a \*\*Personal projects\*\* entry for projects in the user's personal namespace.

```
Check the box next to each project that should participate in automations. Mintlify registers a webhook on the project, generates a secret token, and stores it encrypted. From then on, Mintlify receives push and merge-request events from your instance for that project.

<Note>
  The connecting user must have **Maintainer** role on a project for Mintlify to mint short-lived project access tokens during automation runs. Without Maintainer, the agent can read but cannot push commits or open merge requests.
</Note>
```

## Rotate credentials

If you need to change the registered application's client secret—for example after renewing it on GitLab—remove the saved instance in Mintlify and add it again with the new values. You must revoke active OAuth connections first; otherwise Mintlify blocks the removal.

Click \*\*Revoke\*\* on every installation listed under the self-hosted instance. This removes the webhook on every connected project and revokes the OAuth token on GitLab. In the \*\*Self-hosted GitLab\*\* card, click \*\*Remove instance\*\*. Follow the \*\*Set up the connection\*\* steps described earlier with the new client secret.

## Troubleshooting

### `invalid_client` after authorizing

GitLab rejected the token-exchange step because the client secret Mintlify sent doesn't match what's registered on the application. The most common cause is that a secret rotated on GitLab—by an explicit **Renew secret**, or silently when someone edited the application—and the value in Mintlify is stale.

Fix: rotate credentials following the [Rotate credentials](https://github.com/#rotate-credentials) steps with the current secret.

### Webhook registration failed: `Invalid url given`

GitLab refused to register the webhook because the URL Mintlify sent (`https://app.mintlify.com/gitlab-oauth-webhook`) was rejected by GitLab's outbound-request allowlist. Self-hosted instances reject "local" URLs unless the admin explicitly allows them.

Fix: in your GitLab admin area, go to **Settings** > **Network** > **Outbound requests** and enable **Allow requests to the local network from webhooks and integrations**. If your network policy blocks `app.mintlify.com`, contact your network admin to allow outbound HTTPS to that host.

### No consent screen on authorize

If you don't see GitLab's consent dialog when authorizing, either:

- The application is marked **Trusted** on GitLab. Trusted applications skip consent for all users. Uncheck **Trusted** in the application settings if you want users to see and confirm scopes.
- Your GitLab user has previously authorized the application with the same scopes. GitLab remembers prior grants and skips consent on subsequent authorizes. Revoke the application authorization in **User settings** > **Applications** > **Authorized applications** to see consent again.