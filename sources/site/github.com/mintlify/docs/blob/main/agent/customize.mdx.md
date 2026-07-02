# Source: https://github.com/mintlify/docs/blob/main/agent/customize.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# customize.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/agent/customize.mdx)

History

52 lines (39 loc) · 2.85 KB

 main

/

# customize.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

52 lines (39 loc) · 2.85 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/agent/customize.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Customize agent behavior</td></tr><tr><th>description</th><td>Customize agent behavior with an `AGENTS.md` configuration file to control how the agent handles documentation tasks and follows your conventions.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">AGENTS.md</div></th><th><div dir="auto">agent configuration</div></th><th><div dir="auto">custom instructions</div></th><th><div dir="auto">agent customization</div></th></tr></tbody></table></td></tr></tbody></table>

Create a `.mintlify/AGENTS.md` file at the root of your documentation project to customize the agent's behavior (`Agents.md` is also an accepted filename).

Place your \`AGENTS.md\` file inside the \`.mintlify/\` directory, not at the root of your project. If you store the file at the root of your project, your custom instructions are publicly accessible by the \`/agents.md\` path. The \`.mintlify/\` directory is not served publicly so your \`AGENTS.md\` file is not accessible when in that directory.

If you must store your `AGENTS.md` file at the root of your project or any other directory, add it to your [`.mintignore`](https://github.com/mintlify/docs/blob/main/organize/mintignore) file to exclude it from your documentation site.

Add any instructions that you want the agent to follow. The agent appends these instructions to its system prompt, so the instructions apply to all tasks whether you use the agent in your dashboard, on Slack, or via the API.

## What to include in AGENTS.md

Consider adding instructions for:

- **Style preferences**: Voice, tone, formatting, and terminology specific to your documentation.
- **Code standards**: Programming languages, frameworks, and coding conventions to use in examples.
- **Content requirements**: What sections or information to include for different types of pages.
- **Project context**: Specific details about your product, architecture, or user base that inform documentation decisions.

## Example AGENTS.md file

```md
# Documentation agent instructions

## Code examples
- Use TypeScript for all code examples. Our users are primarily TypeScript developers.
- Always include error handling in API call examples.
- Show both success and error response examples for all endpoints.
- Include import statements at the top of code examples.

## API documentation standards
- Every endpoint must document: authentication requirements, rate limits, and common error codes.
- Use real-world parameter values in examples (not foo/bar placeholders).
- Include a complete request/response cycle for each endpoint.

## Style and formatting
- Write for developers with 2-5 years of experience. Don't oversimplify, but explain non-obvious concepts.
- Use active voice and second person ("you").
- Date format: ISO 8601 (YYYY-MM-DD).
- When referencing UI elements, use bold: **Settings** button.

## What to include
- Add prerequisite sections to guides when users need API keys, environment setup, or dependencies.
- Include "Next steps" sections linking to related documentation.
- Add troubleshooting sections for common issues we see in support tickets.
```