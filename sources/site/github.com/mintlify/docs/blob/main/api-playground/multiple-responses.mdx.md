# Source: https://github.com/mintlify/docs/blob/main/api-playground/multiple-responses.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# multiple-responses.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)

[mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

and

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Improve SEO descriptions across 177 pages (](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) [#4993](https://github.com/mintlify/docs/pull/4993) [)](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712)

Open commit detailsfailure

Mar 31, 2026

[f8e015f](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) · Mar 31, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/api-playground/multiple-responses.mdx)

Open commit details

History

53 lines (46 loc) · 1.71 KB

## FilesExpand file tree

 main

/

# multiple-responses.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

53 lines (46 loc) · 1.71 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/api-playground/multiple-responses.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>Multiple responses</td></tr><tr><th>description</th><td>Document multiple response variations for API endpoints, including success and error cases, with status codes and example payloads.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">response examples</div></th><th><div dir="auto">conditional responses</div></th><th><div dir="auto">response variations</div></th><th><div dir="auto">examples property</div></th></tr></tbody></table></td></tr></tbody></table>

If your API returns different responses based on input parameters, user context, or other conditions of the request, you can document multiple response examples with the `examples` property.

Add this property to any response. It has the following schema.

```yaml
responses:
  "200":
    description: Successful response
    content:
      application/json:
        schema:
          $ref: "#/components/schemas/YourResponseSchema"
        examples:
          us:
            summary: Response for United States
            value:
              countryCode: "US"
              currencyCode: "USD"
              taxRate: 0.0825
          gb:
            summary: Response for United Kingdom
            value:
              countryCode: "GB"
              currencyCode: "GBP"
              taxRate: 0.20
```

The playground also handles non-JSON response types differently based on their content type.

## Audio response examples

For endpoints that return audio files, set the response content type to `audio/*` and provide a URL to an audio file as the example value. The playground renders an interactive audio player instead of a code snippet.

```yaml
responses:
  "200":
    description: Audio file generated successfully
    content:
      audio/mpeg:
        schema:
          type: string
          format: binary
        examples:
          sample:
            summary: Sample audio output
            value: "https://example.com/sample-audio.mp3"
```