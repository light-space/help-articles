# Currency Settings

This article explains how currencies are configured in Light, including local currency setup on entities and FX-related account configuration.

[Open in Light →](https://app.light.inc/settings/entities)

## Understanding currency in Light

Light supports multi-currency accounting:

- **Base currency**: The company-wide reporting currency, set when your company is created (it cannot be changed afterwards)
- **Local currency**: Each company entity's operating currency, set during entity creation
- **Transaction currency**: The currency transactions are posted in (may differ from local currency)
- **Exchange rates**: Conversion rates between currencies for translation and revaluation. Light applies daily ECB rates by default; you can override these with [custom FX rates](/articles/02-organization-setup/2-10-custom-fx-rates-company), set daily or monthly

## Configuring local currencies for entities

Each entity has its own local currency, set when the entity is created:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click **+ Create entity** (for new entities) or click an existing entity and then **Edit**
3. Select the **Local currency** from the dropdown. This field is **required** — you can't save the entity without it, and there's no default
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

## Enable revaluation on an account

To include an account in period-end FX revaluation, turn on revaluation from its edit form.

1. Open [**Chart of accounts**](https://app.light.inc/accounting/ledger-accounts), then open the account you want to revalue
2. In the **FX settings** section, set **Entity revaluation settings** to **Revalue** (the other option is **Do not revalue**)
3. Set **Group revaluation settings** to the exchange rate type you want applied at group level
4. Click **Save**

Only accounts set to **Revalue** are picked up by the FX revaluation task below.

## Currency revaluation

At period end, Light revalues balances held in non-local currencies to current exchange rates and posts the difference as unrealized gain or loss:

1. Navigate to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods)
2. Click on the period you want to revalue
3. In the Tasks view, find the **FX revaluation** task
4. Click **Run revaluations**. If the task has already run for this period, the button reads **Re-run revaluations**

Light identifies every account set to **Revalue** that holds a non-local currency balance, calculates the unrealized gain or loss, and posts adjustment journal entries automatically.

**Before you can run this task, two things must already be done:**

- The **previous period's** FX revaluation task must be completed for all entities. If it isn't, you'll see: *"Fx revaluation tasks in previous periods are still not completed."* There's no way to force-run or skip this — the only fix is to go back and complete the earlier period's FX revaluation first.
- The current period's lock tasks (AP, AR, and JE) must also be completed. If they aren't, you'll see a separate error: *"Lock tasks for accounting period are still not completed."*

> Tip: Run FX revaluation before closing other period tasks, so your financial statements reflect current rates — but plan for the fact that periods must be revalued **in period order**; you can't skip ahead.

## Best practices

- Set each entity's local currency to match its primary operating country
- Configure FX account defaults before posting multi-currency transactions
- Run FX revaluation at every period close, **in period order** — you cannot revalue a period until the prior one's FX revaluation is complete
- Set **Entity revaluation settings** to **Revalue** on every balance sheet account that holds foreign currency balances
- Verify exchange rate accuracy before processing large transactions

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Setting a Custom FX Rate for Your Company](/articles/02-organization-setup/2-10-custom-fx-rates-company)
- [Setting a Custom FX Rate per Entity](/articles/02-organization-setup/2-11-custom-fx-rates-entity)
- [When Custom Rates Apply vs System Rates](/articles/02-organization-setup/2-12-custom-vs-system-fx-rates)

---

*Also searched as: why can't I change my local currency, is local currency required, FX loss and FX gain accounts, FX unrealized account, enable FX revaluation on an account, why is currency revaluation blocked, "Fx revaluation tasks in previous periods are still not completed," re-run revaluations, ECB exchange rates, custom FX rate.*
