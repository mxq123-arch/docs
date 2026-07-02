# Source: https://github.com/mintlify/docs/blob/main/ai-native.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# ai-native.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)![claude](https://avatars.githubusercontent.com/u/81847?v=4&size=40)

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

and

[claude](https://github.com/mintlify/docs/commits?author=claude)

[Codex MCP guide (](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46) [#6271](https://github.com/mintlify/docs/pull/6271) [)](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46)

Open commit detailssuccess

Jun 25, 2026

[4cffd85](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46) · Jun 25, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/ai-native.mdx)

Open commit details

History

58 lines (40 loc) · 4.12 KB

## FilesExpand file tree

 main

/

# ai-native.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

58 lines (40 loc) · 4.12 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/ai-native.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>AI-native documentation</td></tr><tr><th>sidebarTitle</th><td>AI-native</td></tr><tr><th>description</th><td>Discover how AI-native features enhance reading, writing, and discovering your documentation with the assistant, agent, and MCP server.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">AI</div></th><th><div dir="auto">assistant</div></th><th><div dir="auto">agent</div></th><th><div dir="auto">llms.txt</div></th><th><div dir="auto">MCP</div></th><th><div dir="auto">llms-full.txt</div></th></tr></tbody></table></td></tr></tbody></table>

When you host your documentation on Mintlify, built-in AI features help your users find answers and your team maintain content more efficiently. Your content provides the context for these AI-native features to improve the experiences of reading, writing, and discovering your documentation.

## What makes your documentation AI-native

### Reading

In addition to reading individual pages, users can chat with the [assistant](https://github.com/mintlify/docs/blob/main/assistant) in your documentation for immediate answers to their questions and links to relevant content. The assistant helps guide users through your product with accurate information from your documentation. Embed the assistant into custom apps with the [API](https://github.com/mintlify/docs/blob/main/api/assistant/create-assistant-message-v2) to extend where users can access your documentation.

### Writing

The [agent](https://github.com/mintlify/docs/blob/main/agent) helps you write and maintain documentation. It creates pull requests with proposed changes based on your prompts, pull requests, and Slack threads. Add the agent to your Slack workspace so that anyone on your team can help maintain your documentation by chatting with the agent. Or embed the agent into custom apps via the [API](https://github.com/mintlify/docs/blob/main/api/agent/v2/create-agent-job).

Create [automations](https://github.com/mintlify/docs/blob/main/automations/index) to run the agent on a schedule or on a push to a repository. Each automation defines a prompt for the agent and a trigger for when to run it.

Configure popular tools like [Cursor](https://github.com/mintlify/docs/blob/main/guides/cursor), [Claude Code](https://github.com/mintlify/docs/blob/main/guides/claude-code), and [Devin Desktop](https://github.com/mintlify/docs/blob/main/guides/devin-desktop) to reference the Mintlify schema, your style guide, and best practices.

### Discovering

Your site is automatically optimized for AI tools and search engines to help users discover your documentation. All pages send their content as Markdown to AI agents instead of HTML, which helps these tools process your content faster and use fewer tokens. Every page is also available to view as Markdown by appending `.md` to the URL. Use the [visibility](https://github.com/mintlify/docs/blob/main/components/visibility) component to tailor content for each audience.

Mintlify hosts `llms.txt` and `skill.md` files for your documentation. These industry-standard files help LLMs respond efficiently with relevant information to user queries and provide a list of capabilities for agents to use, so that users are more successful with your product.

Teach your users how to install your \`skill.md\` file so they get better results when using your product with AI tools. Embed an installation prompt directly in your docs with the \[\`Prompt\` component\](/components/prompt):

```mdx
<Prompt description="Install the skill for your product." actions={["copy", "cursor"]}>
npx skills add https://your-docs-domain.com
</Prompt>
```

Your documentation site also hosts an MCP server that lets users connect your documentation directly to their AI tools for up-to-date information about your product directly where they want it.

Full-text search and semantic understanding help users and AI tools find relevant information quickly. Search understands user intent rather than just matching keywords. And if a user encounters a 404 error, your site suggests related pages to help them find what they're looking for. No configuration required.

## Enable AI features

Select any of the following cards for more information.

Configure the assistant to search external sites or direct people to your support team if it can't answer their questions. Get documentation updates automatically on a schedule or when a push event occurs. Add a menu to pages that lets users query AI tools, connect to your MCP server, and copy pages as context with one click.