# Currency Settings

This article explains how currencies are configured in Light, including local currency setup on entities and FX-related account configuration.

[Open in Light →](https://app.light.inc/settings/entities)

## Understanding currency in Light

Light supports multi-currency accounting:

- **Local currency**: Each company entity's operating currency, set during entity creation
- **Transaction currency**: The currency transactions are posted in (may differ from local currency)
- **Exchange rates**: Conversion rates between currencies for translation and revaluation

## Configuring local currencies for entities

Each entity has its own local currency, set when the entity is created:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click **+ Create entity** (for new entities) or click an existing entity and then **Edit**
3. Select the **Local currency** from the dropdown
4. Click **Create** or **Save**

The local currency is the default currency for all transactions at that entity. Transactions can be posted in alternative currencies with automatic conversion.

> Good to know: Local currency cannot be changed after entity creation. If you need to change it, you'll need to create a new entity.

## FX account configuration

Light uses designated accounts for foreign exchange gains, losses, and revaluations. These are configured in the [**Account defaults**](https://app.light.inc/accounting/ledger-accounts) tab:

1. Go to [**Accounting → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Click the **Account defaults** tab
3. Configure the following FX-related accounts:
   - **FX loss**: Account for realized foreign exchange losses
   - **FX gain**: Account for realized foreign exchange gains
   - **FX unrealized**: Account for unrealized FX gains and losses
   - **Currency translation adjustment**: Account for currency translation differences
   - **Rounding**: Account for rounding gain/loss on currency conversions

These accounts receive the gain/loss entries generated during currency conversions and period-end revaluations.

## Currency revaluation

At period end, Light can revalue balance sheet accounts to current exchange rates through the FX revaluation closing task:

1. Navigate to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods)
2. Click on the period you want to revalue
3. In the Tasks view, find the **FX revaluation** task
4. Click **Run revaluations**
5. Light identifies all accounts with transactions in non-local currencies, calculates unrealized gain/loss, and creates adjustment journal entries

> Tip: Run FX revaluation before closing other period tasks to ensure financial statements reflect current rates.

## Multi-currency accounts

Accounts can be configured to track foreign currency transactions. When creating or editing an account in the [Chart of accounts](https://app.light.inc/accounting/ledger-accounts), check the **Revalue open balance for foreign currency transactions** checkbox to enable automatic FX revaluation for that account.

## Best practices

- Set each entity's local currency to match its primary operating country
- Configure FX account defaults before posting multi-currency transactions
- Run FX revaluations at every period close
- Enable the revalue checkbox on balance sheet accounts that hold foreign currency balances
- Verify exchange rate accuracy before processing large transactions

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
