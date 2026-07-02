# Source: https://github.com/mintlify/docs/blob/main/deploy/gitlab.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# gitlab.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/gitlab.mdx)

History

145 lines (118 loc) · 6.44 KB

 main

/

# gitlab.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

145 lines (118 loc) · 6.44 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/gitlab.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>GitLab</td></tr><tr><th>description</th><td>Connect your GitLab repository to Mintlify for automated documentation deployments, merge request previews, and continuous synchronization.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">GitLab integration</div></th><th><div dir="auto">access tokens</div></th><th><div dir="auto">merge request previews</div></th><th><div dir="auto">self-hosted</div></th><th><div dir="auto">instance</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Mintlify uses access tokens and webhooks to authenticate and sync changes between GitLab and Mintlify.

- Mintlify uses access tokens to pull information from GitLab.
- GitLab uses webhooks to notify Mintlify when you make changes, which enables preview deployments for merge requests.

## Set up the connection

When you open [Git Settings](https://app.mintlify.com/settings/deployment/git-settings) for the first time, a setup wizard guides you through connecting your GitLab repository.

On the \[Git Settings\]([https://app.mintlify.com/settings/deployment/git-settings](https://app.mintlify.com/settings/deployment/git-settings)) page, click \*\*Connect to GitLab\*\* and then click \*\*Continue\*\*. If you already have a GitLab repository with your documentation, you can skip the download and click \*\*Continue setup\*\* directly.

```
If your documentation is hosted by Mintlify, download it as a zip file.
* Create a new repository in GitLab.
* Extract the zip contents.
* Push the contents to your repository.

Click **Continue setup** to proceed.
```

In your GitLab project, navigate to \*\*Settings\*\* > \*\*General\*\* and locate your \*\*Project ID\*\*.

[![The General Settings page in the GitLab dashboard. The Project ID is highlighted.](https://github.com/mintlify/docs/raw/main/images/gitlab/gitlab-project-id.png)](https://github.com/mintlify/docs/blob/main/images/gitlab/gitlab-project-id.png)

Navigate to \*\*Settings\*\* > \*\*Access Tokens\*\* and click \*\*Add new token\*\*.

```
Configure the token with these settings:
- **Name**: Mintlify
- **Role**: Maintainer (required for private repos)
- **Scopes**: `api` and `read_api`

Click **Create project access token** and copy the token.

<Note>
  If Project Access Tokens are not available, you can use a Personal Access Token instead. Note that Personal Access Tokens expire and must be updated.
</Note>

<Frame>
  <img src="/images/gitlab/gitlab-project-access-token.png" alt="The Access tokens page in the GitLab dashboard. The settings to configure for Mintlify are highlighted." />
</Frame>
```

Back in the setup wizard, fill in the following fields:

```
- **GitLab instance URL**: Leave blank for `gitlab.com`, or enter your self-hosted instance URL (for example, `https://gitlab.your-domain.com`). Your instance must be publicly accessible for Mintlify to reach it.
- **Project ID**: The project ID from your GitLab project settings.
- **GitLab deployment token**: The access token you generated.
- **Branch**: Select the branch to deploy your documentation from.

Click **Connect**.
<Frame>
  <img src="/images/gitlab/gitlab-config-light.png" alt="The GitLab configuration panel in the Git Settings page of the Mintlify dashboard." className="block dark:hidden" />
  <img src="/images/gitlab/gitlab-config-dark.png" alt="The GitLab configuration panel in the Git Settings page of the Mintlify dashboard." className="hidden dark:block" />
</Frame>
```

## Update an existing connection

To modify your GitLab connection settings after the initial setup, go to [Git Settings](https://app.mintlify.com/settings/deployment/git-settings) and update your project ID, access token, branch, or instance URL directly.

## Revalidate Git settings

If your deployment shows unexpected behavior, such as missing branch options or stale configuration, you can force Mintlify to refresh your Git source.

Go to \[Git Settings\]([https://app.mintlify.com/settings/deployment/git-settings](https://app.mintlify.com/settings/deployment/git-settings)) in your dashboard. Click the green \*\*Active\*\* badge in the corner of the GitLab settings box to revalidate your Git source.

## Create the webhook

Webhooks notify Mintlify when you push changes so that deployments trigger automatically.

1\. In GitLab, navigate to \*\*Settings\*\* > \*\*Webhooks\*\*. 2. Click \*\*Add new webhook\*\*.

[![Screenshot of the Webhooks page in the GitLab dashboard.](https://github.com/mintlify/docs/raw/main/images/gitlab/gitlab-webhook.png)](https://github.com/mintlify/docs/blob/main/images/gitlab/gitlab-webhook.png)

Name the webhook \*\*Mintlify\*\*.

```
In the **URL** field, enter the endpoint `https://leaves.mintlify.com/gitlab-webhook`.
```

In your Mintlify dashboard, click \*\*Show Webtoken\*\*. Copy the webtoken.

[![Screenshot of the GitLab connection in the Mintlify dashboard.](https://github.com/mintlify/docs/raw/main/images/gitlab/show-webtoken-light.png)](https://github.com/mintlify/docs/blob/main/images/gitlab/show-webtoken-light.png)

[![Screenshot of the GitLab connection in the Mintlify dashboard.](https://github.com/mintlify/docs/raw/main/images/gitlab/show-webtoken-dark.png)](https://github.com/mintlify/docs/blob/main/images/gitlab/show-webtoken-dark.png)

In GitLab, paste the webtoken from your Mintlify dashboard in the \*\*Secret token\*\* field. Select the following events to trigger the webhook: - \*\*Push events\*\* (All branches) - \*\*Merge requests events\*\* You should see the following settings after configuring the webhook:

```
- **Name**: Mintlify
- **URL**: `https://leaves.mintlify.com/gitlab-webhook`
- **Secret token**: The webtoken from your Mintlify dashboard
- **Events**: **Push events** (All branches) and **Merge requests events**

Add the webhook.

<Frame>
  <img src="/images/gitlab/gitlab-project-webtoken.png" alt="The Webhook page in the GitLab dashboard. The settings to configure for Mintlify are highlighted." />
</Frame>
```

After you create the webhook, click the \*\*Test\*\* dropdown. Click \*\*Push events\*\* to send a sample payload. If the test returns \`Hook executed successfully: HTTP 200\`, you configured the webhook correctly.

```
<Frame>
  <img src="/images/gitlab/gitlab-project-webtoken-test.png" alt="Screenshot of the GitLab Webhooks page. The 'Push events' menu item is highlighted in the 'Test' menu." />
</Frame>
```