# API Access and Custom Integrations

Light's REST API covers integrations beyond the pre-built connectors. Use it to create and manage transactions, read your financial data, and automate accounting workflows from any system.

[Open API documentation →](https://docs.light.inc)

## What is this page about

This page covers how to authenticate against the Light API, which resources it exposes, how to create and query records, and the rate limits and error codes to build around. It assumes you are comfortable making HTTP requests and reading JSON.

**On this page**

- API overview
- Available API resources
- Authentication
- Creating transactions via API
- Querying data
- Rate limits
- Error handling
- Custom integration examples
- Troubleshooting
- API documentation and support
- Related articles

## API overview

The Light API is organised around REST and uses standard HTTP response codes, authentication, and verbs. Most endpoints accept and return JSON-encoded data in **camelCase** format. The base URL for all API requests is:

```javascript
https://api.light.inc
```

Some fields use enumerated (enum) values to represent specific states or types. Light documents these enums and may add new values over time, so handle unknown enum values gracefully rather than relying on exhaustive matching.

## Available API resources

The API provides endpoints for managing the following resources:

- **Accounting Documents**: list and query all accounting documents across types
- **Attachments**: upload, list, and manage document attachments
- **Authorization**: the OAuth 2.0 authorisation flow, rather than a queryable resource like the others. See Authentication below
- **Bank Accounts**: create and access bank accounts. Creating a bank account also creates its linked ledger account atomically
- **Card Balance Accounts**: access card balance accounts, statements, and total spend
- **Card Customers**: retrieve the card integration public key
- **Card Transactions**: list, post, and update card transactions and receipts
- **Cards**: create, freeze, unfreeze, and manage corporate cards
- **Companies**: access company configuration, such as currency settings
- **Contracts**: create, publish, renew, terminate, and manage contracts
- **Credit Notes**: create, list, and link credit notes to invoice payables
- **Custom Properties**: access custom property groups
- **Customer Credits**: manage customer credit documents
- **Customers**: create, list, activate, and archive customers
- **Entities**: list company entities
- **Exchange**: retrieve currency exchange rates
- **Expenses**: list expenses and submit reimbursements
- **Invoice Approvals**: retrieve invoice approval status
- **Invoice Payables**: create, approve, decline, mark as paid, and manage bills and their line items
- **Invoice Receivables**: create, update, open, reset, and send sales invoices
- **Journal Entries**: create journal entries programmatically
- **Ledger Transactions**: query ledger transaction lines
- **Ledger Accounts**: list the chart of accounts
- **Products**: manage your product catalogue
- **Purchase Orders**: create, close, cancel, and manage purchase orders and lines
- **User Comments**: create, list, and manage comments on records
- **Users**: list users, manage reimbursement configuration
- **Vendors**: create, list, update, and manage vendors

For full endpoint details, see the API Reference (click "API Reference" in the top navigation).

## Authentication

You can authenticate to the Light API using **API keys** or **OAuth 2.0**.

All API requests must be made over HTTPS. Calls made over plain HTTP will fail. Make sure your HTTP client follows redirects and forwards the `Authorization` header, as some endpoints may redirect to other URLs.

### API keys

To create an API key:

1. Log in to Light and navigate to **Settings > API Keys**
2. Click **Create key**
3. Copy the generated API key and store it securely, since Light shows it once

Light API keys are linked to roles the same way user accounts are. The roles assigned to the API key determine what actions the key can perform.

To authenticate with an API key, include the `Authorization` header using **Basic** authentication:

```javascript
Authorization: Basic YOUR_API_KEY
```

> **Security**: Never expose API keys in client-side code, public repositories, or shared documents. Use environment variables or a secrets manager.

### OAuth 2.0

For integrations that act on behalf of users, Light supports the OAuth 2.0 authorization code flow:

1. Contact Light support at **help@light.inc** to set up your account for OAuth 2.0
2. You'll receive a `client_id` and `client_secret`, and provide Light with your redirect URI
3. Initiate the flow by directing users to:

```javascript
https://api.light.inc/oauth/authorize?client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_REDIRECT_URI
```

1. After authorization, exchange the authorization code for an access token:

```javascript
curl -X POST https://api.light.inc/oauth/token \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=authorization_code&code=AUTHORIZATION_CODE&redirect_uri=YOUR_REDIRECT_URI&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET"
```

1. Use the returned access token in subsequent requests:

```javascript
Authorization: Bearer YOUR_ACCESS_TOKEN
```

The response also includes a `refresh_token` and `expires_in` value. When the access token expires, refresh it:

```javascript
curl -X POST https://api.light.inc/oauth/token \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=refresh_token&refresh_token=YOUR_REFRESH_TOKEN&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET"
```

Store your tokens securely and update the refresh token after each refresh, as the old one is invalidated.

For a full implementation example (Node.js/Express), see the OAuth Callback example in the API documentation.

## Creating transactions via API

A common use case is creating invoice payables (bills) from an external system.

**Example**: Create a bill in Light from your procurement system

```javascript
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

```javascript
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

The Light API enforces two rate limits. These are the standard defaults, and Light can agree different limits with your company:

- **300 requests per minute** per user. Every API key and OAuth token belonging to one user draws on that same allowance, so adding keys does not add capacity
- **100,000 requests per day** across your whole organisation, shared by all users, resetting at midnight UTC

Exceeding a limit returns a `429 Too Many Requests` response with these headers:

- `X-RateLimit-Limit`: maximum capacity
- `X-RateLimit-Remaining`: remaining capacity
- `X-RateLimit-Reset`: Unix timestamp when the limit resets
- `Retry-After`: recommended seconds to wait before retrying

Best practices for staying within limits: monitor `X-RateLimit-Remaining` before large operations, implement exponential backoff on retries, respect the `Retry-After` header, and spread scheduled jobs across different times.

If your use case requires higher limits, contact Light support at **help@light.inc**.

## Error handling

The API returns standard HTTP status codes:

- **200 OK**: request successful
- **400 Bad Request**: invalid request, such as malformed data or missing required fields
- **401 Unauthorized**: API credentials invalid or missing
- **403 Forbidden**: insufficient permissions for the requested action
- **404 Not Found**: resource not found
- **429 Too Many Requests**: rate limit exceeded, check the `Retry-After` header
- **500 Internal Server Error**: server error, contact Light support with the request details

## Custom integration examples

**Example 1: Procurement system to AP automation**

1. Procurement system approves a purchase
2. API creates an invoice payable via `POST /v1/invoice-payables` with vendor ID and amount
3. API adds line items via `POST /v1/invoice-payables/{id}/line-items`
4. Approval workflow triggers via `POST /v1/invoice-payables/{id}/approve`
5. Invoice enters Light's standard payment processing
6. (Optional) If you handle payment externally, record the payment via `POST /v1/invoice-payables/{id}/mark-as-paid` to close the bill in Light

**Example 2: CRM to invoicing**

1. CRM closes a deal and records the customer
2. API creates a customer via `POST /v1/customers` (or looks up existing via `GET /v1/customers`)
3. API creates an invoice via `POST /v1/invoice-receivables` with customer and line items
4. API opens the invoice via `POST /v1/invoice-receivables/{id}/open`
5. API sends the invoice email via `POST /v1/invoice-receivables/{id}/send-email`

**Example 3: Financial reporting dashboard**

1. Dashboard queries ledger accounts via `GET /v1/ledger-accounts`
2. Retrieves transaction lines via `GET /v1/ledger-transaction-lines` with date filters
3. Aggregates data for custom visualisations
4. Refreshes on a schedule, respecting rate limits

## Troubleshooting

**401 Unauthorized**: Verify your API key is correct and hasn't been revoked. Check that the `Authorization` header uses `Basic` scheme (for API keys) or `Bearer` scheme (for OAuth tokens).

**400 Bad Request**: Verify request JSON is valid and all required fields are provided. Check that amounts are in cents (integer) and IDs are valid UUIDs.

**403 Forbidden**: The API key's assigned role may not have permission for this action. Check role permissions in Settings > API Keys.

**429 Too Many Requests**: Implement exponential backoff and check the `Retry-After` header. Consider spreading requests over time.

**Redirect issues**: Ensure your HTTP client follows redirects and forwards the `Authorization` header to redirected URLs.

## API documentation and support

- **Full API reference**: [docs.light.inc](https://docs.light.inc), which includes endpoint details, request and response schemas, and code examples
- **Support**: Contact **help@light.inc** for API integration help or to request OAuth 2.0 setup or higher rate limits

## Related articles

- [Integrations overview](https://light.inc/help/integrations/integrations-overview)
- [Data import and migration tools](https://light.inc/help/integrations/data-import)
- [Data migration from E-Conomic](https://light.inc/help/integrations/migration-economic)
- [Data migration from QuickBooks](https://light.inc/help/integrations/migration-quickbooks)
