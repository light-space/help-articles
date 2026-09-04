# API Access and Custom Integrations

> **What's this page about: **What Light's REST API is for, who can use it, how to get access, and where the documentation lives. The technical detail (authentication, every endpoint, error codes, rate limits) is maintained in one place, the API documentation at light.inc/docs, so it is not repeated here.

## On this page

- What you can do with the API
- Who it is for
- Getting access
- Where to read next
- Connecting an AI assistant instead
- Rate limits and support
- Related articles

Light's REST API lets any system create and read the same records you work with in Light: bills, sales invoices, journal entries, customers, vendors, the chart of accounts and the ledger itself. Use it where a pre-built integration does not exist.

[Open in Light →](https://app.light.inc/settings/api-keys)

[Open API documentation →](https://light.inc/docs)

## What you can do with the API

- Push bills from a procurement or AP system, with line items and the PDF, straight into your approval flow
- Create customers and sales invoices from a CRM or billing system, and send them
- Post journal entries (accruals, reclassifications, corrections) from a close checklist or a spreadsheet tool
- Pull the general ledger, account balances and every accounting document into a data warehouse or BI tool
- Keep vendors, customers and products in sync with a master-data system

The API does not send webhooks, does not expose reports beyond the general ledger summary, and does not list tax codes. [Choosing an endpoint](https://light.inc/docs/concepts/choosing-an-endpoint) maps common jobs to the calls that do them and lists what is not available.

## Who it is for

Anyone who can make HTTP requests, or who works with someone who can. If you are a finance user working out what an integration could do, the [Concepts](https://light.inc/docs/concepts/how-light-records-money) pages explain how Light keeps books in plain language: what a document is, why a posting has two sides, how to read the amounts, what a closed period blocks. They are written for you, not for developers.

## Getting access

1. Go to **Settings (gear icon) → API keys**
2. Click **Create key**, choose the roles the key should have, and copy the key. Light shows it once.
3. Give each integration its own key with the narrowest roles that work. A key can do exactly what its roles can do, and it appears in the audit trail as its own actor. Use the IP allowlist if the calling system has a fixed address.

Integrations that act on behalf of individual users (submitting an expense as that person, for example) use OAuth 2.0 instead. Contact **help@light.inc** to set up a client.

> **Security**: never put an API key in client-side code, a public repository or a shared document. Use environment variables or a secrets manager.

## Where to read next

- [Authentication](https://light.inc/docs/getting-started/authentication): API keys and OAuth, with request examples
- [Concepts](https://light.inc/docs/concepts/how-light-records-money): how Light keeps books, for readers who are not developers
- [Choosing an endpoint](https://light.inc/docs/concepts/choosing-an-endpoint): common jobs mapped to the calls that do them
- [Create an invoice payable](https://light.inc/docs/examples/create-invoice-payable): a worked example, end to end
- [API reference](https://light.inc/docs/api-reference): every endpoint, with notes on behaviour the specification leaves out

Developers and AI agents can read the same documentation as plain text, starting from [light.inc/docs/llms.txt](https://light.inc/docs/llms.txt).

## Connecting an AI assistant instead

If what you want is to ask questions of your Light data, or have an assistant draft entries for you to approve, you do not need the REST API. Light has an MCP server that Claude and other AI clients connect to directly, acting as you with your permissions. See [Connect your AI assistant to Light](https://light.inc/help/ai-features/how-to-use-light-mcp).

## Rate limits and support

The defaults are 300 requests a minute per user and 100,000 a day per organisation. Light can agree different limits with your company. The headers to watch and how to back off are in [Rate limits](https://light.inc/docs/getting-started/rate-limits).

For help with an integration, higher limits or OAuth setup, contact **help@light.inc**.

## Related articles

- [Integrations overview](https://light.inc/help/integrations/integrations-overview)
- [Connect your AI assistant to Light](https://light.inc/help/ai-features/how-to-use-light-mcp)
- [Data import and migration tools](https://light.inc/help/integrations/data-import)
