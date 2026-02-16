# Airwallex Integration

Airwallex is a global fintech platform enabling multi-currency payments, virtual accounts, and financial operations for international businesses. Light integrates with Airwallex to enable outgoing payments directly from your Airwallex virtual bank accounts.

[Open in Light →](https://app.light.inc/settings/integrations)

> **No fees from Light**: Light does not charge any integration or transaction fees for the Airwallex integration. Additional fees from Airwallex may apply — see the [Airwallex pricing page](https://www.airwallex.com/eu/pricing) for details.

## Integration capabilities

The Airwallex integration enables:

- **Outgoing payments**: Make domestic and international (SWIFT) payments from your Airwallex virtual bank accounts
- **Bank account linking**: Connect one or more Airwallex bank accounts to Light, each mapped by currency
- **Payment status tracking**: Light automatically checks for payment status updates every 15 minutes

## Prerequisites

Before connecting Airwallex to Light, you'll need:

1. An active Airwallex account
2. Your Client ID and API Key from the Airwallex dashboard (see [Airwallex documentation](https://www.airwallex.com) for how to retrieve them)
3. At least one Airwallex bank account created in Light

To create an Airwallex bank account in Light:

1. Navigate to **Settings (gear icon) → Bank accounts**
2. Click **+ Add account**
3. Fill in only the following fields:
   - **Entity**: The entity owning the bank account
   - **Bank Country**: The country of the bank account
   - **Name**: The display name shown when selecting a bank account
   - **Bank provider**: Must be set to `Airwallex`
   - **Currency**: Must match the currency of the corresponding Airwallex account balance
4. Click **Add**

## Setting up Airwallex integration

To connect Airwallex:

1. Navigate to **Settings (gear icon) → Integrations → Add Integration → Airwallex**
2. In the connection dialog, enter:
   - **Client ID**: Found in your Airwallex dashboard
   - **API Key**: Found in your Airwallex dashboard

> **Important**: Make sure to use account-level credentials, not organization-level credentials.

3. Under **Bank Accounts**, select the Light bank accounts you want to link to this Airwallex connection:
   - You can add one bank account per currency
   - Use the toggle to set each bank account as active or inactive
   - Click **+ Add another bank account** to link additional accounts
4. Click **Create** to save the connection

Once connected, Light validates your credentials against Airwallex and your connection is ready for use.

## Managing your connection

### Viewing connections

Navigate to **Settings (gear icon) → Integrations → Airwallex** to view all your Airwallex connections.

### Updating a connection

To change your API key (for example, when rotating keys) or modify bank account mappings:

1. Navigate to **Settings (gear icon) → Integrations → Airwallex** and select the desired connection
2. To update the API key, click the **Update** icon, enter the new API key in the dialog, and click **Save Changes**
3. To change bank account mappings, add or remove mappings as needed, then click **Save Changes**

### Disabling a bank account

To temporarily stop payments from a specific bank account without removing the connection entirely:

1. Toggle the bank account to **Inactive**
2. Click **Save Changes**

This blocks new payments, including scheduled payments that haven't reached their payment date, while preserving the connection for historical records. You can reactivate the account at any time by toggling it back to **Active**.

> **Note**: If a bank account is disabled immediately after a payment is executed, Light cannot retrieve the status of that payment (whether it succeeded or failed) since the connection has been disabled.

### Deleting a connection

To remove an Airwallex connection entirely:

1. Navigate to **Settings (gear icon) → Integrations → Airwallex** and select the desired connection
2. Click **Delete Connection**
3. Confirm the deletion by clicking **Delete** in the dialog

This removes all bank account mappings associated with that connection. The same considerations for disabling a bank account apply: new payments are blocked and the status of still-executing payments cannot be retrieved.

## Making payments

In the bill payment details page, select the Airwallex connection from the **Pay from Account** dropdown to initiate a payment through Airwallex.

### Payment status

Once a payment is initiated through Airwallex, Light automatically checks for status updates every 15 minutes.

## Fees

Light does not charge any integration fees or transaction fees for this integration. For information on Airwallex pricing, including transaction fees and other applicable charges, refer directly to the [Airwallex pricing page](https://www.airwallex.com/eu/pricing).

## Troubleshooting

**"Invalid credentials" error**: Verify your Client ID and API Key are correct in the Airwallex dashboard. Ensure your API key has not expired or been revoked.

**"Bank account not valid" error**: The bank account must be set up as a virtual bank account with Airwallex as the provider. Contact support if you need help configuring bank accounts.

**"Country mismatch" error**: Your company entity country must match one of the countries configured in your Airwallex account. Check your entity settings in Light or your Airwallex account configuration.

**Payments not processing**: Verify the bank account mapping is set to active (toggle is on). Check that your Airwallex account has sufficient funds. Ensure beneficiary details are valid.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Bank integrations overview](11-11-bank-integrations.md)
- [Stripe integration](11-6-stripe.md)
- [Multi-currency revenue recognition](../09-revenue-compliance/9-4-multi-currency-revenue.md)
