# Source: https://github.com/mintlify/docs/blob/main/snippets/gitlab-workflow-setup.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# gitlab-workflow-setup.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/snippets/gitlab-workflow-setup.mdx)

History

7 lines (5 loc) · 533 Bytes

 main

/

# gitlab-workflow-setup.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

7 lines (5 loc) · 533 Bytes

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/snippets/gitlab-workflow-setup.mdx)

Copy raw file

Download raw file

Edit and raw actions

## GitLab setup

To use GitLab repositories in a workflow, connect each project through the [GitLab OAuth](https://app.mintlify.com/settings/organization/gitlab-oauth) settings page. Connect every repository the workflow touches—your documentation repository and any trigger or context repositories. You must have at least the Maintainer role on each project.

Workflows require a paid GitLab tier. The agent uses short-lived project access tokens for repository access, which GitLab's Free plan does not support.