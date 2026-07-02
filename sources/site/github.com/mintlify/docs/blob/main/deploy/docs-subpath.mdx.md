# Source: https://github.com/mintlify/docs/blob/main/deploy/docs-subpath.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# docs-subpath.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/docs-subpath.mdx)

History

21 lines (15 loc) · 1.39 KB

 main

/

# docs-subpath.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

21 lines (15 loc) · 1.39 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/docs-subpath.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Host docs at a /docs subpath</td></tr><tr><th>description</th><td>Host your Mintlify documentation at a /docs subpath on your main domain using Cloudflare Workers, Vercel rewrites, or an nginx reverse proxy.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">subpath routing</div></th><th><div dir="auto">/docs setup</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Host your documentation at a subpath like `your-domain.com/docs` to keep your docs on your main domain, which makes them easier to find and maintains a cohesive brand experience for your users.

## Set up by hosting provider

Setting up a `/docs` subpath varies depending on your hosting provider. Choose your hosting provider and follow the setup instructions.

- [Cloudflare](https://github.com/mintlify/docs/blob/main/deploy/cloudflare): Set up Cloudflare Workers for your domain to serve your documentation at the `/docs` subpath.
- [AWS Route 53 and CloudFront](https://github.com/mintlify/docs/blob/main/deploy/route53-cloudfront): Deploy your documentation at the `/docs` subpath using AWS with Route 53 DNS and CloudFront CDN.
- [Vercel](https://github.com/mintlify/docs/blob/main/deploy/vercel) - Use rewrites to deploy your documentation at the `/docs` subpath.
- [Custom reverse proxy](https://github.com/mintlify/docs/blob/main/deploy/reverse-proxy) - For other hosting platforms, set up a reverse proxy to deploy your documentation at the `/docs` subpath.

### Additional configuration for strict security policies

If you proxy all traffic on your custom domain, you may need to configure your proxy or firewall rules to add the correct [headers](https://github.com/mintlify/docs/blob/main/deploy/csp-configuration) so your documentation displays properly.