# Source: https://github.com/mintlify/docs/blob/main/agent/effective-prompts.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# effective-prompts.mdx

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

[docs: replace dashboard.mintlify.com with app.mintlify.com (](https://github.com/mintlify/docs/commit/6bb14aa0616706693af60ac655fc16a107935ab4) [#5990](https://github.com/mintlify/docs/pull/5990) [)](https://github.com/mintlify/docs/commit/6bb14aa0616706693af60ac655fc16a107935ab4)

Open commit detailssuccess

May 26, 2026

[6bb14aa](https://github.com/mintlify/docs/commit/6bb14aa0616706693af60ac655fc16a107935ab4) · May 26, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/agent/effective-prompts.mdx)

Open commit details

History

34 lines (21 loc) · 2.36 KB

## FilesExpand file tree

 main

/

# effective-prompts.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

34 lines (21 loc) · 2.36 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/agent/effective-prompts.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Write effective prompts</td></tr><tr><th>description</th><td>Write clear, specific prompts to get better results from the Mintlify agent, with examples of effective instructions and tips for common patterns.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">prompts</div></th><th><div dir="auto">agent prompts</div></th><th><div dir="auto">effective prompting</div></th><th><div dir="auto">agent usage</div></th></tr></tbody></table></td></tr></tbody></table>

Think of the agent as a helpful assistant that needs your guidance to complete tasks. Give it clear instructions and context. More focused tasks are easier to complete, so break down complex projects into smaller steps.

## Make prompts specific and outcome-focused

Generic prompts like `@mintlify Improve the onboarding page` apply general best practices, but may not improve content in the specific way that you were picturing.

Try prompts based on outcomes you want your users to achieve or problems that they encounter.

- `@mintlify A lot of users have trouble installing the CLI. Review the onboarding page and update the docs so that users can easily install the CLI`
- `@mintlify Developers keep getting 401 errors when following our authentication guide. Review the auth docs and add clearer examples showing how to properly format the API key`

## Use broad prompts for maintenance tasks

Use broad prompts for general content maintenance like fixing typos, updating redirects, or renaming a feature throughout your docs.

- `@mintlify Find and fix all typos in the docs`
- `@mintlify change all unordered lists to use * instead of -`

## Specify a domain name for multi-site organizations

If you have multiple documentation sites, include the `subdomain` parameter in your message to specify which documentation set the agent should work on.

To find your domain name, look at your dashboard URL for the documentation set you want to update. The domain name is the last part after your organization name. For example, if your dashboard URL is `https://app.mintlify.com/org-name/domain-name`, your domain name is `domain-name`.

Use the format `@mintlify subdomain=<your-domain-name> <your-prompt>` to prompt the agent to work on a specific documentation set.

- `@mintlify subdomain=public-docs Add a new section to the quickstart about inviting collaborators based on this PR`: Prompts the agent to update the quickstart only on the `public-docs` site.
- `@mintlify subdomain=customer-docs Update the auth docs for the new authentication method`: Prompts the agent to update the auth docs only on the `customer-docs` site.