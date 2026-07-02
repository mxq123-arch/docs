# Source: https://github.com/mintlify/docs/blob/main/optimize/pdf-exports.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# pdf-exports.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/optimize/pdf-exports.mdx)

History

43 lines (33 loc) · 1.94 KB

 main

/

# pdf-exports.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

43 lines (33 loc) · 1.94 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/optimize/pdf-exports.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>PDF exports</td></tr><tr><th>description</th><td>Export your entire documentation site as a single PDF with a navigable table of contents for offline reading, sharing, and print distribution.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">PDF</div></th><th><div dir="auto">offline docs</div></th></tr></tbody></table></td></tr></tbody></table>

export const DownloadPDFButton = () => { return ( [View Example PDF](https://github.com/mintlify/docs/blob/main/files/mint-full-docs.pdf) ) }

PDF exports are available on \[Enterprise plans\]([https://mintlify.com/pricing](https://mintlify.com/pricing)).

You can export your docs as a single PDF file for offline viewing. The PDF contains all the content in the docs, including images and links, and a navigable table of contents.

Full-site PDF exports include all pages regardless of group restrictions, so anyone with access to the exported PDF can read content that may otherwise be gated behind user groups.

To let users download individual pages as PDFs, use the \[contextual menu's\](/ai/contextual-menu) \`download-pdf\` option.

## Export a PDF

1. Navigate to the [General](https://app.mintlify.com/settings/deployment/general) page in the Project Settings section of your dashboard.
2. Click the **Export all content** button.
3. Optionally, customize the export options:
 - **Page format**: Choose the page size of the PDF.
 - **Scale percentage**: Adjust the scale of the PDF.
 - **Include footer**: Include a footer with the page number and total pages.
 - **Language**: If your content is available in multiple languages, choose which language to export.
4. Click **Export** to start the export process.
5. Once the export is complete, you receive an email with a download link.
6. Click the download link to download the PDF file.