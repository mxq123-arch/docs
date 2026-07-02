# Source: https://github.com/mintlify/docs/blob/main/deploy/vercel-external-proxies.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# vercel-external-proxies.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/vercel-external-proxies.mdx)

History

33 lines (21 loc) · 1.67 KB

## FilesExpand file tree

 main

/

# vercel-external-proxies.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

33 lines (21 loc) · 1.67 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/vercel-external-proxies.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>External proxies with Vercel</td></tr><tr><th>description</th><td>Configure external reverse proxies like Cloudflare or Nginx in front of your Vercel deployment to serve Mintlify docs at a custom subpath.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">Vercel</div></th><th><div dir="auto">external proxy</div></th><th><div dir="auto">CloudFront</div></th><th><div dir="auto">domain verification</div></th><th><div dir="auto">SSL certificates</div></th></tr></tbody></table></td></tr></tbody></table>

If you have an external proxy like Cloudflare or AWS CloudFront in front of your Vercel deployment, you must configure it properly to avoid conflicts with Vercel's domain verification and SSL certificate provisioning.

Improper proxy configuration can prevent Vercel from provisioning Let's Encrypt SSL certificates and cause domain verification failures.

See the [supported providers](https://vercel.com/guides/how-to-setup-verified-proxy#supported-providers-verified-proxy-lite) in the Vercel documentation.

## Required path allowlist

Your external proxy must allow traffic to these specific paths without blocking, redirecting, or heavily caching:

- `/.well-known/acme-challenge/*` - Required for Let's Encrypt certificate verification
- `/.well-known/vercel/*` - Required for Vercel domain verification
- `/mintlify-assets/_next/static/*` - Required for static assets

These paths should pass through directly to your Vercel deployment without modification.

## Header forwarding requirements

Ensure that your proxy correctly forwards the `HOST` header. Without proper header forwarding, verification requests fail.

## Test your proxy setup

To verify your proxy is correctly configured:

1. Test that `https://[yourdomain].com/.well-known/vercel/` returns a response.
2. Ensure SSL certificates are provisioning correctly in your Vercel dashboard.
3. Check that domain verification completes successfully.