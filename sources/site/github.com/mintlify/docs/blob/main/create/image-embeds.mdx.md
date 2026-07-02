# Source: https://github.com/mintlify/docs/blob/main/create/image-embeds.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# image-embeds.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/create/image-embeds.mdx)

History

211 lines (160 loc) · 5.53 KB

## FilesExpand file tree

 main

/

# image-embeds.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

211 lines (160 loc) · 5.53 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/image-embeds.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Images and embeds</td></tr><tr><th>description</th><td>Add images, embed YouTube videos, and include iframes in your MDX pages to enhance documentation with visual and interactive media content.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">images</div></th><th><div dir="auto">videos</div></th><th><div dir="auto">iframes</div></th><th><div dir="auto">media</div></th><th><div dir="auto">svg</div></th></tr></tbody></table></td></tr></tbody></table>

Add images, embed videos, and include interactive content with iframes to your documentation.

[![Photograph of a scenic landscape with purple flowers in the foreground, mountains in the background, and a blue sky with scattered clouds.](https://camo.githubusercontent.com/67056a40bff7d506e593b7be7656555f36f860e07dd84cbd963fd19a3854717b/68747470733a2f2f6d696e746c6966792d6173736574732e622d63646e2e6e65742f62696762656e642e6a7067)](https://camo.githubusercontent.com/67056a40bff7d506e593b7be7656555f36f860e07dd84cbd963fd19a3854717b/68747470733a2f2f6d696e746c6966792d6173736574732e622d63646e2e6e65742f62696762656e642e6a7067)

## Images

Add images to provide visual context, examples, or decoration to your documentation.

### Basic image syntax

Use [Markdown syntax](https://www.markdownguide.org/basic-syntax/#images) to add images to your documentation:

```mdx
![Alt text describing the image](/images/screenshot.png)
```

Image paths are root-relative from your docs repository. For example, if your image is at `images/screenshot.png` in your repository, the path is `/images/screenshot.png`. Relative paths (for example, `./screenshot.png`) are not supported.

Always include descriptive alt text to improve accessibility and SEO. The alt text should clearly describe what the image shows.

Image files must be less than 20 MB. For larger files, host them on a CDN service like [Amazon S3](https://aws.amazon.com/s3) or [Cloudinary](https://cloudinary.com).

### HTML image embeds

For more control over image display, use HTML `<img>` tags:

```js
<img 
  src="/images/dashboard.png" 
  alt="Main dashboard interface"
  style={{height: "300px", width: "400px"}}
  className="rounded-lg"
/>
```

#### Resize images with inline styles

Use JSX inline styles with the `style` attribute to resize images:

```js
<img
  src="/images/architecture.png"
  style={{width: "450px", height: "auto"}}
  alt="Diagram showing the architecture of the system"
/>
```

#### Disable image zoom

To disable the default zoom on click for images, add the `noZoom` property:

```html
<img 
  src="/images/screenshot.png" 
  alt="Descriptive alt text"
  noZoom
/>
```

#### Link images

To make an image a clickable link, wrap the image in an anchor tag and add the `noZoom` property:

```html
<a href="https://mintlify.com" target="_blank">
  <img 
    src="/images/logo.png" 
    alt="Mintlify logo"
    noZoom
  />
</a>
```

Images within anchor tags automatically display a pointer cursor to indicate they are clickable.

#### Light and dark mode images

To display different images for light and dark themes, use Tailwind CSS classes:

```html
<!-- Light mode image -->
<img 
  className="block dark:hidden" 
  src="/images/light-mode.png" 
  alt="Light mode interface"
/>

<!-- Dark mode image -->
<img 
  className="hidden dark:block" 
  src="/images/dark-mode.png" 
  alt="Dark mode interface"
/>
```

### SVG images

SVG files that use `foreignObject` elements render differently in production than in local development. Mintlify's image CDN strips `foreignObject` from SVGs as a security measure, which can truncate or hide text and other embedded HTML content.

This commonly affects SVGs exported from tools like [draw.io](https://www.drawio.com) that have HTML text formatting or word wrap turned on. To fix this, disable **Formatted Text** and **Word Wrap** on all labels in your diagram before exporting to SVG. See the [draw.io documentation](https://www.drawio.com/doc/faq/svg-export-text-problems) for more information on SVG exports.

## Videos

Mintlify supports [HTML tags in Markdown](https://www.markdownguide.org/basic-syntax/#html), giving you flexibility to create rich content.

Always include fallback text content within video elements for browsers that don't support video playback.

### YouTube embeds

Embed YouTube videos using iframe elements:

```html
<iframe
  className="w-full aspect-video rounded-xl"
  src="https://www.youtube.com/embed/4KzFe50RQkQ"
  title="YouTube video player"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowFullScreen
></iframe>
```

<iframe className="w-full aspect-video rounded-xl" src="[https://www.youtube.com/embed/4KzFe50RQkQ](https://www.youtube.com/embed/4KzFe50RQkQ)" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowFullScreen ></iframe>

### Self-hosted videos

Use the HTML `<video>` element for self-hosted video content:

```html
<video
  controls
  className="w-full aspect-video rounded-xl"
  src="link-to-your-video.com"
></video>
```

### Autoplay videos

To autoplay a video, use:

```html
<video
  autoPlay
  muted
  loop
  playsInline
  className="w-full aspect-video rounded-xl"
  src="/videos/demo.mp4"
></video>
```

When using JSX syntax, write double-word attributes in camelCase: \`autoPlay\`, \`playsInline\`, \`allowFullScreen\`.

## Iframes

Embed external content using iframe elements:

```html
<iframe 
  src="https://example.com/embed" 
  title="Embedded content"
  className="w-full h-96 rounded-xl"
></iframe>
```

Wrap iframes in a \[frame\](/components/frames) component to keep them within the text column width and prevent overflow.

```html
<Frame>
  <iframe 
    src="https://example.com/embed" 
    title="Embedded content"
    className="w-full h-96 rounded-xl"
  ></iframe>
</Frame>
```

## Related resources

Learn how to use the Frame component for presenting images.