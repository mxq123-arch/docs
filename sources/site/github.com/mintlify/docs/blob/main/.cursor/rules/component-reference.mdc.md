# Source: https://github.com/mintlify/docs/blob/main/.cursor/rules/component-reference.mdc

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# component-reference.mdc

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)](https://github.com/ethanpalm) [ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Cursor rule update (](https://github.com/mintlify/docs/commit/9d22f79a440542a486be216d8cca2bdf060ac5f5) [#2612](https://github.com/mintlify/docs/pull/2612) [)](https://github.com/mintlify/docs/commit/9d22f79a440542a486be216d8cca2bdf060ac5f5)

Open commit detailssuccess

Jan 8, 2026

[9d22f79](https://github.com/mintlify/docs/commit/9d22f79a440542a486be216d8cca2bdf060ac5f5) · Jan 8, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/.cursor/rules/component-reference.mdc)

Open commit details

History

329 lines (268 loc) · 9.78 KB

## FilesExpand file tree

 main

/

# component-reference.mdc

Copy path

Top

## File metadata and controls

- Code
 
- Blame
 

329 lines (268 loc) · 9.78 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/.cursor/rules/component-reference.mdc)

Copy raw file

Download raw file

Open symbols panel

Edit and raw actions

\--- description: Reference for Mintlify MDX components with syntax examples globs: alwaysApply: true --- # Mintlify component reference docs.json schema: https://mintlify.com/docs.json ### Callout components #### Note - Additional helpful information <Note> Supplementary information that supports the main content without interrupting flow. Use for helpful context, related concepts, or non-critical details. </Note> #### Tip - Best practices and pro tips <Tip> Expert advice, shortcuts, or best practices that enhance user success. Use for optimization suggestions, time-savers, or friendly recommendations. </Tip> #### Warning - Important cautions <Warning> Critical information about potential issues, breaking changes, or destructive actions. Use sparingly and only for genuine risks. </Warning> #### Info - Neutral contextual information <Info> Background information, context, or neutral announcements. Use for prerequisites, permissions, or required setup information. </Info> #### Check - Success confirmations <Check> Positive confirmations, successful completions, or achievement indicators. Use to verify steps were completed correctly. </Check> ### Code components #### Single code block \`\`\`javascript config.js const apiConfig = { baseURL: 'https://api.example.com', timeout: 5000, headers: { 'Authorization': \`Bearer ${process.env.API\_TOKEN}\` } }; \`\`\` #### Code group with multiple languages <CodeGroup> \`\`\`javascript Node.js const response = await fetch('/api/endpoint', { headers: { Authorization: \`Bearer ${apiKey}\` } }); \`\`\` \`\`\`python Python import requests response = requests.get('/api/endpoint', headers={'Authorization': f'Bearer {api\_key}'}) \`\`\` \`\`\`curl cURL curl -X GET '/api/endpoint' \\ -H 'Authorization: Bearer YOUR\_API\_KEY' \`\`\` </CodeGroup> #### Request/Response examples <RequestExample> \`\`\`bash cURL curl -X POST 'https://api.example.com/users' \\ -H 'Content-Type: application/json' \\ -d '{"name": "John Doe", "email": "john@example.com"}' \`\`\` </RequestExample> <ResponseExample> \`\`\`json Success { "id": "user\_123", "name": "John Doe", "email": "john@example.com", "created\_at": "2024-01-15T10:30:00Z" } \`\`\` </ResponseExample> ### Structural components #### Steps for procedures <Steps> <Step title="Install dependencies"> Run \`npm install\` to install required packages. <Check> Verify installation by running \`npm list\`. </Check> </Step> <Step title="Configure environment"> Create a \`.env\` file with your API credentials. \`\`\`bash API\_KEY=your\_api\_key\_here \`\`\` <Warning> Never commit API keys to version control. </Warning> </Step> </Steps> #### Tabs for alternative content <Tabs> <Tab title="macOS"> \`\`\`bash brew install node npm install -g package-name \`\`\` </Tab> <Tab title="Windows"> \`\`\`powershell choco install nodejs npm install -g package-name \`\`\` </Tab> <Tab title="Linux"> \`\`\`bash sudo apt install nodejs npm npm install -g package-name \`\`\` </Tab> </Tabs> #### Accordions for collapsible content <AccordionGroup> <Accordion title="Troubleshooting connection issues"> - \*\*Firewall blocking\*\*: Ensure ports 80 and 443 are open - \*\*Proxy configuration\*\*: Set HTTP\_PROXY environment variable - \*\*DNS resolution\*\*: Try using 8.8.8.8 as DNS server </Accordion> <Accordion title="Advanced configuration"> \`\`\`javascript const config = { performance: { cache: true, timeout: 30000 }, security: { encryption: 'AES-256' } }; \`\`\` </Accordion> </AccordionGroup> ### API documentation components #### Parameter fields <ParamField path="user\_id" type="string" required> Unique identifier for the user. Must be a valid UUID v4 format. </ParamField> <ParamField body="email" type="string" required> User's email address. Must be valid and unique within the system. </ParamField> <ParamField query="limit" type="integer" default="10"> Maximum number of results to return. Range: 1-100. </ParamField> <ParamField header="Authorization" type="string" required> Bearer token for API authentication. Format: \`Bearer YOUR\_API\_KEY\` </ParamField> #### Response fields <ResponseField name="user\_id" type="string" required> Unique identifier assigned to the newly created user. </ResponseField> <ResponseField name="created\_at" type="timestamp"> ISO 8601 formatted timestamp of when the user was created. </ResponseField> <ResponseField name="permissions" type="array"> List of permission strings assigned to this user. </ResponseField> #### Expandable nested fields <ResponseField name="user" type="object"> Complete user object with all associated data. <Expandable title="User properties"> <ResponseField name="profile" type="object"> User profile information including personal details. <Expandable title="Profile details"> <ResponseField name="first\_name" type="string"> User's first name as entered during registration. </ResponseField> <ResponseField name="avatar\_url" type="string | null"> URL to user's profile picture. Returns null if no avatar is set. </ResponseField> </Expandable> </ResponseField> </Expandable> </ResponseField> ### Interactive components #### Cards for navigation <Card title="Getting started guide" icon="rocket" href="/quickstart"> Complete walkthrough from installation to your first API call in under 10 minutes. </Card> <CardGroup cols={2}> <Card title="Authentication" icon="key" href="/auth"> Learn how to authenticate requests using API keys or JWT tokens. </Card> <Card title="Rate limiting" icon="clock" href="/rate-limits"> Understand rate limits and best practices for high-volume usage. </Card> </CardGroup> ### Media and advanced components #### Frames for images Wrap all images in frames with descriptive alt text. <Frame> <img src="/images/dashboard.png" alt="Main dashboard showing analytics overview" /> </Frame> <Frame caption="The analytics dashboard provides real-time insights"> <img src="/images/analytics.png" alt="Analytics dashboard with charts" /> </Frame> #### Tooltips and updates <Tooltip tip="Application Programming Interface - protocols for building software"> API </Tooltip> <Update label="Version 2.1.0" description="Released March 15, 2024"> ## New features - Added bulk user import functionality - Improved error messages with actionable suggestions ## Bug fixes - Fixed pagination issue with large datasets - Resolved authentication timeout problems </Update> ## Required page structure Every documentation page must begin with YAML frontmatter: \`\`\`yaml --- title: "Clear, specific, keyword-rich title" description: "Concise description explaining page purpose and value" --- \`\`\` ## Content quality standards ### Code examples requirements - Always include complete, runnable examples that users can copy and execute - Show proper error handling and edge case management - Use realistic data instead of placeholder values (you can use \`minty\`, \`wintergreen\`, \`spearmint\` or similar for Mintlify examples) - Include expected outputs and results for verification - Test all code examples thoroughly before publishing - Specify language and include filename when relevant - Add explanatory comments for complex logic - Never include real API keys or sensitive credentials ### API documentation requirements - Document all parameters including optional ones with clear descriptions - Show both success and error response examples with realistic data - Include rate limiting information with specific limits - Provide authentication examples showing proper format - Explain all HTTP status codes and error handling - Cover complete request/response cycles - Include pagination details when applicable ### Accessibility requirements - Include descriptive alt text for all images and diagrams - Use specific, actionable link text instead of "click here" - Ensure proper heading hierarchy starting with H2 - Provide keyboard navigation considerations - Use sufficient color contrast in examples and visuals - Structure content for easy scanning with headers and lists - Use semantic HTML elements appropriately ## Component selection logic ### When to use each component - \*\*Steps\*\*: Procedures, tutorials, setup guides, and sequential instructions - \*\*Tabs\*\*: Platform-specific content, alternative approaches, or multiple installation methods - \*\*CodeGroup\*\*: Same concept demonstrated in multiple programming languages - \*\*Accordions\*\*: Supplementary information that might interrupt main flow - \*\*Cards/CardGroup\*\*: Navigation, feature overviews, and related resources - \*\*Frame\*\*: Wrap all images with descriptive captions when helpful - \*\*RequestExample/ResponseExample\*\*: Specifically for API endpoint documentation - \*\*Expandable\*\*: Nested object properties or hierarchical information - \*\*ParamField\*\*: API parameters with types and requirements - \*\*ResponseField\*\*: API response documentation with clear descriptions ### Callout selection guidelines - \*\*Note\*\*: Extra relevant information that supports main content (not crucial to task completion) - \*\*Warning\*\*: Potentially destructive actions, breaking changes, or critical cautions - \*\*Info\*\*: Required information, permissions, prerequisites, neutral announcements, background context - \*\*Tip\*\*: Opinionated best practices, expert advice, shortcuts, or friendly recommendations - \*\*Check\*\*: Success confirmations, positive completions, achievement indicators - Don't stack callouts - separate with content between them ## Component selection decision trees ### For procedures: - Use ordered lists when: Sequential simple tasks. For example "Navigate to the dashboard" or "Click Configurations" - Use <Steps> when: Sequential complex tasks that require subtasks to complete - Use <Tabs> when: Platform-specific alternatives - Use <AccordionGroup> when: Optional supplementary info ### For code examples: - Use single \`\`\` when: One language, simple example - Use <CodeGroup> when: Same concept in multiple languages - Use <RequestExample>/<ResponseExample> when: API documentation

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

39

40

41

42

43

44

45

46

47

48

49

50

51

52

53

54

55

56

57

58

59

60

61

62

63

64

65

66

67

68

69

70

71

72

73

74

75

76

77

78

79

80

81

82

83

84

85

86

87

88

89

90

91

92

93

94

95

96

97

98

99

100

101

102

103

104

105

106

107

108

109

110

111

112

113

114

115

116

117

118

119

120

121

122

123

124

125

126

127

128

129

130

131

132

133

134

135

136

137

138

139

140

141

142

143

144

145

146

147

148

149

150

151

152

153

154

155

256

257

258

259

260

261

262

263

264

265

266

267

268

269

270

271

272

273

274

275

276

277

278

279

280

281

282

283

284

285

286

287

288

289

290

291

292

293

294

295

296

297

298

299

300

301

302

303

304

305

306

307

308

309

310

311

312

313

314

315

316

317

318

319

320

321

322

323

324

325

326

327

328

329

\---

description: Reference for Mintlify MDX components with syntax examples

globs:

alwaysApply: true

\---

\# Mintlify component reference

docs.json schema: https://mintlify.com/docs.json

\### Callout components

\#### Note - Additional helpful information

<Note>

Supplementary information that supports the main content without interrupting flow. Use for helpful context, related concepts, or non-critical details.

</Note>

\#### Tip - Best practices and pro tips

<Tip>

Expert advice, shortcuts, or best practices that enhance user success. Use for optimization suggestions, time-savers, or friendly recommendations.

</Tip>

\#### Warning - Important cautions

<Warning>

Critical information about potential issues, breaking changes, or destructive actions. Use sparingly and only for genuine risks.

</Warning>

\#### Info - Neutral contextual information

<Info>

Background information, context, or neutral announcements. Use for prerequisites, permissions, or required setup information.

</Info>

\#### Check - Success confirmations

<Check>

Positive confirmations, successful completions, or achievement indicators. Use to verify steps were completed correctly.

</Check>

\### Code components

\#### Single code block

\`\`\`javascript config.js

const apiConfig = {

baseURL: 'https://api.example.com',

timeout: 5000,

headers: {

'Authorization': \`Bearer ${process.env.API\_TOKEN}\`

}

};

\`\`\`

\#### Code group with multiple languages

<CodeGroup>

\`\`\`javascript Node.js

const response = await fetch('/api/endpoint', {

headers: { Authorization: \`Bearer ${apiKey}\` }

});

\`\`\`

\`\`\`python Python

import requests

response = requests.get('/api/endpoint',

headers={'Authorization': f'Bearer {api\_key}'})

\`\`\`

\`\`\`curl cURL

curl -X GET '/api/endpoint' \\

\-H 'Authorization: Bearer YOUR\_API\_KEY'

\`\`\`

</CodeGroup>

\#### Request/Response examples

<RequestExample>

\`\`\`bash cURL

curl -X POST 'https://api.example.com/users' \\

\-H 'Content-Type: application/json' \\

\-d '{"name": "John Doe", "email": "john@example.com"}'

\`\`\`

</RequestExample>

<ResponseExample>

\`\`\`json Success

{

"id": "user\_123",

"name": "John Doe",

"email": "john@example.com",

"created\_at": "2024-01-15T10:30:00Z"

}

\`\`\`

</ResponseExample>

\### Structural components

\#### Steps for procedures

<Steps>

<Step title="Install dependencies">

Run \`npm install\` to install required packages.

<Check>

Verify installation by running \`npm list\`.

</Check>

</Step>

<Step title="Configure environment">

Create a \`.env\` file with your API credentials.

\`\`\`bash

API\_KEY=your\_api\_key\_here

\`\`\`

<Warning>

Never commit API keys to version control.

</Warning>

</Step>

</Steps>

\#### Tabs for alternative content

<Tabs>

<Tab title="macOS">

\`\`\`bash

brew install node

npm install -g package-name

\`\`\`

</Tab>

<Tab title="Windows">

\`\`\`powershell

choco install nodejs

npm install -g package-name

\`\`\`

</Tab>

<Tab title="Linux">

\`\`\`bash

sudo apt install nodejs npm

npm install -g package-name

\`\`\`

</Tab>

</Tabs>

\#### Accordions for collapsible content

<AccordionGroup>

<Accordion title="Troubleshooting connection issues">

\- \*\*Firewall blocking\*\*: Ensure ports 80 and 443 are open

\- \*\*Proxy configuration\*\*: Set HTTP\_PROXY environment variable

\- \*\*DNS resolution\*\*: Try using 8.8.8.8 as DNS server

</Accordion>

<Accordion title="Advanced configuration">

\`\`\`javascript

const config = {

performance: { cache: true, timeout: 30000 },

security: { encryption: 'AES-256' }

};

\`\`\`

</Accordion>

</AccordionGroup>

Every documentation page must begin with YAML frontmatter:

\`\`\`yaml

\---

title: "Clear, specific, keyword-rich title"

description: "Concise description explaining page purpose and value"

\---

\`\`\`

\## Content quality standards

\### Code examples requirements

\- Always include complete, runnable examples that users can copy and execute

\- Show proper error handling and edge case management

\- Use realistic data instead of placeholder values (you can use \`minty\`, \`wintergreen\`, \`spearmint\` or similar for Mintlify examples)

\- Include expected outputs and results for verification

\- Test all code examples thoroughly before publishing

\- Specify language and include filename when relevant

\- Add explanatory comments for complex logic

\- Never include real API keys or sensitive credentials

\### API documentation requirements

\- Document all parameters including optional ones with clear descriptions

\- Show both success and error response examples with realistic data

\- Include rate limiting information with specific limits

\- Provide authentication examples showing proper format

\- Explain all HTTP status codes and error handling

\- Cover complete request/response cycles

\- Include pagination details when applicable

\### Accessibility requirements

\- Include descriptive alt text for all images and diagrams

\- Use specific, actionable link text instead of "click here"

\- Ensure proper heading hierarchy starting with H2

\- Provide keyboard navigation considerations

\- Use sufficient color contrast in examples and visuals

\- Structure content for easy scanning with headers and lists

\- Use semantic HTML elements appropriately

\## Component selection logic

\### When to use each component

\- \*\*Steps\*\*: Procedures, tutorials, setup guides, and sequential instructions

\- \*\*Tabs\*\*: Platform-specific content, alternative approaches, or multiple installation methods

\- \*\*CodeGroup\*\*: Same concept demonstrated in multiple programming languages

\- \*\*Accordions\*\*: Supplementary information that might interrupt main flow

\- \*\*Cards/CardGroup\*\*: Navigation, feature overviews, and related resources

\- \*\*Frame\*\*: Wrap all images with descriptive captions when helpful

\- \*\*RequestExample/ResponseExample\*\*: Specifically for API endpoint documentation

\- \*\*Expandable\*\*: Nested object properties or hierarchical information

\- \*\*ParamField\*\*: API parameters with types and requirements

\- \*\*ResponseField\*\*: API response documentation with clear descriptions

\### Callout selection guidelines

\- \*\*Note\*\*: Extra relevant information that supports main content (not crucial to task completion)

\- \*\*Warning\*\*: Potentially destructive actions, breaking changes, or critical cautions

\- \*\*Info\*\*: Required information, permissions, prerequisites, neutral announcements, background context

\- \*\*Tip\*\*: Opinionated best practices, expert advice, shortcuts, or friendly recommendations

\- \*\*Check\*\*: Success confirmations, positive completions, achievement indicators

\- Don't stack callouts - separate with content between them

\## Component selection decision trees

\### For procedures:

\- Use ordered lists when: Sequential simple tasks. For example "Navigate to the dashboard" or "Click Configurations"

\- Use <Steps> when: Sequential complex tasks that require subtasks to complete

\- Use <Tabs> when: Platform-specific alternatives

\- Use <AccordionGroup> when: Optional supplementary info

\### For code examples:

\- Use single \`\`\` when: One language, simple example

\- Use <CodeGroup> when: Same concept in multiple languages

\- Use <RequestExample>/<ResponseExample> when: API documentation