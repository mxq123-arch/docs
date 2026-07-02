# Source: https://github.com/mintlify/docs/blob/main/optimize/analytics.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# analytics.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/optimize/analytics.mdx)

History

171 lines (115 loc) · 8.26 KB

 main

/

# analytics.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

171 lines (115 loc) · 8.26 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/optimize/analytics.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Analytics</td></tr><tr><th>description</th><td>Track documentation analytics in the Mintlify dashboard to understand page views, visitor trends, search queries, and content effectiveness.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">analytics</div></th><th><div dir="auto">metrics</div></th><th><div dir="auto">page views</div></th><th><div dir="auto">traffic</div></th><th><div dir="auto">trends</div></th><th><div dir="auto">insights</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

The [analytics](https://app.mintlify.com/products/analytics/v2/) page in your dashboard shows data about visitors to your docs, how they interact with the assistant, what they search for, and their feedback. Use this information to identify which pages are most valuable to your users and track trends over time.

## Filter by AI or human visitors

Filter your analytics data by traffic source to analyze AI agent traffic separately from human visitors.

[![The traffic source filter on the analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/traffic-filter-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/traffic-filter-light.png)

[![The traffic source filter on the analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/traffic-filter-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/traffic-filter-dark.png)

When you change the traffic source, the analytics page only displays relevant metrics to that traffic source. For AI traffic, the analytics page displays visitors and MCP searches. For human traffic, the analytics page displays visitors, page views, assistant usage, searches, and feedback.

## Filter time period

Use the range selector to adjust the time period for displayed data.

[![The range selector expanded to show options for viewing different time periods of data.](https://github.com/mintlify/docs/raw/main/images/analytics/range-selector-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/range-selector-light.png)

[![The range selector expanded to show options for viewing different time periods of data.](https://github.com/mintlify/docs/raw/main/images/analytics/range-selector-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/range-selector-dark.png)

## Visitors

The visitors tab displays a bar chart of visitors over time, a list of popular pages, and referral sources.

Review your visitors analytics to:

- **Monitor traffic trends**: Observe changes in traffic after updates or new content to understand the impact of your changes.
- **Identify popular pages**: Use popular pages to understand what content is most important to your users so that you can make sure it is up to date and comprehensive.
- **Track traffic sources**: Understand where your users are coming from to help you optimize your content for the right audience.

### Agent visitors

Mintlify identifies agent visitors by IP address and user agent. The agent visitor count approximates distinct sources of AI traffic rather than individual agent sessions or conversations. Multiple requests from the same IP address count as one visitor.

When viewing agent traffic, top agents replaces referrals in the visitors tab. Top agents shows which AI agents are visiting your documentation. Use this information to help determine:

- **AI agent distribution**: See which AI platforms are accessing your docs to learn which tools your users prefer.
- **Integration opportunities**: Identify which AI platforms to prioritize for optimization and testing.
- **AI traffic patterns**: Monitor which agents are most active and how their usage changes over time.

## Views

The views tab displays a bar chart of page views over time and a list of your top pages by view count.

Review your page views analytics to:

- **Monitor content engagement**: Track total page views to understand overall documentation usage and identify trends.
- **Identify top pages**: See which pages receive the most views to prioritize updates and ensure high-traffic content stays accurate.

## Assistant

The assistant tab displays a bar chart of assistant usage over time, a list of categories, and chat history.

Review your assistant analytics to:

- **Monitor assistant usage**: Observe changes in assistant usage to understand how your users engage with your content.
- **Identify frequent categories**: Use high occurrence categories to understand what topics are most important to your users. Identify gaps in coverage and prioritize content updates.
- **Review chat history**: Get detailed high intent data about how your users think about your product by reviewing their chat history with the assistant. See what terms they use, what they need help with, and what tasks they try to accomplish.

### Categories

The categories tab uses LLMs to automatically group conversations by topic or theme.

[![The categories tab in the assistant analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/categories-light.png)](https://github.com/mintlify/docs/blob/main/images/analytics/categories-light.png)

[![The categories tab in the assistant analytics page.](https://github.com/mintlify/docs/raw/main/images/analytics/categories-dark.png)](https://github.com/mintlify/docs/blob/main/images/analytics/categories-dark.png)

Use categories to identify common topics, patterns in user needs and behavior, and areas where documentation might need expansion or clarification.

Click a category row to expand it and view related conversations grouped under that category.

Click an individual conversation to view the complete chat thread, including the user's question, the assistant's response, and any sources cited.

### Chat history

The chat history tab displays chronological records of all assistant conversations.

Click any message to view the complete chat thread, including the user's question, the assistant's response, and any sources cited.

## Searches

The Searches metric is only available when viewing human traffic.

The searches tab displays a bar chart of searches over time and specific queries.

Review your searches analytics to:

- **Monitor search trends**: Observe changes in search queries to understand how your users are finding your content and what topics they want information on.
- **Identify frequent queries**: Use frequent queries to understand what topics are most important to your users. Identify gaps in coverage and prioritize content updates.
- **Identify low click through rates**: Click through rates (CTR) show how many users click a search result after typing in a query. Low CTR can indicate that the search results are not relevant to users' queries. If you have frequent search terms with low CTR, consider improving the relevance of search results by adding keywords and updating your content.

## MCP searches

The MCP Searches metric is only available when viewing AI traffic.

The MCP searches tab displays AI agent search interactions through the Model Context Protocol (MCP). This metric counts calls to your MCP server's search tool. It reflects agents that users connected to your MCP server and then issued a search, not general AI crawler traffic to your docs pages.

Review your MCP searches analytics to:

- **Monitor AI search activity**: Track how frequently AI agents search your documentation and identify trends in AI-driven queries.
- **Identify common AI queries**: Understand what information AI agents are looking for to optimize your content for AI consumption.
- **Improve AI discoverability**: Use frequent MCP search queries to identify gaps in your documentation that AI agents struggle to find answers for.

## Feedback

The feedback tab displays a bar chart of feedback over time and specific feedback items.

See [Feedback](https://github.com/mintlify/docs/blob/main/optimize/feedback) for more information on using feedback data to improve your content.

## Export analytics

Export any analytics tab to CSV for deeper analysis, reporting, or archival. Exports respect the current traffic source and time range filters.

1. Navigate to the [analytics](https://app.mintlify.com/products/analytics/) page of your dashboard.
2. Click the tab you want to export.
3. Optionally, adjust the traffic source and time range to narrow down the data you want to export.
4. Click **Export to CSV**.
5. Mintlify sends you an email with a download link when the export is ready.

### Assistant exports

Assistant exports include the queries, responses, sources, and a `resolutionStatus` column that indicates whether the assistant successfully answered each question (`answered` or `unanswered`). Use the `resolutionStatus` column to identify documentation gaps surfaced by questions the assistant could not resolve.

Sample analysis prompts for assistant exports:

- List any queries that had no sources cited.
- Find patterns in unsuccessful interactions.
- Group unanswered queries by topic to prioritize content updates.