# Currency Settings

This article explains how to configure local and group currencies, set up exchange rate sources, and manage multi-currency operations in Light.

[Open in Light →](https://app.light.inc/settings/entities)

## Understanding currency in Light

Light supports sophisticated multi-currency accounting:

- **Group Currency**: The primary currency for consolidated reporting (typically your parent company's currency)
- **Local Currency**: Each company entity's operating currency
- **Transaction Currency**: The currency transactions are posted in (may differ from local currency)
- **Exchange Rates**: Conversion rates between currencies for translation and revaluation

> Good to know: Light automatically handles currency conversions and can track multiple currencies per entity simultaneously.

## Setting the group currency

The group currency is your organization's reporting currency used for consolidated statements:

1. Navigate to **Settings (gear icon) → Organization settings** or **Settings (gear icon) → Entities**
2. Look for **Group Currency Configuration**
3. Select the **Group Currency** from the dropdown (e.g., USD, EUR)
4. Click **Save**

The group currency cannot be changed after initial setup. All entities will consolidate to this currency in group-level reporting.

## Configuring local currencies for entities

Each entity has its own local currency:

1. Go to **Settings (gear icon) → Entities**
2. Select the entity to configure
3. In **+ Create entity** or **Edit**, set the **Local Currency**
4. The local currency typically matches the entity's operating country
5. Click **Save**

The local currency is the default currency for all transactions at that entity. Transactions can be posted in alternative currencies with automatic conversion.

## Multi-currency transaction posting

When posting a transaction in a currency different from local:

1. Create a transaction (invoice, bill, journal entry)
2. In the **Currency** field, select the transaction currency
3. Light displays both:
   - **Transaction Amount**: In the selected currency
   - **Local Amount**: Automatically converted to entity's local currency
4. The system uses the current exchange rate for conversion
5. Post the transaction normally

Exchange rate differences are recorded to a gain/loss account designated in currency settings.

## Setting up exchange rate sources

Light automatically fetches exchange rates from configured sources:

1. Go to **Settings (gear icon) → Currency settings** or **Organization settings**
2. Click **Exchange Rate Configuration**
3. Select your **Rate Source**:
   - **ECB (European Central Bank)**: Daily rates covering all major currency pairs (default)
   - **Manual**: Upload rates yourself via CSV
   - **API Integration**: Real-time rates from financial data providers
4. Click **Save Configuration**

ECB rates are the default exchange rate source in Light. They are updated daily and cover all major currency pairs. Light uses ECB cross-rates to derive conversions between any two supported currencies. If using manual rates, upload a CSV file with date, from-currency, to-currency, and rate columns.

## Managing exchange rates

Navigate to Currency Settings → Exchange Rates to view historical and current rates by source. To upload manual rates, click Upload Rates and provide a CSV with Date, FromCurrency, ToCurrency, and Rate columns. When posting transactions, Light looks up rates by transaction date, uses the most recent rate if exact date unavailable, and locks rates once posted.

## Currency revaluation

At period end, Light can revalue balance sheet accounts to current exchange rates:

1. Navigate to **Accounting → Accounting periods** ([Open in Light →](https://app.light.inc/accounting/accounting-periods)) to manage period tasks
2. Select **FX_REVALUATION** task
3. Click **Execute**
4. Light identifies all accounts with transactions in non-local currencies
5. Calculates unrealized gain/loss to current rates
6. Creates adjustment journal entries to revalue accounts
7. Gain/loss entries are posted to designated FX revaluation accounts

> Tip: Execute FX revaluation before period closing to ensure financial statements reflect current rates.

## Multi-currency GL accounts

Accounts can track balances in multiple currencies:

1. Set up **Currency Codes** in each account record
2. When transactions are posted to the account in any currency, balances are maintained separately
3. Account reports show balances by currency with amounts for each
4. Consolidated reports convert all currencies to group currency using period-end rates

## Intercompany and reporting configuration

For multi-entity transactions, each entity uses its local currency; Light tracks conversion rates for consolidation. In Reporting Settings, set Display Currency to Local or Group, configure Rounding Rules, and specify Decimal Places to comply with jurisdiction requirements.

## Best practices

Keep group currency consistent for reliable consolidation. ECB daily rates work well as the default for most organizations. Verify rate accuracy before large transactions. Execute FX revaluation at every period close. Use multi-currency GL accounts for foreign currency balances. Document conversion policies. Test before going live and archive rates for audit purposes.

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
