# Connect your AI assistant to Light

Light's MCP integration lets you use AI tools to query your financial data, search invoices, look up vendors, and run reports, without switching context.

Your AI model runs on your machine. Light only receives the individual tool calls you trigger and returns the results. No conversation history or AI output is ever sent to Light.

---

## Prerequisites

- Access to Light (your account must be enabled for MCP, contact your account manager if the MCP Tokens section is not visible in your profile)
- The AI client you want to connect installed on your machine

---

## Step 1: Generate a token

Tokens are personal, each team member generates and manages their own. Tokens are never shown again after creation, so copy yours before closing the dialog.

1. Open **Settings → Profile** in Light
2. Scroll to the **MCP Tokens** section
3. Click **Add**
4. Enter a descriptive name (e.g. `Claude Code - MacBook`) and optionally set an expiration date
5. Click **Create**
6. Copy the token shown in the confirmation dialog, it starts with `lmcp_`
7. Check **I have saved my token** and click **Done**

> Each user can have up to **20 active tokens**. If you reach the limit, revoke unused ones from the MCP Tokens section before creating a new one.

---

## Step 2: Configure your client

### AI coding agents

#### Claude Code

Run this once, replacing the token with yours:

```bash
claude mcp add --transport http light-mcp https://api.light.inc/rest/ext/mcp --header "Authorization: Bearer lmcp_your_token_here"
```

That's it. Restart Claude Code and Light tools will appear in the tool list.

---

#### OpenCode

Set the token as an environment variable. Add this line to your shell profile (`~/.zshrc`, `~/.bashrc`, etc.) and reload your shell:

```bash
export LIGHT_MCP_TOKEN="lmcp_paste_your_token_here"
source ~/.zshrc   # or ~/.bashrc
```

Then edit `~/.config/opencode/opencode.json` and add the `light` entry under `mcp`:

```json
{
    "$schema": "https://opencode.ai/config.json",
    "mcp": {
        "light": {
            "type": "remote",
            "url": "https://api.light.inc/rest/ext/mcp",
            "headers": {
                "Authorization": "Bearer {env:LIGHT_MCP_TOKEN}"
            }
        }
    }
}
```

If OpenCode shows `⚠ needs authentication`, the environment variable was not in scope when it launched, open a new terminal and try again.

---

### Claude Desktop

Step-by-step walkthrough: [Connect Light's MCP server from Claude Desktop](https://app.supademo.com/demo/cmn2v0nkv4xersjdoez6n4ccs?utm_source=link)

---

### n8n

Step-by-step walkthrough: [Connect Light's MCP server from n8n](https://app.supademo.com/demo/cmn3x1hlk0cchz3qmh18fqr7m?utm_source=link)

---

## Step 3: Verify the connection

Open your AI agent and ask it something like:

> "What Light tools do you have available?"

If the connection is working, it will list the Light tools it can use. You're all set.

---

## Manage your tokens

All token management is available in **Settings → Profile → MCP Tokens**.

- **View tokens** : the list shows each token's name, status (Active / Revoked), expiry, and when it was last used
- **Revoke a token** : click a token to open its details, then click **Revoke token**. Revocation is immediate; the next request using that token returns a 401 error. This cannot be undone, you will need to create a new token if you still need access
- **Token details** : the full raw token is never shown again after creation. The detail view shows only the obfuscated version (e.g. `lmcp_xxxx...a3Bf`)

---

## Troubleshooting

| Symptom | Likely cause | Fix                                                                                                           |
|---------|--------------|---------------------------------------------------------------------------------------------------------------|
| MCP Tokens section not visible in Settings | Feature not yet enabled for your account | Contact your account manager                                                                                  |
| `401 Unauthorized` | Token revoked, expired, or not set correctly | Check **Settings → MCP Tokens** for the token's status; create a new token if needed                          |
| Tools list is empty or shorter than expected | Your Light role doesn't have access to those tools | Tools respect your existing permissions in Light, check your role in **Settings → Users**                     |
| OpenCode shows `⚠ needs authentication` | Environment variable was not set when OpenCode launched | Open a new terminal (with the variable exported) and try again                                                |
| `{"error":{"code":-32601}}` | Client version mismatch | Update your AI client to the latest version                                                                   |
| Other errors | Network issues, temporary server issues, etc. | Check your network connection and try again; if the issue persists, contact support with details of the error |
