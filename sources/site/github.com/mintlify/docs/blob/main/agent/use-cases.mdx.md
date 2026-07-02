# Source: https://github.com/mintlify/docs/blob/main/agent/use-cases.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# use-cases.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/agent/use-cases.mdx)

History

75 lines (40 loc) · 4 KB

 main

/

# use-cases.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

75 lines (40 loc) · 4 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/agent/use-cases.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Use cases</td></tr><tr><th>description</th><td>Explore real-world examples of using the Mintlify agent to automate documentation updates, capture knowledge, and maintain accurate docs.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">agent automations</div></th><th><div dir="auto">documentation automations</div></th><th><div dir="auto">automation examples</div></th></tr></tbody></table></td></tr></tbody></table>

The agent assists with many different documentation tasks. These examples show some of the ways you can integrate the agent into your documentation process. Try an approach that fits how your team currently works and adapt it to your specific needs.

## Iterate on a prompt in a Slack thread

Prompt the agent, then continue to mention it with `@mintlify` in the same thread to refine and iterate on the pull request that it creates.

For example: `@mintlify Our quickstart page needs a new section on inviting collaborators`. Then `@mintlify The new section should be called "Inviting collaborators"`. Followed by any other iterations.

## Start with the agent, finish manually

Prompt the agent to begin a project, then check out the branch it creates and finish the task in your local environment or the web editor. The agent can help you get started, then you can take over to complete the task.

For example: `@mintlify Update the quickstart page to include information about inviting collaborators` and then checkout the branch to make any additional changes using your preferred method.

## Update docs when merging feature changes

When you merge a feature pull request, share the PR link with the agent to update relevant docs.

For example: `@mintlify This PR adds a new authentication method. Update the docs to include the new auth flow: [PR link]`.

## Generate release notes from a pull request

Prompt the agent with a specific pull request to generate release notes or changelog updates based on the commit history.

For example: `@mintlify Generate release notes for this PR: [PR link]`.

## Address pull request review feedback

Share a pull request link with the agent to address reviewer comments and code review feedback on documentation pull requests.

For example: `@mintlify Address the review comments on this PR: [PR link]`.

## Generate code examples

Prompt the agent to generate code examples for features throughout your docs or on specific pages.

For example: `@mintlify Generate a code example to make the authentication method easier to understand`.

## Add images or files to your docs

Attach files or images directly to your Slack message when prompting the agent. The agent processes the attachment and includes it in the documentation.

For example: `@mintlify Add this diagram to the architecture overview page` with the image attached to the message.

## Review existing content

Prompt the agent to review existing content for technical accuracy, style, grammar, or other issues.

For example: `@mintlify Review the API rate limiting section. We changed limits last month`.

## Respond to user feedback

Prompt the agent with feedback from your users to make focused updates to your docs.

For example: `@mintlify Users are getting confused by step 3 in the setup guide. What might be making it unclear?`.

## Automate with automations

Create automations to automate recurring tasks and reactive maintenance tasks like writing changelogs or updating content when you add new features to your product.

See [Automations overview](https://github.com/mintlify/docs/blob/main/automations/index) for more information.

## Automate with the API

Integrate the agent into your existing automation tools to automatically update documentation when code changes occur, trigger content reviews, or sync documentation updates across multiple repositories.

Use the agent endpoints to [create jobs](https://github.com/mintlify/docs/blob/main/api/agent/v2/create-agent-job), [get job status](https://github.com/mintlify/docs/blob/main/api/agent/v2/get-agent-job), and [send messages](https://github.com/mintlify/docs/blob/main/api/agent/v2/send-message).

When creating jobs via the API, you can control whether pull requests open in draft mode using the `asDraft` parameter (defaults to `false`). Set `asDraft: true` to create draft pull requests, or keep the default to create non-draft pull requests ready for immediate review and merging in automated workflows.