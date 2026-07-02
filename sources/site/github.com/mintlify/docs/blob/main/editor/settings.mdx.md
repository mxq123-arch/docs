# Source: https://github.com/mintlify/docs/blob/main/editor/settings.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# settings.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/editor/settings.mdx)

History

105 lines (68 loc) · 4.58 KB

## FilesExpand file tree

 main

/

# settings.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

105 lines (68 loc) · 4.58 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/settings.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Editor settings for AI and publishing</td></tr><tr><th>description</th><td>Configure AI instructions, pull request defaults, draft behavior, and the default merge method to control how the Mintlify web editor publishes changes.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">editor</div></th><th><div dir="auto">settings</div></th><th><div dir="auto">ai</div></th><th><div dir="auto">instructions</div></th><th><div dir="auto">publishing</div></th><th><div dir="auto">pull request</div></th><th><div dir="auto">draft</div></th><th><div dir="auto">merge</div></th></tr></tbody></table></td></tr></tbody></table>

The web editor has two layers of settings:

- **Your settings** apply only to you and control how the editor's AI assists with your edits.
- **Publishing settings** apply to everyone on a deployment and shape what happens when you commit changes and turn them into pull requests.

You can configure both from the settings panel. To open it, click the settings icon in the editor toolbar.

## AI instructions

AI instructions are persistent guidance that the editor sends to the AI alongside your request. Use them to capture style and tone rules you don't want to repeat every time, like voice, terminology, or formatting conventions.

Your instructions apply to:

- **Edit with AI** actions on a selection, such as rewrite, expand, or fix.
- **Agent sessions** started from the editor.

Each teammate maintains their own instructions, scoped to their user account.

### When to use AI instructions

Add AI instructions when you find yourself repeating the same guidance in prompts, for example:

- Enforcing second-person voice or sentence case headings.
- Preferring specific product names or terminology.
- Banning marketing language or filler phrases.
- Requiring certain components, like always using `<Note>` for callouts.

Keep instructions short and specific. The AI follows them on every request, so vague or contradictory rules degrade results.

### Configure AI instructions

1. Click the settings icon in the editor toolbar.
2. In the **AI instructions** field, enter the guidance you want the AI to follow.
3. Save your changes.

Example:

```
- Use second person ("you") and active voice.
- Use sentence case for all headings.
- Refer to the product as "Acme" — never "Acme Inc." or "the platform".
- Wrap notes and warnings in <Note> or <Warning> components.
- Do not add introductory filler like "In this guide" or "Let's explore".
```

Leave the field empty to remove your instructions.

## Publishing settings

You configure publishing settings per deployment, and they apply to everyone who publishes from the editor. They control how the editor generates, opens, and merges pull requests and commits.

You need admin access to your Mintlify deployment to change publishing settings.

### Pull request instructions

Pull request instructions guide the AI when it generates a pull request title and description. They apply whenever the editor opens a pull request on your behalf, including from **Create pull request** and **Merge and publish** flows.

Use pull request instructions to standardize what reviewers see, for example:

- Required sections like **Summary** and **Changes**.
- A description template that links to a tracking system.
- Tone or length requirements for titles.

Example:

```
Title: imperative mood, under 70 characters, no trailing period.
Description: include a "## Summary" section (one sentence) and a
"## Changes" section as a bulleted list. Link any referenced page
using its relative path.
```

### Create pull requests as drafts by default

Turn this on to have the editor open every new pull request in draft state. You can't merge a draft pull request until you mark it ready for review. This is useful when:

- Your team requires a manual review pass before a pull request is open for approval.
- You want to share preview URLs without signaling that the change is ready to merge.

You can still mark a pull request as ready for review from your Git provider.

### Default merge method

Choose how the editor merges pull requests when you click **Merge and publish**:

- **Merge**: Creates a merge commit that preserves the full branch history.
- **Squash**: Combines all commits in the branch into a single commit on your deployment branch.
- **Rebase**: Replays each commit from the branch onto your deployment branch without a merge commit.

The editor uses the selected method by default. If you pass an explicit merge method through the API or your Git provider's UI, that choice takes precedence.

Match your default merge method to your Git provider's branch protection settings. If your deployment branch only allows squash merges, set the default to \*\*Squash\*\* to avoid failed merges from the editor.

## Related

- [Branching and publishing](https://github.com/mintlify/docs/blob/main/editor/branching-and-publishing)
- [Configurations](https://github.com/mintlify/docs/blob/main/editor/configurations)