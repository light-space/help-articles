# Currency Setting

> **What is this page about:** How to set up currencies in Light, from base and local currency rules to configuring FX accounts and running period-end revaluation.

[Open in Light →](https://app.light.inc/settings/entities)

## On this page

- Understanding currency in Light
- Set an entity's local currency
- Configure FX accounts in Light
- Enable revaluation on an account
- Run currency revaluation
- Best practices

## Understanding currency in Light

- **Base currency**: your company's reporting currency, set when the company is created. It cannot be changed afterwards.
- **Local currency**: each entity's operating currency, set when the entity is created. It cannot be changed afterwards. To use a different currency, create a new entity.
- **Transaction currency**: the currency a transaction posts in. It can differ from the entity's local currency, and Light converts it automatically.
- **Exchange rates**: Light applies daily ECB rates by default. You can override these with custom rates, set daily or monthly.

## Set an entity's local currency

Each entity's local currency is fixed at creation, so confirm it before saving.

1. Go to **Settings**.
2. Open **Entities**.
3. Click **+ Create entity** for a new entity.
4. Select the currency from the **Local currency** dropdown. This field is **required** — you can't save the entity without it, and there's no default.
5. Click **Create** or **Save**.

## Configure FX accounts

Light posts foreign exchange gains, losses, and revaluation entries to accounts you designate. Set these up before posting multi-currency transactions.

1. Click the gear icon at the bottom of the left sidebar.
2. Open **Settings**.
3. Under **Records**, open **Chart of accounts**.
4. Click the **Account defaults** tab.
5. Set an account for each of the following:
   - **FX loss**: realised foreign exchange losses.
   - **FX gain**: realised foreign exchange gains.
   - **FX unrealized**: unrealised FX gains and losses.
   - **Currency translation adjustment**: currency translation differences.
   - **Rounding**: rounding gain or loss on currency conversions.

## Enable revaluation on an account

To include an account in period-end FX revaluation, turn on revaluation from its edit form.

1. Open **Chart of accounts**, then open the account you want to revalue.
2. In the **FX settings** section, set **Entity revaluation settings** to **Revalue** (the other option is **Do not revalue**).
3. Set **Group revaluation settings** to the exchange rate type you want applied at group level.
4. Click **Save**.

Only accounts set to **Revalue** are picked up by the FX revaluation task below.

## Run currency revaluation

At period end, Light revalues balances held in non-local currencies to current exchange rates and posts the difference as unrealised gain or loss.

1. Go to **Accounting**.
2. Open **Accounting periods**.
3. Open the period you want to revalue.
4. In the **Tasks** view, find **FX revaluation**.
5. Click **Run revaluations**. If the task has already run for this period, the button reads **Re-run revaluations**.

Light identifies every account set to **Revalue** that holds a non-local currency balance, calculates the unrealised gain or loss, and posts adjustment journal entries automatically.

**Before you can run this task, two things must already be done:**

- The **previous period's** FX revaluation task must be completed for all entities. If it isn't, you'll see: *"Fx revaluation tasks in previous periods are still not completed."* There's no way to force-run or skip this — the only fix is to go back and complete the earlier period's FX revaluation first.
- The current period's lock tasks (AP, AR, and JE) must also be completed. If they aren't, you'll see a separate error: *"Lock tasks for accounting period are still not completed."*

Run FX revaluation before closing other period tasks, so your financial statements reflect current rates — but plan for the fact that periods must be revalued **in order**; you can't skip ahead.

## Best practices

- Match each entity's local currency to its primary operating country.
- Set up FX account defaults before posting multi-currency transactions.
- Run FX revaluation at every period close, **in period order** — you cannot revalue a period until the prior one's FX revaluation is complete.
- Set **Entity revaluation settings** to **Revalue** on every balance sheet account that holds foreign currency balances.
- Check exchange rate accuracy before processing large transactions.

## Related articles

- [Managing Entities](https://help.light.inc/organization-setup/managing-entities)
- [Chart of Accounts Setup](https://help.light.inc/organization-setup/chart-of-accounts)
- [Fiscal Year and Accounting Periods](https://help.light.inc/organization-setup/fiscal-year-periods)
- [Tax and VAT Configuration](https://help.light.inc/organization-setup/tax-vat-configuration)
- [Setting a Custom FX Rate for Your Company](https://help.light.inc/organization-setup/custom-fx-rates-company)
- [Setting a Custom FX Rate per Entity](https://help.light.inc/organization-setup/custom-fx-rates-entity)
- [When Custom Rates Apply vs System Rates](https://help.light.inc/organization-setup/custom-vs-system-fx-rates)

---

*Also searched as: why can't I change my local currency, is local currency required, FX loss and FX gain accounts, FX unrealized account, enable FX revaluation on an account, why is currency revaluation blocked, "Fx revaluation tasks in previous periods are still not completed," re-run revaluations, ECB exchange rates, custom FX rate.*
