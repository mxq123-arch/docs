# Source: https://github.com/mintlify/docs/blob/main/editor/branching-and-publishing.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# branching-and-publishing.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)![claude](https://avatars.githubusercontent.com/u/81847?v=4&size=40)

3 people

[Update from code changes: switch hosted docs domain to mintlify.site (](https://github.com/mintlify/docs/commit/3ca550b188eb71db76cf352efd816131e1fbad45) [#…](https://github.com/mintlify/docs/pull/6296)

Open commit detailssuccess

Jun 26, 2026

[3ca550b](https://github.com/mintlify/docs/commit/3ca550b188eb71db76cf352efd816131e1fbad45) · Jun 26, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/editor/branching-and-publishing.mdx)

Open commit details

History

185 lines (115 loc) · 10.2 KB

## FilesExpand file tree

 main

/

# branching-and-publishing.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

185 lines (115 loc) · 10.2 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/branching-and-publishing.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Branching and publishing</td></tr><tr><th>description</th><td>Understand how branches and protection rules determine what happens when you publish, and how to manage the full review and deployment workflow.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">editor</div></th><th><div dir="auto">branch</div></th><th><div dir="auto">publish</div></th><th><div dir="auto">pull request</div></th><th><div dir="auto">preview</div></th><th><div dir="auto">git</div></th><th><div dir="auto">merge</div></th><th><div dir="auto">deploy</div></th></tr></tbody></table></td></tr></tbody></table>

The web editor autosaves everything as you type, but your changes are only live when you choose to publish them.

What happens when you publish depends on two things: **which branch you're on** and **whether that branch requires pull requests**.

## Saving versus publishing

**Saving** happens automatically. Mintlify stores your edits on its servers and persists them across browser tabs, devices, and network interruptions.

**Publishing** commits your changes to your Git repository. Click **Publish** in the toolbar to open the publish menu, save your changes as a Git commit, and create a pull request.

The editor tracks the following as pending changes:

- Content edits in pages
- New or deleted pages
- Navigation structure changes
- Media uploads
- Configuration updates

## What happens when you publish

The actions available when you click the publish button depend on your current branch and whether it has branch protection rules that require pull requests.

| Branch type | Branch protection | Available actions |
| --- | --- | --- |
| Deployment branch | None | **Publish** directly to your live site |
| Deployment branch | Pull requests required | **Create branch** to move changes to a new branch |
| Feature branch | None | **Save in branch**, **Create pull request** |
| Feature branch | Pull requests required | **Save in branch**, **Create pull request** |

- **Publish**: Commits and deploys your changes to your live site immediately.
- **Save in branch**: Commits your changes to the feature branch without merging to your deployment branch.
- **Create branch**: Moves your pending changes to a new feature branch when you're on a protected deployment branch.
- **Create pull request**: Opens a pull request targeting your deployment branch.

If there are no pending changes, the editor disables the publish and save actions.

Your live site updates after Mintlify builds and deploys your changes. This typically takes 30 seconds to a few minutes. Check the deployment status on your \[dashboard\]([https://app.mintlify.com](https://app.mintlify.com)).

## When to use a branch

**Edit directly on your deployment branch** if you do not use a Git-based workflow.

**Create a branch** when you use a branch-based workflow where you make each change to your content on a separate branch.

## Create and switch branches

### Create a branch

1. Click the branch name in the editor toolbar.
2. Click **Create new branch**.
3. If you have pending changes, choose whether to bring them to the new branch or leave them on the current branch.
4. Enter a name and click **Create branch**.

Use descriptive branch names so you can easily identify them and other people understand what each branch is for.

### Switch branches

1. Click the branch name in the toolbar.
2. Search for or scroll to the branch you want.
3. Click the branch to switch to it.

Switching branches while you have unpublished changes prompts you to bring those changes to the new branch or leave them behind. Changes left behind remain on your original branch. To copy a branch name, hover over the branch in the dropdown and click the copy icon. This is useful when sharing the branch with teammates or referencing it in a pull request.

## Preview your changes

Every time you save changes to a feature branch, Mintlify builds a preview deployment, a temporary URL where your changes render exactly as they look when published.

### Access and share a preview

1. Click **Publish** in the editor toolbar.
2. In the publish menu, click the preview URL. The URL format is `organization-branch-name.mintlify.site`. [![Preview URL emphasized in the publish menu.](https://github.com/mintlify/docs/raw/main/images/editor/preview-url-light.png)](https://github.com/mintlify/docs/blob/main/images/editor/preview-url-light.png) [![Preview URL emphasized in the publish menu.](https://github.com/mintlify/docs/raw/main/images/editor/preview-url-dark.png)](https://github.com/mintlify/docs/blob/main/images/editor/preview-url-dark.png)

Copy the URL and send it to reviewers. The preview updates automatically each time you save to the branch.

### Restrict access to previews

Preview URLs are publicly accessible by default. To restrict access to members of your Mintlify organization, enable preview authentication in the [Add-ons](https://app.mintlify.com/products/addons) page of your dashboard.

### Share editor links

To invite a teammate to a specific page on a branch, copy the URL from your browser's address bar and share it. Anyone with access to your Mintlify organization can open the link directly in their editor session.

The URL format is:

```
https://app.mintlify.com/{org}/{project}/editor/{branch}/~/{filepath}
```

For example: `https://app.mintlify.com/acme/docs/editor/main/~/guides/quickstart.mdx`

## Review and merge pull requests

When a pull request is open for the current branch, the publish menu shows a review panel with:

- The pull request title, description, and whether it is a draft.
- The source and target branches.
- The number of changed files.
- The approval requirement on the deployment branch: **Approval required**, **Code owner required**, or no requirement.
- The current review status: **Approved**, **Changes requested**, or **Awaiting review**.

Click **Open in GitHub** or **Open in GitLab** to view the pull request in your Git provider.

After a reviewer approves a pull request, click **Merge and publish** to merge and deploy directly from the editor. The editor switches to your deployment branch after merging.

### Approve pull requests from the editor

For GitHub repositories, reviewers can approve open pull requests in the editor. When a pull request is open, an **Approve pull request** button appears in the review panel if your account has permission to review it. Click **Approve pull request** when the changes are ready to merge. The review status updates to **Approved** and the **Merge and publish** action becomes available.

The approve action is not available for draft pull requests, pull requests you have already approved, or GitLab merge requests. Click **Open in GitLab** to approve a merge request in GitLab.

Configure branch protection rules in your Git provider to require pull requests. See \[About protected branches\]([https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)) in the GitHub help or \[Protected branches\]([https://docs.gitlab.com/user/project/repository/branches/protected/](https://docs.gitlab.com/user/project/repository/branches/protected/)) in the GitLab help.

### Review changes before merging

Click any changed file in the publish menu to open it in diff view and compare your branch against the published version. In visual mode you see a visual diff. In source mode you see a text diff. Files that can't display a diff, such as images or deleted files, appear in the list but aren't clickable.

Changed pages are highlighted in the file tree so you can see at a glance which files an [automation](https://github.com/mintlify/docs/blob/main/automations) or teammate touched. Unlisted pages that appear in the branch diff are also openable from the publish menu, even though they don't appear in your site navigation.

### Open an automation run in the editor

When an [automation](https://github.com/mintlify/docs/blob/main/automations) opens a pull request, you can jump straight from the run review UI or its Slack notification into the editor on the automation's branch:

- From the **Automation Runs** page in your dashboard, click **Open in editor** on a completed run.
- From a Slack notification, click the **View changes** link.

Either entry point opens the editor on the automation's branch with the changed pages preselected in the publish menu, so you can review the diff and merge or request changes without leaving the editor.

### Simultaneous publishing

Only one publish can happen at a time per branch. If another team member publishes to the same branch, wait for the current publish to complete before trying again.

### Commit messages

When you publish, you can enter a commit message before confirming. If you leave it blank, the editor uses a default message that lists the files you created, updated, moved, or deleted.

## Resolve conflicts

Conflicts occur when your branch and the deployment branch have incompatible changes to the same files. For example, when you and a teammate edited the same lines in a file or moved a file to different locations.

The editor displays a warning when conflicts block publishing. Follow the prompts to choose which version of each conflicting section to keep.

## Collaborate in real time

When multiple people open the same page on the same branch, they edit together in real time. Each person's cursor and edits are visible to everyone, with avatars shown in the toolbar.

- Changes from all collaborators merge automatically. Two people editing the same section won't create conflicts.
- Undo only affects your own edits.
- If you lose your connection, edits save locally and sync when you reconnect.

When the [Mintlify agent](https://github.com/mintlify/docs/blob/main/agent) edits a page through the API or MCP, it appears in the editor like any other collaborator. You see the agent's avatar in the toolbar and a live cursor at its most recent edit location. The cursor clears automatically after the agent finishes.

## Git sync

When someone pushes changes to your repository from outside the editor, the editor incorporates those changes automatically.

Non-overlapping changes apply automatically. If a remote change and your local edit affect the same part of a page, the editor highlights the conflict so you can resolve it.

## Commit signing

Sign commits with your GitHub account by authorizing it in your [account settings](https://app.mintlify.com/settings/account). Without authorization, the Mintlify GitHub App signs commits made in the web editor.

For a reference of how editor actions map to Git operations, see [Git essentials](https://github.com/mintlify/docs/blob/main/editor/git-essentials#how-the-editor-maps-to-git).