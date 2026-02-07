# API Access and Custom Integrations

For integrations beyond Light's pre-built connectors, Light provides a REST API enabling custom integrations with any system. The API allows creating and managing transactions, accessing financial data, and automating accounting workflows.

[Open API documentation →](https://docs.light.inc)

## API overview

The Light API is organized around REST and uses standard HTTP response codes, authentication, and verbs. Most endpoints accept and return JSON-encoded data in **camelCase** format. The base URL for all API requests is:

```
https://api.light.inc
```

Some fields use enumerated (enum) values to represent specific states or types. While these enums are documented, they are not guaranteed to be exhaustive — new enum values may be introduced over time. To maintain forward compatibility, always handle unexpected or unknown enum values gracefully rather than relying on exhaustive matching.

## Available API resources

The API provides endpoints for managing the following resources:

- **Accounting Documents** — List and query all accounting documents across types
- **Attachments** — Upload, list, and manage document attachments
- **Authorization** — OAuth 2.0 token management
- **Bank Accounts** — Access bank account data
- **Card Transactions** — List, post, and update card transactions and receipts
- **Cards** — Create, freeze, unfreeze, and manage corporate cards
- **Companies** — Access company configuration (e.g., currency settings)
- **Contracts** — Create, publish, renew, terminate, and manage contracts
- **Credit Notes** — Create, list, and link credit notes to invoice payables
- **Custom Properties** — Access custom property groups
- **Customer Credits** — Manage customer credit documents
- **Customers** — Create, list, activate, and archive customers
- **Expenses** — List expenses and submit reimbursements
- **Invoice Approvals** — Retrieve invoice approval status
- **Invoice Payables** — Create, approve, decline, and manage bills and their line items
- **Invoices** — Create, update, open, reset, and send sales invoices
- **Journal Entries** — Create journal entries programmatically
- **Ledger Transactions** — Query ledger transaction lines
- **Ledger Accounts** — List the chart of accounts
- **Products** — Manage product catalog
- **Purchase Orders** — Create, close, cancel, and manage purchase orders and lines
- **User Comments** — Create, list, and manage comments on records
- **Users** — List users, manage reimbursement configuration
- **Vendors** — Create, list, update, and manage vendors

For full endpoint details, see the [API Reference](https://docs.light.inc) (click "API Reference" in the top navigation).

## Authentication

You can authenticate to the Light API using **API keys** or **OAuth 2.0**.

All API requests must be made over HTTPS. Calls made over plain HTTP will fail. Make sure your HTTP client follows redirects and forwards the `Authorization` header, as some endpoints may redirect to other URLs.

### API keys

To create an API key:

1. Log in to Light and navigate to **Settings > API Keys**
2. Click **Create Key**
3. Copy and securely store the generated API key — it will not be shown again

Light API keys are linked to roles the same way user accounts are. The roles assigned to the API key determine what actions the key can perform.

To authenticate with an API key, include the `Authorization` header using **Basic** authentication:

```
Authorization: Basic YOUR_API_KEY
```

> **Security**: Never expose API keys in client-side code, public repositories, or shared documents. Use environment variables or a secrets manager.

### OAuth 2.0

For integrations that act on behalf of users, Light supports the OAuth 2.0 authorization code flow:

1. Contact Light support at **support@light.inc** to set up your account for OAuth 2.0
2. You'll receive a `client_id` and `client_secret`, and provide Light with your redirect URI
3. Initiate the flow by directing users to:

```
https://api.light.inc/oauth/authorize?client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_REDIRECT_URI
```

4. After authorization, exchange the authorization code for an access token:

```
curl -X POST https://api.light.inc/oauth/token \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=authorization_code&code=AUTHORIZATION_CODE&redirect_uri=YOUR_REDIRECT_URI&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET"
```

5. Use the returned access token in subsequent requests:

```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

The response also includes a `refresh_token` and `expires_in` value. When the access token expires, refresh it:

```
curl -X POST https://api.light.inc/oauth/token \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=refresh_token&refresh_token=YOUR_REFRESH_TOKEN&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET"
```

Store your tokens securely and update the refresh token after each refresh, as the old one is invalidated.

For a full implementation example (Node.js/Express), see the [OAuth Callback example](https://docs.light.inc/examples/oauth-callback) in the API documentation.

## Creating transactions via API

A common use case is creating invoice payables (bills) from an external system.

**Example**: Create a bill in Light from your procurement system

```
curl -X POST https://api.light.inc/v1/invoice-payables \
  -H "Authorization: Basic YOUR_API_KEY" \
  -H "Content-Type: application/json;charset=UTF-8" \
  -d '{
    "vendorId": "3c90c3cc-0d44-4b50-8888-8dd25736052a",
    "amount": 100000,
    "currency": "USD"
  }'
```

Note that amounts are specified in **cents** (e.g., 100000 = $1,000.00). Light creates the invoice payable and returns its ID and metadata.

You can also create sales invoices, journal entries, purchase orders, and other document types through their respective endpoints.

## Querying data

Retrieve existing records using GET endpoints with sorting, filtering, and pagination:

**Example**: List accounting documents sorted by date

```
curl -X GET "https://api.light.inc/v1/accounting-documents/accounting-documents?sort=documentDate:desc&limit=50" \
  -H "Authorization: Basic YOUR_API_KEY"
```

### Sorting

Sort using the format `field:direction`. Separate multiple sort fields with commas.

Available directions: `asc`, `desc`

Example: `sort=amount:desc,createdAt:asc`

### Filtering

Filter using the format `field:operator:value`. Separate multiple filters with commas.

Available operators: `eq`, `ne`, `in`, `not_in`, `gt`, `gte`, `lt`, `lte`

For `in` and `not_in` operators, separate multiple values with the pipe character (`|`).

Example: `filter=state:in:IN_DRAFT|SCHEDULED|PAID,amount:gte:500,vendorId:ne:null`

### Pagination

Results are paginated. Use the `limit` parameter to control page size (default: 50, maximum: 200). For cursor-based pagination, provide `0` as the cursor for the initial request.

## Rate limits

The Light API enforces two rate limits:

- **300 requests per minute** per API key or OAuth token (applied individually to each user in your organization)
- **100,000 requests per day** per organization (resets at midnight UTC, shared across all users)

Exceeding a limit returns a `429 Too Many Requests` response with these headers:

- `X-RateLimit-Limit` — Maximum capacity
- `X-RateLimit-Remaining` — Remaining capacity
- `X-RateLimit-Reset` — Unix timestamp when the limit resets
- `Retry-After` — Recommended seconds to wait before retrying

Best practices for staying within limits: monitor `X-RateLimit-Remaining` before large operations, implement exponential backoff on retries, respect the `Retry-After` header, and spread scheduled jobs across different times.

If your use case requires higher limits, contact Light support at **support@light.inc**.

## Error handling

The API returns standard HTTP status codes:

- **200 OK** — Request successful
- **400 Bad Request** — Invalid request (malformed data or missing required fields)
- **401 Unauthorized** — API credentials invalid or missing
- **403 Forbidden** — Insufficient permissions for the requested action
- **404 Not Found** — Resource not found
- **429 Too Many Requests** — Rate limit exceeded (check `Retry-After` header)
- **500 Internal Server Error** — Server error (contact Light support with request details)

## Custom integration examples

**Example 1: Procurement system to AP automation**

1. Procurement system approves a purchase
2. API creates an invoice payable via `POST /v1/invoice-payables` with vendor ID and amount
3. API adds line items via `POST /v1/invoice-payables/{id}/line-items`
4. Approval workflow triggers via `POST /v1/invoice-payables/{id}/approve`
5. Invoice enters Light's standard payment processing

**Example 2: CRM to invoicing**

1. CRM closes a deal and records the customer
2. API creates a customer via `POST /v1/customers` (or looks up existing via `GET /v1/customers`)
3. API creates an invoice via `POST /v1/invoices` with customer and line items
4. API opens the invoice via `POST /v1/invoices/{id}/open`
5. API sends the invoice email via `POST /v1/invoices/{id}/send-email`

**Example 3: Financial reporting dashboard**

1. Dashboard queries ledger accounts via `GET /v1/ledger-accounts`
2. Retrieves transaction lines via `GET /v1/ledger-transactions/lines` with date filters
3. Aggregates data for custom visualizations
4. Refreshes on a schedule, respecting rate limits

## Troubleshooting

**401 Unauthorized**: Verify your API key is correct and hasn't been revoked. Check that the `Authorization` header uses `Basic` scheme (for API keys) or `Bearer` scheme (for OAuth tokens).

**400 Bad Request**: Verify request JSON is valid and all required fields are provided. Check that amounts are in cents (integer) and IDs are valid UUIDs.

**403 Forbidden**: The API key's assigned role may not have permission for this action. Check role permissions in Settings > API Keys.

**429 Too Many Requests**: Implement exponential backoff and check the `Retry-After` header. Consider spreading requests over time.

**Redirect issues**: Ensure your HTTP client follows redirects and forwards the `Authorization` header to redirected URLs.

## API documentation and support

- **Full API reference**: [docs.light.inc](https://docs.light.inc) — includes endpoint details, request/response schemas, and code examples
- **Support**: Contact **support@light.inc** for API integration help or to request OAuth 2.0 setup or higher rate limits

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Data import and migration tools](11-13-data-import.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
