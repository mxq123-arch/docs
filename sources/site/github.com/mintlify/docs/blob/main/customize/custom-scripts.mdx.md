# Source: https://github.com/mintlify/docs/blob/main/customize/custom-scripts.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# custom-scripts.mdx

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

[Feedback resolution 2026 06 08 (](https://github.com/mintlify/docs/commit/7662f8fb2a071ff3768c5f533afe85c813bdbb93) [#6123](https://github.com/mintlify/docs/pull/6123) [)](https://github.com/mintlify/docs/commit/7662f8fb2a071ff3768c5f533afe85c813bdbb93)

Open commit detailssuccess

Jun 9, 2026

[7662f8f](https://github.com/mintlify/docs/commit/7662f8fb2a071ff3768c5f533afe85c813bdbb93) · Jun 9, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/customize/custom-scripts.mdx)

Open commit details

History

364 lines (323 loc) · 18.5 KB

## FilesExpand file tree

 main

/

# custom-scripts.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

364 lines (323 loc) · 18.5 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/customize/custom-scripts.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Custom scripts</td></tr><tr><th>description</th><td>Add custom JavaScript and CSS scripts to your documentation site for analytics, widgets, styling overrides, and third-party integrations.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">CSS</div></th><th><div dir="auto">JavaScript</div></th><th><div dir="auto">Tailwind CSS</div></th><th><div dir="auto">style customization</div></th></tr></tbody></table></td></tr></tbody></table>

Use CSS to style HTML elements or add custom CSS and JavaScript to fully customize the look and feel of your documentation.

## Style with Tailwind CSS

Use Tailwind CSS v3 to style HTML elements. You can control layout, spacing, colors, and other visual properties. Some common classes are:

- `w-full` - Full width
- `aspect-video` - 16:9 aspect ratio
- `rounded-xl` - Large rounded corners
- `block`, `hidden` - Display control
- `dark:hidden`, `dark:block` - Dark mode visibility

Tailwind CSS arbitrary values are not supported. For custom values, use the `style` prop instead.

```html
<img style={{ width: '350px', margin: '12px auto' }} src="/path/image.jpg" />
```

Using the \`style\` prop can cause a layout shift on page load, especially on custom mode pages. Use Tailwind CSS classes or custom CSS files instead to avoid shifts or flickering.

## Add custom CSS

Add CSS files to your repository to apply their defined class names and make them available in all of your MDX files.

The references and styling of common elements are subject to change. Use custom styling with caution since breaking changes may occur in future updates.

For example, you can add the following `style.css` file to customize the styling of the navbar and footer.

```css
#navbar {
  background: #fffff2;
  padding: 1rem;
}

footer {
  margin-top: 2rem;
}
```

Mintlify exposes two types of CSS targeting hooks:

- **ID selectors**: unique page-level elements targeted with `#value { }` in CSS
- **Element selectors**: component and layout elements targeted with `value { }` in CSS (no `#` or `.` prefix)

Use inspect element to find references to elements you're looking to customize.

### ID selectors

Each ID appears once per page. Use these as `#value` in CSS. For example, `#navbar { background: red; }`.

\- \`#body-content\` — Outermost wrapper for the page body. - \`#content-area\` — Primary content area, excluding the sidebar and table of contents. - \`#content\` — Inner content element within the content area. - \`#header\` — Page-level header element. - \`#banner\` — Announcement banner displayed above the navbar. - \`#footer\` — Page footer. Also targetable as an element selector: \`footer\`. - \`#page-title\` — The \`

# \` heading at the top of each page. - \`#pagination\` — Bottom pagination bar with previous and next page links. - \`#panel\` — Floating panel overlay. Also targetable as an element selector: \`panel\`. - \`#background-color\` — Page background color element. - \`#navbar\` — Top navigation bar. - \`#topbar-cta-button\` — Call-to-action button in the topbar. - \`#mobile-nav\` — Mobile navigation overlay. - \`#mobile-nav-content\` — Content area within the mobile navigation overlay. - \`#sidebar\` — The sidebar navigation panel. - \`#sidebar-content\` — Scrollable content area within the sidebar. - \`#table-of-contents\` — Table of contents panel on the right side of the page. - \`#table-of-contents-layout\` — Layout wrapper for the table of contents. - \`#table-of-contents-content\` — Scrollable content within the table of contents. - \`#search-bar-entry\` — Search bar trigger in the topbar. - \`#search-bar-entry-mobile\` — Search bar trigger on mobile. - \`#search-input\` — Text input field within the search modal. - \`#assistant-entry\` — AI assistant button in the topbar. - \`#assistant-entry-mobile\` — AI assistant button on mobile. - \`#chat-assistant-sheet\` — AI assistant chat panel. - \`#chat-assistant-textarea\` — Text input within the AI assistant panel. - \`#request-example\` — Request example panel in the API playground. - \`#response-example\` — Response example panel in the API playground. - \`#api-playground-input\` — Input section of the API playground. - \`#endpoints-menu-trigger\` — Button that opens the endpoint selector dropdown. - \`#ask-assistant-code-block-button\` — "Ask Assistant" button that appears on code blocks. - \`#code-snippet-feedback-button\` — Feedback button on code snippets. - \`#code-snippet-feedback-textarea\` — Text area within the code snippet feedback form. - \`#feedback-thumbs-up\` — Thumbs-up feedback button at the bottom of a page. - \`#feedback-thumbs-down\` — Thumbs-down feedback button at the bottom of a page. - \`#feedback-form\` — Feedback form shown after a thumbs-down response. - \`#feedback-form-input\` — Text input within the feedback form. - \`#feedback-form-cancel\` — Cancel button within the feedback form. - \`#feedback-form-submit\` — Submit button within the feedback form. - \`#page-context-menu\` — Contextual options menu for the current page. - \`#page-context-menu-button\` — Button that triggers the page context menu. - \`#localization-select-trigger\` — Button that opens the language selector. - \`#localization-select-content\` — Dropdown content of the language selector. - \`#localization-select-item\` — Individual language option within the selector. - \`#changelog-filters\` — Filter controls on a changelog page. - \`#changelog-filters-content\` — Content area within the changelog filter panel. - \`#multi-view-dropdown\` — Dropdown for switching between documentation views. - \`#text-selection-tooltip\` — Tooltip that appears when text is selected on a page. - \`#text-selection-tooltip-button\` — Action button within the text selection tooltip.

### Element selectors

Multiple instances of these elements can appear on a page. Use these as `value` in CSS. For example, `accordion { border: 1px solid red; }`.

\- \`accordion\` — Collapsible accordion item. - \`accordion-group\` — Wrapper grouping multiple accordions. - \`callout\` — Callout block (Note, Warning, Tip, etc.). - \`card\` — Individual card element. - \`card-group\` — Wrapper grouping multiple cards. Deprecated in favor of \`columns\`, but preserved for backward compatibility. - \`columns\` — Multi-column layout wrapper. - \`code-block\` — Code block element. - \`code-block-icon\` — Icon displayed in a code block header. - \`code-group\` — Tabbed group of code blocks. - \`expandable\` — Expandable section element. - \`frame\` — Frame wrapper for images or embedded content. - \`icon\` — Inline icon element. - \`mermaid\` — Mermaid diagram wrapper. - \`step\` — Individual step within a steps sequence. - \`steps\` — Numbered steps container. - \`tab-icon\` — Icon displayed within a tab. - \`tabs\` — Tabbed content container. - \`tile\` — Tile component element. - \`tooltip\` — Tooltip element. - \`update\` — Changelog update entry. - \`mdx-content\` — Rendered MDX content area. - \`panel\` — Floating panel component. Also targetable as an ID selector: \`#panel\`. - \`eyebrow\` — Small label displayed above a page title. - \`link\` — Anchor link element. - \`breadcrumb-list\` — Breadcrumb navigation list. - \`breadcrumb-item\` — Individual breadcrumb item. - \`nav-logo\` — Logo in the navigation bar. - \`navbar-link\` — Link element within the navigation bar. - \`nav-anchors\` — Container for anchor links in the topbar. - \`nav-anchor\` — Individual anchor link in the topbar. - \`nav-tabs\` — Tab bar in the top navigation. - \`nav-tabs-item\` — Individual tab item in the top navigation tab bar. - \`mobile-nav-tabs-item\` — Tab item in the mobile navigation tab bar. - \`topbar-right-container\` — Right section of the topbar. - \`nav-tag-pill\` — Tag pill shown in the navigation. - \`nav-tag-pill-text\` — Text within a navigation tag pill. - \`nav-dropdown-trigger\` — Button that opens a navigation dropdown. - \`nav-dropdown-content\` — Content container for a navigation dropdown. - \`nav-dropdown-item\` — Individual item within a navigation dropdown. - \`nav-dropdown-item-text-container\` — Text wrapper within a dropdown item. - \`nav-dropdown-item-title\` — Title text within a dropdown item. - \`nav-dropdown-item-description\` — Description text within a dropdown item. - \`nav-dropdown-item-icon\` — Icon within a dropdown item. - \`nav-dropdown-products-selector-trigger\` — Button that opens the products selector dropdown. - \`nav-dropdown-products-selector-content\` — Content container for the products selector. - \`nav-dropdown-products-selector-item\` — Individual product in the selector. - \`nav-dropdown-products-selector-item-title\` — Title of a product selector item. - \`nav-dropdown-products-selector-item-description\` — Description of a product selector item. - \`nav-dropdown-products-selector-item-icon\` — Icon of a product selector item. - \`sidebar-group\` — Group of related sidebar links. - \`sidebar-group-icon\` — Icon for a sidebar group. - \`sidebar-group-header\` — Header label for a sidebar group. - \`sidebar-title\` — Top-level title in the sidebar. - \`sidebar-nav-group-divider\` — Divider between sidebar navigation groups. - \`toc\` — Table of contents container. - \`toc-item\` — Individual heading entry in the table of contents. - \`footer\` — Standard page footer. Also targetable as an ID selector: \`#footer\`. - \`advanced-footer\` — Extended footer with additional columns or content. - \`pagination-prev\` — Previous page link in the pagination bar. - \`pagination-next\` — Next page link in the pagination bar. - \`pagination-title\` — Page title shown in the pagination bar. - \`api-section\` — Full section for a single API endpoint. - \`api-section-heading\` — Heading area for an API endpoint section. - \`api-section-heading-title\` — Title within an API endpoint section heading. - \`api-section-heading-subtitle\` — Subtitle within an API endpoint section heading. - \`field\` — Parameter or property field in the API reference. - \`option-dropdown\` — Dropdown for selecting between API options. - \`tryit-button\` — "Try it" button that opens the API playground. - \`method-pill\` — HTTP method badge (GET, POST, etc.) on an endpoint. - \`method-nav-pill\` — HTTP method badge shown in the sidebar navigation. - \`prompt\` — Prompt component in the API reference. - \`chat-assistant-sheet\` — AI assistant panel container. - \`chat-assistant-sheet-header\` — Header of the AI assistant panel. - \`chat-assistant-sheet-content\` — Content area of the AI assistant panel. - \`chat-assistant-input\` — Text input within the AI assistant panel. - \`chat-assistant-floating-input\` — Floating input variant of the AI assistant. - \`chat-assistant-send-button\` — Send button in the AI assistant panel. - \`chat-assistant-disclaimer-text\` — Disclaimer text displayed in the AI assistant panel. - \`chat-assistant-payload-item\` — Individual message or result item in the assistant panel. - \`starter-question-text\` — Suggested starter question shown in an empty assistant panel. - \`feedback-toolbar\` — Toolbar containing page feedback controls. - \`contextual-feedback-container\` — Container for contextual inline feedback. - \`contextual-feedback-form\` — Inline contextual feedback form. - \`contextual-feedback-form-title\` — Title of the contextual feedback form. - \`contextual-feedback-input\` — Text input within the contextual feedback form. - \`contextual-feedback-button\` — Action button within the contextual feedback form. - \`contextual-feedback-form-submit-button\` — Submit button for the contextual feedback form. - \`code-snippet-feedback-popover-content\` — Popover content for code snippet feedback. - \`code-snippet-feedback-form\` — Feedback form for a code snippet. - \`code-snippet-feedback-textarea\` — Text area within the code snippet feedback form. - \`code-snippet-feedback-form-title\` — Title of the code snippet feedback form. - \`code-snippet-feedback-form-description\` — Description text in the code snippet feedback form. - \`code-snippet-feedback-form-submit-button\` — Submit button for the code snippet feedback form. - \`login-link\` — Link that initiates the login flow. - \`logout-link\` — Link that initiates the logout flow. - \`multi-view-item\` — Individual view option in a multi-view switcher. - \`multi-view-dropdown\` — Dropdown for selecting between multiple views. - \`multi-view-dropdown-trigger\` — Button that opens the multi-view dropdown. - \`multi-view-dropdown-content\` — Content area of the multi-view dropdown. - \`multi-view-dropdown-item\` — Individual item within the multi-view dropdown. - \`directory\` — Root container for a directory page. - \`directory-group\` — Group of related pages within a directory. - \`directory-page\` — Individual page entry in a directory. - \`directory-card\` — Card-style page entry in a directory. - \`not-found-container\` — Root container of the 404 page. - \`not-found-status-code\` — Status code display on the 404 page. - \`not-found-title\` — Title heading on the 404 page. - \`not-found-description\` — Description text on the 404 page. - \`not-found-recommended-pages-list\` — List of recommended pages shown on the 404 page. - \`not-found-recommended-page-link\` — Individual link in the recommended pages list. - \`color\` — Color swatch element. - \`color-row\` — Row grouping color swatches. - \`color-item\` — Individual color item within a color row. - \`tree\` — File tree container. - \`tree-folder\` — Folder entry within a file tree. - \`tree-file\` — File entry within a file tree. Some elements expose data attributes you can use as CSS selectors.

```
Active state (`data-active`):

- `nav-dropdown-item[data-active]` — Active item in a nav dropdown.
- `mobile-nav-tabs-item[data-active]` — Active tab in the mobile nav.
- `sidebar-group[data-active]` — Active sidebar group.
- `#sidebar-content li[data-active]` — Active sidebar link.
- `.nav-tabs-item[data-active]` — Active top nav tab. Only applies to simple tabs; tabs with dropdown menus do not receive `data-active`. Note the leading `.`: this targets a class on a standard `<a>` element, unlike most other components which use custom element names.
- `toc-item[data-active]` — Active table of contents item.
- `toc-item[data-active-deepest]` — Deepest active table of contents item. Only present on the exact heading currently in view, unlike `data-active` which is also set on its parent headings.

Component name (`data-component-name`):

Use `data-component-name` to target specific UI components with a stable selector that persists if internal class names change.

- `[data-component-name="mermaid-container"]` — Mermaid diagram wrapper, including the zoom controls overlay.
- `[data-component-name="mermaid-controls-wrapper"]` — Mermaid zoom and pan controls.
- `[data-component-name="primary-header-button"]` — Primary header button. Sequoia theme only.
- `[data-component-name="theme-toggle"]` — Theme toggle.

Component part (`data-component-part`):

Use `data-component-part` to target sub-elements within a component.

- `[data-component-part="contact-support-button"]` — The `<a>` wrapper around the contact support link in the assistant panel.
- `[data-component-part="contact-support-icon"]` — The `<span>` wrapping the icon.
- `[data-component-part="contact-support-text"]` — The `<p>` element containing the label.

Badge attributes:

- `[data-badge]` — Any badge element.
- `[data-badge][data-color="blue"]` — Badge filtered by color.
- `[data-badge][data-size="sm"]` — Badge filtered by size.

Current path (`data-current-path`):

Use `data-current-path` to style custom CSS on specific pages or subpaths.

- `html[data-current-path="/"]` — Matches the root page.
- `html[data-current-path="/quickstart"]` — Matches a specific page.
- `html[data-current-path^="/api-reference/"]` — Matches any page under a section.
```

## Custom JavaScript

Custom JS lets you add custom executable code globally. It is the equivalent of adding a `<script>` tag with JS code into every page.

Mintlify includes any `.js` file inside your content directory on every page of your documentation site. Custom JavaScript files run after the page becomes interactive. You cannot scope them to specific pages. For example, you can add the following `ga.js` file to enable [Google Analytics](https://marketingplatform.google.com/about/analytics) across the entire documentation.

```js
window.dataLayer = window.dataLayer || [];
function gtag() {
  dataLayer.push(arguments);
}
gtag('js', new Date());

gtag('config', 'TAG_ID');
```

Use with caution to avoid introducing security vulnerabilities.