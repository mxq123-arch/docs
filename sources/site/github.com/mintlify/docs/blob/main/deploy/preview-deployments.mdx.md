# Source: https://github.com/mintlify/docs/blob/main/deploy/preview-deployments.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# preview-deployments.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/preview-deployments.mdx)

History

127 lines (89 loc) · 7.25 KB

 main

/

# preview-deployments.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

127 lines (89 loc) · 7.25 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/preview-deployments.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Preview deployments</td></tr><tr><th>description</th><td>Get unique preview URLs for each pull request so reviewers can see documentation changes in a live environment before merging to production.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">preview URLs</div></th><th><div dir="auto">pull request previews</div></th><th><div dir="auto">branch previews</div></th><th><div dir="auto">staging environments</div></th></tr></tbody></table></td></tr></tbody></table>

Preview deployments let you see how changes to your docs look before merging to production. Each preview creates a shareable URL that updates automatically as you push new changes.

Preview URLs are publicly viewable by default. Share a preview link with anyone who needs to review your changes.

## Create preview deployments

Preview deployments are created automatically through pull requests or manually from your dashboard.

### Automatic previews

Automatic previews are only created for pull requests targeting your \[deployment branch\](/guides/git-concepts#deployment-branch).

When you create a pull request, the Mintlify bot automatically adds a link to view the preview deployment in your pull request. The preview updates each time you push new commits to the branch.

[![Link to view deployment in the pull request timeline](https://github.com/mintlify/docs/raw/main/images/previews/preview-deployment-light.png)](https://github.com/mintlify/docs/blob/main/images/previews/preview-deployment-light.png)

[![Link to view deployment in the pull request timeline](https://github.com/mintlify/docs/raw/main/images/previews/preview-deployment-dark.png)](https://github.com/mintlify/docs/blob/main/images/previews/preview-deployment-dark.png)

### Manual previews

You can manually create a preview for any branch.

1. Go to your [dashboard](https://app.mintlify.com/).
2. Click **Previews**.
3. Click **Create custom preview**.
4. Enter the name of the branch you want to preview.
5. Click **Create preview**.

### API

You can also create preview deployments programmatically using the [Trigger preview deployment](https://github.com/mintlify/docs/blob/main/api/preview/trigger) API endpoint. This is useful for integrating preview creation into CI/CD pipelines or custom tooling.

## Redeploy a preview

Redeploy a preview to refresh content or retry after a failed deployment.

1. Click the preview from your [dashboard](https://app.mintlify.com/).
2. Click **Redeploy**.

[![The Previews menu with the deploy button emphasized by an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/previews/redeploy-preview-light.png)](https://github.com/mintlify/docs/blob/main/images/previews/redeploy-preview-light.png)

[![The Previews menu with the deploy button emphasized by an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/previews/redeploy-preview-dark.png)](https://github.com/mintlify/docs/blob/main/images/previews/redeploy-preview-dark.png)

## Preview widget

The preview widget appears on preview deployments to help you navigate and review updated pages. The widget is a floating button in the bottom-right corner of your preview deployment.

[![Preview widget expanded to show list of changed files.](https://github.com/mintlify/docs/raw/main/images/previews/widget-light.png)](https://github.com/mintlify/docs/blob/main/images/previews/widget-light.png)

[![Preview widget expanded to show list of changed files.](https://github.com/mintlify/docs/raw/main/images/previews/widget-dark.png)](https://github.com/mintlify/docs/blob/main/images/previews/widget-dark.png)

1. Click the widget to show all added, modified, or removed files in the preview.
2. Click a file to view the changes on the corresponding page.
3. Use the search bar to filter the list of changed files.
4. Hover over a file and click the **Open in editor** icon to edit the file directly in the web editor.

The widget only appears on preview deployments, not on your live site or local previews.

## Restrict access to preview deployments

By default, preview deployments are publicly accessible to anyone with the URL. You can restrict access by requiring organization authentication for all previews or by password-protecting individual previews.

### Require organization authentication

Restrict preview access to authenticated members of your Mintlify organization.

1. Navigate to the **Previews** section in the [Add-ons](https://app.mintlify.com/products/addons) page of your dashboard.
2. Click the **Preview authentication** toggle to enable or disable preview authentication.

[![The preview authentication toggle in the Add-ons page](https://github.com/mintlify/docs/raw/main/images/previews/preview-auth-light.png)](https://github.com/mintlify/docs/blob/main/images/previews/preview-auth-light.png)

[![The preview authentication toggle in the Add-ons page](https://github.com/mintlify/docs/raw/main/images/previews/preview-auth-dark.png)](https://github.com/mintlify/docs/blob/main/images/previews/preview-auth-dark.png)

### Password-protect an individual preview

Password-protected previews are available on \[Enterprise plans\]([https://mintlify.com/pricing?ref=preview-deployments](https://mintlify.com/pricing?ref=preview-deployments)).

Password-protect a specific preview to share it with external reviewers without adding them to your Mintlify organization. This option is available when creating a manual preview and is not shown when organization authentication is already enabled for your deployment.

1. Go to your [dashboard](https://app.mintlify.com/).
2. Click **Previews**.
3. Click **Create custom preview**.
4. Enter the name of the branch you want to preview.
5. Toggle **Make private** on and enter a password. Passwords must be at least 8 characters.

[![The Create a custom preview modal with the Make private toggle enabled and a password field.](https://github.com/mintlify/docs/raw/main/images/previews/private-preview-light.png)](https://github.com/mintlify/docs/blob/main/images/previews/private-preview-light.png)

[![The Create a custom preview modal with the Make private toggle enabled and a password field.](https://github.com/mintlify/docs/raw/main/images/previews/private-preview-dark.png)](https://github.com/mintlify/docs/blob/main/images/previews/private-preview-dark.png)

6\. Click \*\*Create preview\*\*.

## Preview lifetime

Preview deployments stay live as long as their source branch exists in your repository and continue to receive updates on every push.

- **Automatic previews**: The preview for a pull request remains available while the PR is open and after it's merged or closed, as long as the source branch still exists. When you delete the branch, the next dashboard sync removes the preview.
- **Manual previews**: Manual previews stay live until you delete them. Redeploying a manual preview refreshes its content against the latest commit on the specified branch.
- **Delete a preview**: In your [dashboard](https://app.mintlify.com/), go to **Previews**, open the preview, and click **Delete** to remove it immediately.

Preview URLs are unique per branch. If you delete a preview and later recreate one for the same branch, Mintlify may issue a new URL.

## Troubleshooting preview deployments

If your preview deployment fails, try these troubleshooting steps.

- **View the build logs**: In your [dashboard](https://app.mintlify.com/), go to **Previews** and click the failed preview. The deployment logs show errors that caused failures.
- **Check your configuration**:
 - Missing `docs.json` at the configured content root. If your `docs.json` is in a subdirectory, confirm the **docs.json is in a subdirectory** setting points to the correct path.
 - Invalid `docs.json` syntax (for example, an empty file or a stray trailing comma that breaks JSON parsing).
 - Schema errors in `docs.json` such as an invalid `theme`, malformed `navigation`, or unresolved `$ref` values.
 - Missing or incorrect file paths referenced in your navigation.
 - Invalid frontmatter in MDX files.
 - Broken image links or missing image files.
- **Validate locally**: Run `mint dev` and `mint validate` locally to catch configuration and build errors before pushing to the repository.
- **Check recent changes**: Review the most recent commits in your branch to identify what changes caused the build to fail.