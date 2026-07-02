# Source: https://github.com/mintlify/docs/blob/main/deploy/cloudflare-firewall-troubleshooting.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# cloudflare-firewall-troubleshooting.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/cloudflare-firewall-troubleshooting.mdx)

History

99 lines (70 loc) · 3.3 KB

## FilesExpand file tree

 main

/

# cloudflare-firewall-troubleshooting.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

99 lines (70 loc) · 3.3 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/cloudflare-firewall-troubleshooting.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Cloudflare firewall troubleshooting</td></tr><tr><th>description</th><td>Troubleshoot blocked requests and resolve Cloudflare WAF rule conflicts when serving Mintlify documentation through Cloudflare Workers.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">Cloudflare WAF</div></th><th><div dir="auto">firewall rules</div></th><th><div dir="auto">Bot Fight Mode</div></th><th><div dir="auto">403 errors</div></th></tr></tbody></table></td></tr></tbody></table>

If your documentation site shows 500 errors after a few seconds or experiences slow navigation, Cloudflare's firewall may be blocking requests to Mintlify assets.

## Symptoms

- Documentation page loads initially but crashes with a 500 error after 30-60 seconds
- Slow or broken client-side navigation between pages
- 403 errors in browser console for requests to `/mintlify-assets/*` paths
- Cloudflare security challenge messages about "malformed data" or "suspicious URL patterns"

## Root cause

Cloudflare's Web Application Firewall (WAF) and Bot Fight Mode can flag Mintlify asset requests as suspicious due to:

- Multiple `%` symbols in encoded URL parameters
- Long query strings with special characters
- Automated requests from idle tabs

## Solution

Create a Cloudflare firewall rule to exempt Mintlify assets from security checks.

### Create the firewall exception

1. Log in to your [Cloudflare dashboard](https://dash.cloudflare.com/)
2. Select your domain
3. Navigate to **Security > WAF**
4. Click **Create rule**
5. Configure the rule with these settings:

**Rule name:** Allow Mintlify assets

**When incoming requests match:**

- Field: `Hostname`
- Operator: `equals`
- Value: `docs.yourdomain.com` (replace with your actual docs domain)

**And:**

- Field: `URI Path`
- Operator: `starts with`
- Value: `/mintlify-assets/`

**Then:**

- Action: `Skip`
- Select: `All remaining custom rules`, `Managed rules`, and `Super Bot Fight Mode`

6. Enable **Log** to track matched requests
7. Click **Deploy**

### Verify the rule

After deploying:

1. Open your documentation site in a browser
2. Leave the page idle for 2-3 minutes
3. Navigate between pages
4. Check browser console for any 403 errors

If issues persist, verify your rule configuration:

- Ensure the hostname exactly matches your docs domain
- Confirm the URI path uses `starts with` (not `contains`)
- Do not include wildcards (`*`) in the path value
- Verify the rule is enabled and deployed

## Common mistakes

- Using `contains` operator with `/mintlify-assets/*` - The `*` is treated as a literal character, not a wildcard
- Using `equals` for URI Path - This only matches the exact path `/mintlify-assets/` and not subpaths
- Forgetting to skip Bot Fight Mode - This must be explicitly included in the skip action
- Wrong hostname - Must match your actual documentation domain

## Additional troubleshooting

If the firewall exception doesn't resolve the issue:

1. Check Cloudflare's **Security > Events** log for blocked requests
2. Verify your Cloudflare Worker (if using custom subpath) correctly forwards the `Host` header
3. Temporarily set Security Level to "Essentially Off" to confirm Cloudflare is the cause
4. Review any custom Page Rules that might override the firewall exception

## Example working configuration

```
Rule: Allow Mintlify assets
Status: Enabled

When incoming requests match:
  (http.host eq "docs.flashnet.xyz" and starts_with(http.request.uri.path, "/mintlify-assets/"))

Then:
  Skip: All remaining custom rules, Managed rules, Super Bot Fight Mode
  Log: Enabled
```