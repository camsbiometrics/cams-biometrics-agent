# Cams Biometrics for Gemini CLI

Connect Gemini CLI to your Cams Biometrics account. Ask Gemini about your
devices, device users and attendance, and (with write access) make changes,
in plain language.

This extension only registers the existing Cams MCP connector with Gemini CLI.
It contains no server code.

## What it can do

- **Read your data:** devices, device users, attendance, device health.
- **Make changes** (needs write access): add or copy users, enrol users, open a
  door, reset a device queue.

## Prerequisites

- [Gemini CLI](https://geminicli.com) installed.
- A Cams Biometrics account (portal at https://camsbiometrics.com) with MCP
  access. It is switched on the first time you connect; if your organisation
  has been switched off by Cams you will see a "contact Cams" message.
- A browser on the same machine as Gemini CLI, for sign-in.

## Install

```
gemini extensions install <repository-url>
```

Replace `<repository-url>` with the URL of this repository once it is published.

## Sign in

The connector is `https://agent.camsbiometrics.com` (use it exactly as shown,
without `/mcp`). After installing, start Gemini CLI and run:

```
/mcp auth cams
```

Your browser opens the Cams sign-in page. Sign in and approve the access
request. Each connection is listed under **Connected Apps** in the Cams portal,
where you can revoke it at any time.

### Using an API key instead

For setups that cannot open a browser, create a key in the portal under
**AI Assistants > API Keys** (read only, or read and make changes). Register
the connector by hand instead of using sign-in:

```
gemini mcp add --transport http --scope user cams https://agent.camsbiometrics.com --header "Authorization: Bearer <your-api-key>"
```

Never commit or share your key. Revoke it in the portal if it leaks.

## Troubleshooting

- **"MCP access is not enabled for this account":** contact Cams to finish
  setup. Reconnecting will not help.
- **Sign-in page does not open:** run `/mcp auth cams` on a machine with a
  browser, or use an API key.
- **Tools missing after sign-in:** run `/mcp` to check that `cams` shows as
  connected, then restart Gemini CLI.

## Support

- WhatsApp support: +91-98409-81006
- Sales: +91-98409-41006
