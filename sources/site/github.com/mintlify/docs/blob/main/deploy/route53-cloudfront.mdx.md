# Source: https://github.com/mintlify/docs/blob/main/deploy/route53-cloudfront.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# route53-cloudfront.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/route53-cloudfront.mdx)

History

207 lines (135 loc) · 8.22 KB

## FilesExpand file tree

 main

/

# route53-cloudfront.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

207 lines (135 loc) · 8.22 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/route53-cloudfront.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>AWS Route 53 and CloudFront</td></tr><tr><th>sidebarTitle</th><td>AWS</td></tr><tr><th>description</th><td>Deploy your Mintlify documentation at a subpath on AWS using Route 53 for DNS routing and CloudFront as a CDN with Lambda@Edge functions.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">AWS deployment</div></th><th><div dir="auto">Route 53 DNS</div></th><th><div dir="auto">CloudFront CDN</div></th><th><div dir="auto">cache policies</div></th></tr></tbody></table></td></tr></tbody></table>

import Propagating from "/snippets/custom-subpath-propagating.mdx";

To host your documentation at a subpath such as `yoursite.com/docs` using AWS Route 53 and CloudFront, you must configure your DNS provider to point to your CloudFront distribution.

## Overview

Route traffic to these paths with a Cache Policy of **CachingDisabled**:

- `/.well-known/acme-challenge/*` - Required for Let's Encrypt certificate verification
- `/.well-known/vercel/*` - Required for domain verification
- `/docs/*` - Required for subpath routing
- `/docs/` - Required for subpath routing

Route traffic to this path with a Cache Policy of **CachingEnabled**:

- `/mintlify-assets/_next/static/*`
- `Default (*)` - Your website's landing page

All Behaviors must have an **origin request policy** of `AllViewerExceptHostHeader`.

