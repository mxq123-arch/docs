# Source: https://github.com/mintlify/docs/blob/main/customize/fonts.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# fonts.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/customize/fonts.mdx)

History

151 lines (128 loc) · 4.98 KB

## FilesExpand file tree

 main

/

# fonts.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

151 lines (128 loc) · 4.98 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/customize/fonts.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Fonts</td></tr><tr><th>description</th><td>Customize typography on your documentation site with Google Fonts or self-hosted font files for headings, body text, and code blocks.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">Google Fonts</div></th><th><div dir="auto">local fonts</div></th><th><div dir="auto">custom typography</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Set a custom font for your entire site or separately for headings and body text. Use Google Fonts, local font files, or externally hosted fonts. The default font varies by theme.

Configure fonts with the [fonts property](https://github.com/mintlify/docs/blob/main/organize/settings-appearance#fonts) in your `docs.json`.

## Google Fonts

Mintlify automatically loads [Google Fonts](https://fonts.google.com) when you specify a font family name in your `docs.json`.

```json
"fonts": {
  "family": "Inter"
}
```

## Local fonts

To use local fonts, place your font files in your project directory and reference them in your `docs.json` configuration.

### Set up local fonts

For example, create a \`fonts\` directory and add your font files:

```
your-project/
├── fonts/
│   ├── InterDisplay-Regular.woff2
│   └── InterDisplay-Bold.woff2
├── docs.json
└── ...
```

Reference your local fonts using relative paths from your project root:

```json
{
  "fonts": {
    "family": "InterDisplay",
    "source": "/fonts/InterDisplay-Regular.woff2",
    "format": "woff2",
    "weight": 400
  }
}
```

### Local fonts for headings and body

Configure separate local fonts for headings and body text in your `docs.json`:

```json
{
  "fonts": {
    "heading": {
      "family": "InterDisplay",
      "source": "/fonts/InterDisplay-Bold.woff2",
      "format": "woff2",
      "weight": 700
    },
    "body": {
      "family": "InterDisplay",
      "source": "/fonts/InterDisplay-Regular.woff2",
      "format": "woff2",
      "weight": 400
    }
  }
}
```

## Externally hosted fonts

Use externally hosted fonts by referencing a font source URL in your `docs.json`:

```json
{
  "fonts": {
    "family": "Hubot Sans",
    "source": "https://mintlify-assets.b-cdn.net/fonts/Hubot-Sans.woff2",
    "format": "woff2",
    "weight": 400
  }
}
```

## Font configuration reference

Font configuration for your documentation. Font family name, such as "Inter" or "Playfair Display." Font weight, such as 400 or 700. Variable fonts support precise weights such as 550. URL to your font source, such as \`[https://mintlify-assets.b-cdn.net/fonts/Hubot-Sans.woff2\`](https://mintlify-assets.b-cdn.net/fonts/Hubot-Sans.woff2`), or path to your local font file, such as \`/assets/fonts/InterDisplay.woff2\`. Google Fonts are loaded automatically when you specify a Google Font \`family\` name, so no source URL is needed. Font file format. Required when using the \`source\` field. Override font settings specifically for headings.

```
  <Expandable title="Heading">
    <ResponseField name="family" type="string" required>
      Font family name for headings.
    </ResponseField>
    <ResponseField name="weight" type="number">
      Font weight for headings.
    </ResponseField>
    <ResponseField name="source" type="string (uri)">
      URL to your font source, such as `https://mintlify-assets.b-cdn.net/fonts/Hubot-Sans.woff2`, or path to your local font file for headings. Google Fonts are loaded automatically when you specify a Google Font `family` name, so no source URL is needed.
    </ResponseField>
    <ResponseField name="format" type="'woff' | 'woff2'">
      Font file format for headings. Required when using the `source` field.
    </ResponseField>
  </Expandable>
</ResponseField>
<ResponseField name="body" type="object">
  Override font settings specifically for body text.

  <Expandable title="Body">
    <ResponseField name="family" type="string" required>
      Font family name for body text.
    </ResponseField>
    <ResponseField name="weight" type="number">
      Font weight for body text.
    </ResponseField>
    <ResponseField name="source" type="string (uri)">
      URL to your font source, such as `https://mintlify-assets.b-cdn.net/fonts/Hubot-Sans.woff2`, or path to your local font file for body text. Google Fonts are loaded automatically when you specify a Google Font `family` name, so no source URL is needed.
    </ResponseField>
    <ResponseField name="format" type="'woff' | 'woff2'">
      Font file format for body text. Required when using the `source` field.
    </ResponseField>
  </Expandable>
</ResponseField>
```