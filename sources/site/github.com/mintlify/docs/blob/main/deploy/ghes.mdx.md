# Source: https://github.com/mintlify/docs/blob/main/deploy/ghes.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# ghes.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)](https://github.com/apps/mintlify) [mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

[docs: apply sentence case to two headings/labels for style consistency (](https://github.com/mintlify/docs/commit/13feb4b38aa37db8dedf19843e931a57a65b44ce)

Open commit detailssuccess

Jun 26, 2026

[13feb4b](https://github.com/mintlify/docs/commit/13feb4b38aa37db8dedf19843e931a57a65b44ce) · Jun 26, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/ghes.mdx)

Open commit details

History

255 lines (193 loc) · 8.75 KB

## FilesExpand file tree

 main

/

# ghes.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

255 lines (193 loc) · 8.75 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/ghes.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>GitHub Enterprise Server</td></tr><tr><th>description</th><td>Install and configure the Mintlify GitHub App on your GitHub Enterprise Server instance for automated documentation deployments and syncing.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">GitHub Enterprise Server</div></th><th><div dir="auto">GHES</div></th><th><div dir="auto">GitHub Enterprise</div></th></tr></tbody></table></td></tr></tbody></table>

This guide walks you through setting up the Mintlify GitHub App on your GitHub Enterprise Server (GHES) installation. To connect a GHES instance to Mintlify, you must create a local version of our app within your self-hosted environment that communicates with our remote server.

If you use a cloud-hosted GitHub instance, see the [GitHub](https://github.com/mintlify/docs/blob/main/deploy/github) page for setup instructions.

## Prerequisites

- Admin privileges on your GitHub Enterprise Server organization where you want to install the app
- Access to your organization's repositories where you want to install the app
- Network connectivity to communicate with our external services (see [Network requirements](https://github.com/#network-requirements) section below)

### Network requirements

#### Outbound connectivity

Your GitHub Enterprise Server must be able to reach:

- Mintlify's API endpoints ([https://leaves.mintlify.com](https://leaves.mintlify.com))
- Webhook receivers (port 443)

#### Firewall configuration

The following outbound connections must be allowed:

- Connections from Mintlify's static IP: `54.242.90.151`
- HTTPS (port 443) to Mintlify's service domains
- DNS resolution for Mintlify's service domains

## Step 1: Register the GitHub App

See [Registering a GitHub App](https://docs.github.com/en/enterprise-server@3.18/apps/creating-github-apps/registering-a-github-app/registering-a-github-app) in the GitHub documentation for detailed instructions.

1\. In the upper-right corner of any page on GitHub, click your profile picture. 2. Click \*\*Your organizations\*\*. 3. Click \*\*Settings\*\* next to the organization that you want to create the app for. 1. In the left sidebar, click \*\*Developer settings\*\*. 2. Click \*\*GitHub Apps\*\*. 3. Click \*\*New GitHub App\*\*. Set the following:

- **GitHub App name:** `Mintlify`
- **Description:** `Integration with Mintlify services`
- **Homepage URL:** `https://mintlify.com`
- **User authorization callback URL:** `https://your-github-server.com/` (replace with your actual GHES domain)

## Step 2: Configure app permissions

Set the following permissions for the app. No Organization, Account, or Enterprise permissions are required:

- **Checks:** Read and write
- **Contents:** Read and write
- **Deployments:** Read and write
- **Metadata:** Read-only
- **Pull Requests:** Read and write

Select the following webhook events:

- Installation
- Installation Target
- Create
- Delete
- Public
- Pull Request
- Push
- Repository

## Step 3: Generate and secure credentials

Click \*\*Create GitHub App\*\*.

You'll be redirected to the app's settings page.

1\. Scroll down to the \*\*Private keys\*\* section. 2. Click \*\*Generate a private key\*\*. 3. Download the \`.pem\` file and securely store it. Record the following:

- **App ID** (visible at the top of the settings page)
- **Client ID** (in the "About" section)
- **Client Secret** (generate and record it securely)

## Step 4: Install the app

1\. From the app settings page, click \*\*Install App\*\* in the left sidebar. 2. Select your organization from the list. Select either:

- **All repositories** (for organization-wide access)
- **Only select repositories** (choose specific repositories)

1\. Click \*\*Install\*\*. 2. Record the installation ID from the URL. For example, in \`[https://your-github-server.com/settings/installations/12345\`](https://your-github-server.com/settings/installations/12345`), the string \`12345\` is the installation ID.

## Step 5: Configure webhook URL

1\. Go back to your app's settings page. 2. Scroll to the \*\*Webhook\*\* section. Configure the following:

-   **Webhook URL:** `https://leaves.mintlify.com/github-enterprise/:subdomain` (replace `:subdomain` with the URL that we provide you with)
-   **Webhook secret:** Generate a random string (32+ characters) and record it securely. Mintlify can also generate this and provide it to you.

## Share credentials with us

Share the following information with our team using your secure information transfer method of choice.

### Required credentials

-   GitHub Enterprise Server base URL: [https://your-github-server.com](https://your-github-server.com)
-   App ID: (from step 3)
-   App client ID: (from step 3)
-   App client secret: (from step 3)
-   Installation ID: (from step 4)
-   Private key: The entire contents of the `.pem` file (should be shared via secure file transfer)
- Webhook secret: (from step 5)

### Optional credentials for troubleshooting

- Organization name: Your GitHub organization name
- Repository names: Specific repositories where the app is installed
- GitHub Enterprise Server version: Found in your site admin dashboard

## Mintlify connection

We take the credentials you provide us and store them, encrypted, in a secure location. Then we work with you to either:

- Integrate your GHES environment with an existing Mintlify deployment.
- Integrate your GHES environment with a new Mintlify deployment that we provision for you.

After your GHES environment is integrated with a Mintlify deployment, you are ready to enable webhooks for your GitHub App.

The webhook URL may change based on our configuration. We test the integration and provide you with the new URL.

## Test the integration

1\. Go to your GitHub App settings. 2. Click the \*\*Advanced\*\* tab. 3. Check "Recent Deliveries" for successful webhook deliveries. 4. Look for HTTP 200 responses. 1. Create a test issue or pull request in an installed repository. 2. Verify that Mintlify responds appropriately.

## FAQ and troubleshooting

Ensure you have:

- Site admin privileges for app creation
- Organization owner or admin rights for app installation.
- Proper repository permissions if installing on specific repositories.

\- Verify the webhook URL is correct and accessible. - Ensure your firewall allows outbound HTTPS connections. - Check the webhook secret matches what was configured. - Review webhook delivery logs in the "Advanced" tab of your GitHub App settings. Your GHES might use self-signed certificates. Our services cannot verify your server's certificate.

**Solution:** Ensure your GHES has a valid SSL certificate.

\- Ensure webhooks are being delivered and acknowledged by our server with response code 200. - Required permissions were granted during installation. Yes, during installation you can select "Only select repositories" and choose specific ones. You can modify this later in your organization's installed apps settings. This is the recommended form of installation. - Go to the app settings as a site admin. - Modify permissions as needed. - The app needs to be re-approved by organization owners. - Notify us of any permission changes so we can advise on any additional steps that may be required. You must:

- Add our service domains to your firewall allowlist.
- Ensure outbound HTTPS (port 443) connectivity.
- If direct internet access is not allowed, set up a proxy.

No, your GHES must be able to communicate with our cloud-hosted server. Reach out to your customer success representative at Mintlify, or contact our support team at [support@mintlify.com](mailto:support@mintlify.com) with:

- Your GitHub Enterprise Server version.
- Specific error messages.
- Screenshots of any issues.
- Network/firewall configuration details (if relevant).