# Source: https://github.com/mintlify/docs/blob/main/editor/tutorial.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# tutorial.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/editor/tutorial.mdx)

History

70 lines (54 loc) · 4.5 KB

## FilesExpand file tree

 main

/

# tutorial.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

70 lines (54 loc) · 4.5 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/tutorial.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>How to use the editor</td></tr><tr><th>description</th><td>Step-by-step walkthrough of the Mintlify editor: create a branch, edit pages, share a preview deployment for review, and publish your changes.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">editor</div></th><th><div dir="auto">tutorial</div></th><th><div dir="auto">branch</div></th><th><div dir="auto">publish</div></th></tr></tbody></table></td></tr></tbody></table>

This tutorial walks you through a complete content update using the editor. You'll create a branch, make a change, share a preview for review, and publish your changes.

A branch is a temporary copy of your content. It's where you make your changes without affecting your live site.

```
Think of branches like drafts. You can merge them into your live site or safely discard them if you choose not to make the changes.

Working on a branch keeps your edits separate from your live site until you're ready to share the content with your users.

1. In the editor toolbar, click the branch name (usually `main`).
    <Frame>
      <img src="/images/editor/create-branch-light.png" alt="Branch name emphasized in the editor toolbar." className="block dark:hidden" />
      <img src="/images/editor/create-branch-dark.png" alt="Branch name emphasized in the editor toolbar." className="hidden dark:block" />
    </Frame>
1. Click **Create new branch**.
1. Enter a name that describes your change, like `update-quickstart`.
1. Click **Create branch**.

The editor switches to your new branch. Any changes you make are only on the branch. They only appear on your live site if you complete the publishing process.
```

Edit an existing page or create a new one.

```
**To edit a page**: Click the page name in the navigation sidebar to open it. Type directly in the editor to add content. Press <kbd>/</kbd> to insert components, images, or other content.

**To create a page**: Click the <Icon icon="plus" /> plus button next to the navigation group where you want to add the page, then click **Add a page** and enter a filename.

<Frame>
  <img src="/images/editor/add-page-light.png" alt="The add page menu opened beside a group in the editor." className="block dark:hidden" />
  <img src="/images/editor/add-page-dark.png" alt="The add page menu opened beside a group in the editor." className="hidden dark:block" />
</Frame>
```

When you're ready for review, create a pull request from your branch. A pull request is a proposal to merge your changes into the branch that builds your live site. Your changes only go live after someone approves and merges the pull request.

```
1. Click **Publish** in the toolbar to open the publish menu.
    <Frame>
      <img src="/images/editor/publish-menu-light.png" alt="The publish menu opened in the editor toolbar." className="block dark:hidden" />
      <img src="/images/editor/publish-menu-dark.png" alt="The publish menu opened in the editor toolbar." className="hidden dark:block" />
    </Frame>
1. Optionally, click any changed file in the list to view and compare your edits against the published version.
1. Click **Create pull request**. Add a title and description, then click **Publish pull request**.

<Note>
  You can also click **Save in branch** to commit your changes without opening a pull request yet. This is useful if you want to keep editing before requesting review.
</Note>

After the pull request is created, a preview deployment builds automatically. The publish menu shows the preview URL, a temporary link where your changes render exactly as they would on your live site. Share this URL with your reviewers.
```

Share the pull request with your team. Reviewers can open the pull request in GitHub or GitLab to leave comments, request changes, or approve it.

```
If a reviewer requests changes, make the edits in the editor on the same branch. Your updates push to the existing pull request automatically. You don't need to create a new one.

When all required reviewers have approved, the pull request is ready to merge.
```

With the pull request approved, click \*\*Publish\*\* in the toolbar to reopen the publish menu. The menu now shows the pull request status and an option to merge.

```
Click **Merge and publish**. The editor merges the pull request and switches you back to your deployment branch. Mintlify builds and deploys your changes. Your live site updates in about 30 seconds to a few minutes.
```