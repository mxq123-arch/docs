# Source: https://github.com/mintlify/docs/blob/main/snippets/vercel-json-generator.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# vercel-json-generator.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/snippets/vercel-json-generator.mdx)

History

108 lines (105 loc) · 4.13 KB

 main

/

# vercel-json-generator.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

108 lines (105 loc) · 4.13 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/snippets/vercel-json-generator.mdx)

Copy raw file

Download raw file

Edit and raw actions

export const VercelJsonGenerator = () => { const \[subdomain, setSubdomain\] = useState('\[SUBDOMAIN\]') const \[subpath, setSubpath\] = useState('\[SUBPATH\]')

const vercelConfig = { rewrites: \[ { source: "/\_mintlify/:path\*", destination: `https://${subdomain}.mintlify.site/_mintlify/:path*` }, { source: "/api/request", destination: `https://${subdomain}.mintlify.site/_mintlify/api/request` }, { source: `/${subpath}`, destination: `https://${subdomain}.mintlify.site/${subpath}` }, { source: `/${subpath}/llms.txt`, destination: `https://${subdomain}.mintlify.site/llms.txt` }, { source: `/${subpath}/llms-full.txt`, destination: `https://${subdomain}.mintlify.site/llms-full.txt` }, { source: `/${subpath}/sitemap.xml`, destination: `https://${subdomain}.mintlify.site/sitemap.xml` }, { source: `/${subpath}/robots.txt`, destination: `https://${subdomain}.mintlify.site/robots.txt` }, { source: `/${subpath}/mcp`, destination: `https://${subdomain}.mintlify.site/mcp` }, { source: `/${subpath}/:path*`, destination: `https://${subdomain}.mintlify.site/${subpath}/:path*` }, { source: "/mintlify-assets/:path+", destination: `https://${subdomain}.mintlify.site/mintlify-assets/:path+` } \] }

const copyToClipboard = () => { navigator.clipboard .writeText(JSON.stringify(vercelConfig, null, 2)) .then(() => { console.log('Copied config to clipboard!') }) .catch((err) => { console.error("Failed to copy: ", err) }) }

return (

Subdomain <input type="text" value={subdomain} onChange={(e) => setSubdomain(e.target.value)} placeholder="your-subdomain" className="w-full p-1 text-sm rounded border dark:border-white/10 bg-transparent" />

Subpath <input type="text" value={subpath} onChange={(e) => setSubpath(e.target.value)} placeholder="docs" className="w-full p-1 text-sm rounded border dark:border-white/10 bg-transparent" />

Copy

```
{JSON.stringify(vercelConfig, null, 2)}
```

) }