[![CloudFront "Behaviors" page with 4 behaviors: /docs/*, /docs, Default, and /.well-known/*.](https://github.com/mintlify/docs/raw/main/images/cloudfront/all-behaviors.png)](https://github.com/mintlify/docs/blob/main/images/cloudfront/all-behaviors.png)

## Create CloudFront distribution

1. Navigate to [CloudFront](https://aws.amazon.com/cloudfront) inside the AWS console.
2. Click **Create distribution**.

!\[CloudFront Distributions page with the "Create distribution" button emphasized.\](/images/cloudfront/create-distribution.png)

3. For the Origin domain, input `[SUBDOMAIN].mintlify.site` where `[SUBDOMAIN]` is your project's unique subdomain.

!\[CloudFront "Create distribution" page showing "acme.mintlify.site" as the origin domain.\](/images/cloudfront/origin-name.png)

4. For "Web Application Firewall (WAF)," enable security protections.

!\[Web Application Firewall (WAF) options with "Enable security protections" selected.\](/images/cloudfront/enable-security-protections.png)

5. The remaining settings should be default.
6. Click **Create distribution**.

## Add default origin

1. After creating the distribution, navigate to the "Origins" tab.

!\[A CloudFront distribution with the "Origins" tab highlighted.\](/images/cloudfront/origins.png)

2. Find your staging URL that mirrors the main domain. This varies depending on how your landing page is hosted. For example, the Mintlify staging URL is [mintlify-landing-page.vercel.app](https://mintlify-landing-page.vercel.app).

If your landing page is hosted on Webflow, use Webflow's staging URL. It would look like \`.webflow.io\`.

If you use Vercel, use the `.vercel.app` domain available for every project.

3. Create a new Origin and add your staging URL as the "Origin domain."

!\[CloudFront "Create origin" page with a "Origin domain" input field highlighted.\](/images/cloudfront/default-origin.png)

By this point, you should have two Origins: one with `[SUBDOMAIN].mintlify.site` and another with your staging URL.

!\[CloudFront "Origins" page with two origins: One for \`mintlify\` and another for \`mintlify-landing-page\`.\](/images/cloudfront/final-origins.png)

## Set behaviors

Behaviors in CloudFront enable control over the subpath logic. At a high level, you create the following logic:

- **If a user lands on your custom subpath**, go to `[SUBDOMAIN].mintlify.site`.
- **If a user lands on any other page**, go to the current landing page.

1. Navigate to the "Behaviors" tab of your CloudFront distribution.

!\[CloudFront "Behaviors" tab highlighted.\](/images/cloudfront/behaviors.png)

2. Click the **Create behavior** button and create the following behaviors.

### `/.well-known/*`

Create behaviors for Vercel domain verification paths with a **Path pattern** of `/.well-known/*` and set **Origin and origin groups** to your docs URL.

For "Cache policy," select **CachingDisabled** to ensure these verification requests pass through without caching.

!\[CloudFront "Create behavior" page with a "Path pattern" of "/.well-known/\*" and "Origin and origin groups" pointing to the staging URL.\](/images/cloudfront/well-known-policy.png) If \`.well-known/\*\` is too generic, it can be narrowed down to 2 behaviors at a minimum for Vercel: - \`/.well-known/vercel/\*\` - Required for Vercel domain verification - \`/.well-known/acme-challenge/\*\` - Required for Let's Encrypt certificate verification

### Your subpath

Create a behavior with a **Path pattern** of your chosen subpath, for example `/docs`, with **Origin and origin groups** pointing to the `.mintlify.site` URL (for example, `acme.mintlify.site`).

- Set "Cache policy" to **CachingOptimized**.
- Set "Origin request policy" to **AllViewerExceptHostHeader**.
- Set Viewer Protocol Policy to **Redirect HTTP to HTTPS**

!\[CloudFront "Create behavior" page with a "Path pattern" of "/docs/\*" and "Origin and origin groups" pointing to the \`acme.mintlify.site\` URL.\](/images/cloudfront/behavior-1.png)

### Your subpath with wildcard

Create a behavior with a **Path pattern** of your chosen subpath followed by `/*`, for example `/docs/*`, and **Origin and origin groups** pointing to the same `.mintlify.site` URL.

These settings should exactly match your base subpath behavior. With the exception of the **Path pattern**.

- Set "Cache policy" to **CachingOptimized**.
- Set "Origin request policy" to **AllViewerExceptHostHeader**.
- Set "Viewer protocol policy" to **Redirect HTTP to HTTPS**

### `/mintlify-assets/_next/static/*`

- Set "Cache policy" to **CachingOptimized**
- Set "Origin request policy" to **AllViewerExceptHostHeader**
- Set "Viewer protocol policy" to **Redirect HTTP to HTTPS**

### `Default (*)`

Lastly, edit the `Default (*)` behavior.

!\[A CloudFront distribution with the "Default (\*)" behavior selected and the Edit button emphasized.\](/images/cloudfront/default-behavior-1.png)

1. Change the default behavior's **Origin and origin groups** to the staging URL (for example, `mintlify-landing-page.vercel.app`).

!\[CloudFront "Edit behavior" page with the "Origin and origin groups" input field highlighted.\](/images/cloudfront/default-behavior-2.png)

2. Click **Save changes**.

### Check behaviors are set up correctly

If you follow the preceding steps, your behaviors should look like this:

!\[CloudFront "Behaviors" page with 4 behaviors: \`/docs/\*\`, \`/docs\`, \`Default\`, and \`/.well-known/\*\`.\](/images/cloudfront/all-behaviors.png)

## Preview distribution

You can now test if your distribution is set up properly by going to the "General" tab and visiting the **Distribution domain name** URL.

!\[CloudFront "General" tab with the "Distribution domain name" URL highlighted.\](/images/cloudfront/preview-distribution.png)

All pages should be directing to your main landing page, but if you append your chosen subpath, for example `/docs`, to the URL, you should see it going to your Mintlify documentation instance.

## Connect with Route 53

Now, bring the capabilities of the CloudFront distribution into your primary domain.

For this section, you can also refer to AWS's official guide on \[Configuring Amazon Route 53 to route traffic to a CloudFront distribution\]([https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-to-cloudfront-distribution.html#routing-to-cloudfront-distribution-config](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-to-cloudfront-distribution.html#routing-to-cloudfront-distribution-config))

1. Navigate to [Route53](https://aws.amazon.com/route53) inside the AWS console.
2. Navigate to the "Hosted zone" for your primary domain.
3. Click **Create record**.

!\[Route 53 "Records" page with the "Create record" button emphasized.\](/images/cloudfront/route53-create-record.png)

4. Toggle `Alias` and then **Route traffic to** the `Alias to CloudFront distribution` option.

!\[Route 53 "Create record" page with the "Alias" toggle and the "Route traffic to" menu highlighted.\](/images/cloudfront/create-record-alias.png)

5. Click **Create records**.

You may need to remove the existing A record if one currently exists.

Your documentation is now live at your chosen subpath for your primary domain.