# Source: https://github.com/mintlify/docs/blob/main/optimize/feedback.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# feedback.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)](https://github.com/ethanpalm) [ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Update plan gates (](https://github.com/mintlify/docs/commit/564f4a768a0467d9fb7545bb6232701a4b40f14a) [#6043](https://github.com/mintlify/docs/pull/6043) [)](https://github.com/mintlify/docs/commit/564f4a768a0467d9fb7545bb6232701a4b40f14a)

Open commit detailssuccess

Jun 1, 2026

[564f4a7](https://github.com/mintlify/docs/commit/564f4a768a0467d9fb7545bb6232701a4b40f14a) · Jun 1, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/optimize/feedback.mdx)

Open commit details

History

158 lines (110 loc) · 7.02 KB

## FilesExpand file tree

 main

/

# feedback.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

158 lines (110 loc) · 7.02 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/optimize/feedback.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Feedback</td></tr><tr><th>description</th><td>Monitor user satisfaction with built-in feedback widgets, page ratings, and thumbs up/down reactions to identify documentation improvement areas.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">user feedback</div></th><th><div dir="auto">thumbs rating</div></th><th><div dir="auto">contextual</div></th><th><div dir="auto">satisfaction</div></th><th><div dir="auto">agents</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

To collect and view feedback, you must enable feedback from the \[Add-ons\]([https://app.mintlify.com/products/addons](https://app.mintlify.com/products/addons)) page in your dashboard.

The [feedback](https://app.mintlify.com/products/analytics/v2/feedback) tab displays quantitative thumbs up and thumbs down votes your docs have received and any qualitative feedback that users have provided. Use this information to gauge the quality of your docs and make improvements.

View feedback on the analytics page in your dashboard.

[![Feedback tab in the Analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/feedback-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/feedback-light.png)

[![Feedback tab in the Analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/feedback-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/feedback-dark.png)

## Feedback types

Contextual and code snippet feedback are in beta. To enable them for your documentation site, \[contact our sales team\](mailto:gtm@mintlify.com).

The feedback tab displays information according to the [feedback add-ons](https://app.mintlify.com/products/addons) that you enable.

[![Feedback toggles in the Add-ons page.](https://github.com/mintlify/docs/raw/main/images/analytics/feedback-addons-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/feedback-addons-light.png)

[![Feedback toggles in the Add-ons page.](https://github.com/mintlify/docs/raw/main/images/analytics/feedback-addons-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/feedback-addons-dark.png)

- **Thumbs rating**: Simple thumbs up/down voting to gauge overall satisfaction with pages.
- **Edit suggestions**: Allow users to suggest edits to your documentation. Only available for public GitHub repositories.
- **Raise issues**: Allow users to create GitHub issues directly from your documentation. Only available for public GitHub repositories.
- **Contextual feedback**: Free form feedback about the content of a page.
- **Code snippet feedback**: Feedback specifically on code snippets.
- **Agent feedback**: Feedback submitted by third-party AI agents that access your documentation.

## Collect email addresses

Enable email collection so users can optionally provide their email address when submitting feedback.

1. Navigate to the [Add-ons](https://app.mintlify.com/products/addons) page in your dashboard.
2. Enable the **Collect reader emails** toggle under the feedback settings.
3. Optionally add a privacy disclaimer about how your team uses collected emails.

View email addresses submitted with feedback in the [feedback dashboard](https://app.mintlify.com/products/analytics/v2/feedback) alongside the feedback content.

If you disable telemetry in your \`docs.json\` file, feedback features are not available.

## Manage feedback

For contextual and code snippet feedback, you can set the status of a piece of feedback and add internal notes to track your work resolving user feedback.

### Change feedback status

Select the status beside a piece of feedback to mark it as **Pending**, **In Progress**, **Resolved**, or **Dismissed**.

Best practices for setting feedback statuses:

- **Pending**: Feedback is awaiting review.
- **In Progress**: Work is in progress to address the feedback.
- **Resolved**: You resolved the feedback.
- **Dismissed**: Feedback is irrelevant or inaccurate.

### Filter by status

Use the **Filters** menu to control which feedback displays. Clear a status to hide all feedback with that status. By default, all feedback types display.

### Filter by type

Select between **Ratings by page**, **Detailed feedback**, and **Code snippets** depending on the information you want to analyze.

- **Ratings by page**: See which pages have the most positive and negative feedback. Use this quantitative data to identify pages that users find most and least helpful.
- **Detailed feedback**: Review the open feedback users leave on pages to identify targeted improvements to specific pages. Detailed feedback only displays feedback that includes additional information. Submissions that use only the thumbs up or thumbs down rating without selecting an additional feedback option do not appear in the detailed view.
- **Code snippets**: Review the open feedback users leave on code snippets to identify targeted improvements to specific blocks of code.

### Add internal notes

Click a piece of feedback to add an internal note. These notes are only visible to people with access to your dashboard.

Use notes to add information for collaboration, link relevant support or engineering tickets, or remember any other useful information.

## Agent feedback

Agent feedback is in beta and subject to change.

When third-party AI agents fetch your documentation, they can submit structured feedback about pages they find incorrect, outdated, or difficult to use.

This feedback appears in the [feedback dashboard](https://app.mintlify.com/products/analytics/v2/feedback) identified by an **Agent** badge. Manage agent feedback the same way as human feedback. Set statuses, add internal notes, and filter feedback.

### How agent feedback works

You must enable agent feedback in your dashboard to collect it.

Once enabled, Mintlify appends an `<AgentInstructions>` block with instructions and the endpoint for submitting feedback when an agent fetches a page using Markdown export.

Agents post feedback to the endpoint with the page path and feedback text. The feedback appears in the dashboard alongside human feedback.

The feedback endpoint is always available at `https://your-domain.com/feedback` as a `POST` request, even if you don't add the instructions to the Markdown export. You can prompt agents to submit feedback manually by posting to the endpoint.

### Enable agent feedback

1. Navigate to the [Add-ons](https://app.mintlify.com/products/addons) page in your dashboard.
2. Enable the **Agent feedback** toggle. [![Agent feedback toggle in the Add-ons page.](https://github.com/mintlify/docs/raw/main/images/analytics/agent-feedback-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/agent-feedback-light.png) [![Agent feedback toggle in the Add-ons page.](https://github.com/mintlify/docs/raw/main/images/analytics/agent-feedback-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/agent-feedback-dark.png)

### Retrieve agent feedback via API

Use the [analytics feedback endpoint](https://github.com/mintlify/docs/blob/main/api/analytics/feedback) to retrieve agent feedback programmatically. Filter by `source=agent` to return only agent feedback.

Agent feedback responses include:

- `comment`: The feedback text submitted by the agent.
- `path`: The path of the page the feedback is about.

## Use feedback data

Review your feedback data to:

- **Identify successful content**: Pages with the most positive feedback show what works well in your documentation.
- **Prioritize improvements**: Pages with the most negative feedback indicate what content might need attention.
- **Take action**: Make documentation updates based on direct user feedback.