# Source: https://github.com/mintlify/docs/blob/main/deploy/deployments.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# deployments.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/deployments.mdx)

History

47 lines (37 loc) · 2.68 KB

 main

/

# deployments.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

47 lines (37 loc) · 2.68 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/deployments.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Deployments</td></tr><tr><th>description</th><td>Manage documentation deployments in the Mintlify dashboard, including viewing deployment history, monitoring build status, and troubleshooting.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">manual deployment</div></th><th><div dir="auto">deployment history</div></th><th><div dir="auto">deployment triggers</div></th><th><div dir="auto">delete deployment</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Your documentation site automatically deploys when you push changes to your connected repository. This requires the Mintlify GitHub app to be properly installed and connected.

If your latest changes are not appearing on your live site, first check that the GitHub account or organization that owns your docs repository has the GitHub App installed. See [GitHub troubleshooting](https://github.com/mintlify/docs/blob/main/deploy/github#troubleshooting) for more information.

If you have the GitHub App installed, but changes are still not deploying, manually trigger a deployment from your dashboard.

## Manually trigger a deployment

Check that your latest commit appears in your docs repository and did not encounter any errors. Go to your \[dashboard\]([https://app.mintlify.com](https://app.mintlify.com)) and click the deploy button.

[![The manual update button emphasized with an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/deployments/manual-update-light.png)](https://github.com/mintlify/docs/blob/main/images/deployments/manual-update-light.png)

[![The manual update button emphasized with an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/deployments/manual-update-dark.png)](https://github.com/mintlify/docs/blob/main/images/deployments/manual-update-dark.png)

## Delete a deployment

You can permanently delete a deployment from the [Danger zone](https://app.mintlify.com/settings/organization/danger-zone) in your dashboard settings. This action is irreversible and removes all deployment data, including any associated preview deployments.

Go to the \[Danger zone\]([https://app.mintlify.com/settings/organization/danger-zone](https://app.mintlify.com/settings/organization/danger-zone)) in the settings page of your dashboard. 1. In the \*\*Delete my deployment\*\* section, provide a reason for deletion. 2. Click the delete button and confirm that you want to delete the deployment. Deleting a deployment is permanent and cannot be undone. If you have an active subscription, you'll receive a prorated credit for any unused time remaining in your billing period.

If you have multiple deployments, Mintlify redirects you to another deployment after deletion. If you delete your only deployment, Mintlify redirects you to the Mintlify homepage. When you delete a deployment, the organization admin receives an email notification confirming the deletion.