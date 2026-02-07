# API Access and Custom Integrations

For integrations beyond Light's pre-built connectors, Light provides a comprehensive REST API enabling custom integrations with any system. The API allows reading and writing transactions, accessing reports, and automating accounting workflows.

[Open in Light →](https://app.light.inc/settings/integrations)

## API overview

Light's API provides:

- **Transaction creation**: Create AP, AR, JE, FX documents programmatically
- **Transaction queries**: Search and retrieve transactions by criteria
- **Report access**: Retrieve financial reports (balance sheet, P&L, trial balance)
- **Master data**: Access and update customers, vendors, employees, chart of accounts
- **Batch operations**: Create multiple transactions in a single API call
- **Webhooks**: Receive real-time notifications of accounting events

This enables unlimited custom integrations.

## API authentication

Light uses OAuth for API authentication:

1. Create API credentials in **Settings (gear icon) > API > Credentials**
2. Generate API key and secret
3. Store credentials securely (never commit to code)
4. Use credentials to authenticate API requests

OAuth is industry standard and secure.

> Security: Never expose API credentials. Use environment variables, secure vaults, or managed secrets services.

## Creating transactions via API

Common use case: Create AR invoices from external system

**Example**: Your e-commerce platform wants to create invoices in Light

```
POST /api/v1/accounting/invoices
Content-Type: application/json
Authorization: Bearer [API_TOKEN]

{
  "customerName": "Acme Corp",
  "amount": 10000,
  "currency": "USD",
  "postingDate": "2025-02-07",
  "lineItems": [
    {
      "description": "Product A",
      "quantity": 10,
      "unitPrice": 1000,
      "ledgerAccountId": "[UUID]"
    }
  ]
}
```

Light creates the invoice and returns its ID, ready for posting.

## Querying transactions

Retrieve existing transactions from Light:

**Example**: Get all invoices for a customer

```
GET /api/v1/accounting/invoices?customer=Acme&status=POSTED
Authorization: Bearer [API_TOKEN]
```

Light returns array of matching invoices with full detail.

## Accessing financial data

Retrieve reports and GL data:

**Example**: Get balance sheet as of date

```
GET /api/v1/reporting/balance-sheet?asOfDate=2025-01-31
Authorization: Bearer [API_TOKEN]
```

Light returns balance sheet data in structured format.

## Batch operations

Create multiple transactions efficiently:

**Example**: Post 100 customer payments at once

```
POST /api/v1/accounting/batch
Content-Type: application/json
Authorization: Bearer [API_TOKEN]

{
  "operations": [
    { "type": "create_receipt", "data": {...} },
    { "type": "create_receipt", "data": {...} },
    ...
  ]
}
```

Light processes in batch, faster than individual requests.

## Webhooks for real-time events

Receive notifications of accounting events:

1. Navigate to **Settings (gear icon) > API > Webhooks**
2. Configure webhook endpoint (your API receiving Light events)
3. Select events you want to be notified of:
   - Invoice created
   - Invoice posted
   - Payment received
   - Report generated
4. When event occurs, Light sends POST to your endpoint

This enables real-time reaction to accounting events.

**Example webhook payload**:

```json
{
  "eventType": "invoice.posted",
  "timestamp": "2025-02-07T10:30:00Z",
  "data": {
    "invoiceId": "[UUID]",
    "customer": "Acme Corp",
    "amount": 10000,
    "status": "POSTED"
  }
}
```

Your system receives this and can take immediate action.

## Rate limiting

Light API has rate limits to prevent abuse:

- **10,000 requests per hour** per API key
- **100 requests per minute** burst limit
- Exceeding limit returns 429 (Too Many Requests)
- Implement exponential backoff when rate limited

Check rate limit headers in API responses.

## Error handling

API returns standard HTTP status codes:

- **200 OK**: Request successful
- **400 Bad Request**: Invalid request (malformed data)
- **401 Unauthorized**: API credentials invalid or missing
- **403 Forbidden**: Insufficient permissions
- **404 Not Found**: Resource not found
- **429 Too Many Requests**: Rate limit exceeded
- **500 Internal Server Error**: Light error (rare)

Include error handling in your integration.

## Custom integration examples

**Example 1: Project management to timesheet to invoicing**

1. Project management system tracks project hours
2. API reads completed project hours
3. Aggregates hours by customer
4. Creates AR invoice with line items by project
5. Posts invoice to GL

This automates invoice creation from project data.

**Example 2: Accounting software migration**

1. Old accounting system exports GL and transactions
2. Custom script uses Light API to recreate chart of accounts
3. Script recreates historical transactions
4. Script posts opening balances
5. Migration complete, old system retired

This enables data migration to Light.

**Example 3: Real-time expense alerts**

1. Expense management system processes expenses
2. Expenses sync to Light via API
3. Light webhook notifies management system of posting
4. Alert triggered if expense violates policy
5. Manager approves or rejects in real-time

This creates real-time expense controls.

## API documentation

Comprehensive API documentation is available at:

`https://docs.light.com/api/`

Documentation includes:

- Full endpoint reference
- Request/response examples
- Error codes and meanings
- Authentication methods
- Rate limiting policies
- SDK availability (JavaScript, Python, Go)

## SDKs and client libraries

Light provides SDKs to simplify integration:

**Official SDKs**:
- JavaScript/Node.js
- Python
- Go
- Java

**Community SDKs**:
- C#/.NET
- Ruby
- PHP

Use SDKs to reduce boilerplate and handle authentication automatically.

## API access control

Control who can access the API:

1. Navigate to **Settings (gear icon) > API > Access Control**
2. Create API credentials for each integration
3. Assign permissions:
   - Read-only (can't create/modify)
   - Read/Write (can create and modify)
   - Webhook-only (can only receive events)
4. Revoke credentials for old integrations
5. Monitor API usage by credential

This maintains security and auditability.

## Testing API integration

Before going live:

1. Use Light's test/sandbox environment
2. Create test data
3. Test API requests
4. Verify data appears correctly in Light
5. Test error scenarios
6. Once confident, move to production

This prevents production data issues.

## Monitoring API performance

Track API usage:

1. Navigate to **Settings (gear icon) > API > Usage Analytics**
2. View:
   - Number of API calls (by endpoint, by credential)
   - Average response time
   - Error rates
   - Peak usage times
3. Optimize based on patterns

This helps identify bottlenecks or errors.

## API rate limiting and optimization

When integrating large data volumes:

1. Use batch operations (100-1000 records per batch)
2. Schedule heavy operations during off-peak times
3. Implement caching to avoid redundant queries
4. Use filtering to retrieve only necessary data
5. Monitor rate limit headers to stay within limits

This ensures smooth integration performance.

## Webhook security

Secure your webhook endpoints:

1. Use HTTPS only (no HTTP)
2. Validate webhook signature (Light includes signature header)
3. Implement request timeout (if slow processing needed, queue asynchronously)
4. Log all webhooks for audit trail
5. Test webhook delivery (Light provides test webhook feature)

This prevents unauthorized webhook calls.

## Troubleshooting API issues

**Connection refused**: Verify API endpoint URL is correct, check firewall allows outbound connections.

**401 Unauthorized**: Verify API credentials are correct, check if credentials have been revoked.

**400 Bad Request**: Verify request JSON is valid, check required fields are provided.

**429 Too Many Requests**: Implement exponential backoff, reduce request frequency.

**500 Internal Server Error**: Contact Light support with request details.

## API support and resources

For help with API integration:

- **API documentation**: https://docs.light.com/api/
- **Community forum**: https://community.light.com/api-integrations
- **Support ticket**: Create support request in Light
- **Office hours**: Weekly developer office hours (timezone rotating)

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Data import and migration tools](11-13-data-import.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
