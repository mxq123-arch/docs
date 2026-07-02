# Source: https://github.com/mintlify/docs/blob/main/editor/git-essentials.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# git-essentials.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/editor/git-essentials.mdx)

History

72 lines (56 loc) · 4.17 KB

## FilesExpand file tree

 main

/

# git-essentials.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

72 lines (56 loc) · 4.17 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/git-essentials.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Git essentials for the editor</td></tr><tr><th>sidebarTitle</th><td>Git essentials</td></tr><tr><th>description</th><td>Understand the Git version control concepts behind the Mintlify editor, including branches, commits, pull requests, and merge workflows.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">git</div></th><th><div dir="auto">version control</div></th><th><div dir="auto">web editor</div></th><th><div dir="auto">branches</div></th><th><div dir="auto">commits</div></th><th><div dir="auto">pull requests</div></th><th><div dir="auto">PRs</div></th></tr></tbody></table></td></tr></tbody></table>

Git lets you control and track changes to files. It's the version control system behind branch-based workflows, where you manage content the same way you would any other codebase.

The web editor handles Git operations for you. Understanding a few key concepts helps you get the most out of the editor and collaborate effectively with your team.

## What Git does for your content

Git tracks every change made to your content. It records what changed, who changed it, when they changed it, and why. This means you can:

- See the full history of any page.
- Undo changes by reverting to a previous version.
- Work on updates without affecting your live site.
- Review changes before they go live.

Your repository is the collection of files and their history that makes up your site. The editor connects to this repository to sync and publish your content.

## Key concepts

These are the Git concepts you'll encounter most often when using the web editor.

A saved snapshot of your changes at a specific point in time. Each commit includes a message describing what changed and creates a permanent record in your project history.

```
When you publish changes, the web editor creates a commit in your Git repository.
```

A separate line of work in your repository. Sometimes called a \*\*feature branch\*\*.

```
Your live site builds from a **deployment branch**, usually called `main`. Other branches let you work on changes independently without affecting your live site. Nothing on a branch goes live until you merge it into your deployment branch with a pull request.

Switch between branches using the branch dropdown in the editor toolbar. If you have unpublished changes, the editor lets you bring them to the new branch or leave them on your current branch.
```

The branch that builds your live site, typically called \`main\`. Changes merged into this branch automatically deploy to your site. A proposal to merge changes from one branch into another. Pull requests let your team review and discuss changes before they go live.

```
When you publish changes on a feature branch (or when your repository requires pull requests), the web editor creates a pull request. Your team reviews and merges the pull request in your Git provider (GitHub or GitLab).
```

Combining changes from one branch into another. After your team reviews and approves a pull request, merging the branch incorporates your changes into the deployment branch and publishes them. Occurs when two branches have incompatible changes to the same files. The editor helps you resolve conflicts when they occur. A comparison showing the differences between two versions of a file. The editor shows a visual diff of your pending changes before you publish so you can review exactly what gets committed.

## How the editor maps to Git

Every action in the web editor corresponds to a Git operation. Here is the full reference:

| Action in the editor | Git operation |
| --- | --- |
| Edit a page | Changes auto-save to Mintlify servers. No Git commit yet. |
| Publish on your deployment branch | `git commit` and `git push`. Triggers a deployment. |
| Save in branch | `git commit` to the current feature branch. |
| Create pull request | `git push` and opens a pull request against your deployment branch. |
| Merge and publish | Merges the pull request and triggers a deployment. |
| Create a branch | `git checkout -b <branch-name>` |
| Switch branches | `git checkout <branch-name>` |
| External push or CLI update | Incoming changes sync into the editor automatically using a three-way merge. |