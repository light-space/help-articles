# FX Revaluations

Foreign exchange (FX) revaluation adjusts your GL account balances to reflect current exchange rates. In Light, FX revaluation is a required step in the period-end close process and is run on a per-entity basis. This article also explains the wider currency framework it sits in — how Light stores currencies, sources rates, and translates balances for consolidation.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## How Light handles foreign currency

Light maintains a **three-tier currency model** on every ledger transaction line:

| Tier | What it is | Set at |
| --- | --- | --- |
| **Transaction currency** | The currency a document was actually transacted in (e.g. a USD vendor bill). Present only when it differs from the local currency. | Per document |
| **Local (functional) currency** | The functional currency of the legal entity. | Per entity (cannot be changed after the entity is created) |
| **Group (presentation) currency** | The reporting currency used for consolidation. | Per company (group) |

Every posted line stores its amount in all three currencies at the same time — local and group are always populated, transaction currency where applicable — together with the debit/credit sign. This means the functional-currency and group-currency view of each transaction is fixed and auditable at the moment it posts.

## Understanding FX Revaluation

FX revaluation addresses the mismatch between when a transaction is recorded and when it settles.

**Example:**
- You invoice an AR customer for 100,000 EUR on January 1 at a rate of 1.20 USD/EUR = 120,000 USD
- You post 120,000 USD to your receivable in the GL
- By January 31 (period-end), the rate has moved to 1.18 USD/EUR
- The receivable is now worth 118,000 USD at the new rate
- Unrealized loss: 120,000 - 118,000 = 2,000 USD

FX revaluation entries record this unrealized gain or loss and adjust GL balances to reflect current exchange rates at period-end.

## Exchange Rate Sources and Governance

Light sources exchange rates from two providers:

- **European Central Bank (ECB)** — The primary source, providing daily reference rates that are ingested automatically.
- **OpenExchangeRates** — A commercial provider used for currency pairs not published by the ECB, ensuring coverage for less common currencies.

How rates are stored and resolved:

- **EUR pivot.** All rates are stored against EUR (currency → EUR). Cross-rates between two non-EUR currencies are derived arithmetically — for example, USD→GBP = USD→EUR ÷ GBP→EUR.
- **Dual dates.** Each rate is held with both its effective (market) date and the date it was ingested.
- **Non-trading days.** A request for a date with no published rate resolves to the most recent prior effective rate — for example, a Monday with no rate uses the preceding Friday.

### Rate overrides

You can override system rates instead of using market rates:

- **Override scope and precedence.** Overrides resolve in the order **entity → company → system**, and are available at daily or monthly granularity. **Document-level** rate overrides take the highest precedence — on an AP, AR, or JE document, open the **FX Rates** section and toggle **Override Local Currency Rate** or **Override Group Currency Rate** to set the entity or group conversion explicitly.
- **No hybrid cross-rates.** If only one leg of a required currency pair has an override, Light discards the override and falls back to system rates for *both* legs — a derived cross-rate is never built from mismatched sources. To be sure your custom rates apply everywhere, set a rate for every non-EUR currency you transact in, each month.

For setting your own rates, see [Setting a Custom FX Rate for Your Company](/articles/02-organization-setup/2-10-custom-fx-rates-company) and [When Custom Rates Apply vs System Rates](/articles/02-organization-setup/2-12-custom-vs-system-fx-rates).

## How Rates Are Applied by Account Type

Light assigns each ledger account an exchange-rate type derived automatically from the account's classification. This is the key control behind which balances move at period-end:

| Account classification | Rate applied | Re-translated each period? |
| --- | --- | --- |
| **Asset, Liability** | End-of-month (closing) rate | **Yes** — through period-end revaluation |
| **Equity** | Historical rate | No — locked at the original posting rate |
| **Revenue, Expense** | Historical rate (transaction date) | No — locked at the original posting rate |

This implements the standard **monetary / non-monetary distinction**: monetary balance-sheet items are carried at the closing rate, while equity and income-statement items are held at the historical rate at which they were recognized. The difference that arises between closing-rate balance-sheet items and historical-rate equity/P&L is captured as the cumulative translation adjustment (see below).

> **Note on income and expenses:** Light translates income and expenses at the actual transaction-date (spot) rate of each item, **not** at a period-average rate. Under IAS 21 this is the **preferred basis** — the standard requires the spot rate at the date of each transaction and only permits a period-average rate as a practical approximation (and not at all when rates fluctuate significantly). Light applies the actual rate per item, so it is more precise than an average-rate method rather than a deviation from it; auditors expecting average-rate P&L translation should simply note the difference in approach.

## What gets revalued

A revaluation is defined by two things: **which balances** are revalued (the *population*) and **which currency layer** the difference lands in (the *dimension*). Light keeps these separate.

### Open items (AP / AR and accruals)

Open or partially-cleared payable and receivable documents, plus released accrual lines that are still open at period end. These are revalued **per document or accrual line** at the period-end closing rate, with a link back to the source invoice/line for traceability.

### Monetary accounts (bank, cash, etc.)

Balance-sheet accounts you set to revalue — bank, cash, and other monetary accounts. These are revalued **per account and currency** at the closing rate, based on the account's open foreign-currency balance.

### Local entity FX (functional-currency revaluation)

The transaction → local dimension. Light brings the open foreign-currency balance to the period-end closing rate in the **entity's functional (local) currency** and posts the offset to the **unrealized FX gain/loss** account. This is the gain or loss that appears in the entity's own books. It is controlled per account by the **Entity revaluation settings** dropdown described below.

### Group FX (presentation-currency translation → CTA)

The local → group dimension. Light re-translates the local-currency balance to the **group (presentation) currency** at the closing rate and posts the offset to the **CTA** account. On a CTA posting the **local-currency amount is nil** — by design it adjusts only the group-currency balance, because it represents the translation-only difference between functional and presentation currency. It is controlled per account by the **Group revaluation settings** dropdown; an account set to *Historical* generates **no** CTA.

## Setting FX behaviour per account

Each ledger account has an **FX settings** section with two dropdowns that control how the account behaves at period-end. Set them when creating or editing an account in **Accounting → Chart of accounts**:

| Setting | Options | What it does |
| --- | --- | --- |
| **Entity revaluation settings** | *Do not revalue* / *Revalue for entity* | *Revalue for entity* revalues the account's open foreign-currency balances into the entity's functional (local) currency at period-end, posting unrealized FX gain/loss. *Do not revalue* leaves the balance at its booked local amount. |
| **Group revaluation settings** | *End of period* / *Historical* | *End of period* carries the account at the closing (end-of-period) rate and generates **CTA** on the local→group difference. *Historical* keeps it at the original posting rate, so **no CTA** is posted. |

To configure an account:

1. Go to **Accounting → Chart of accounts** ([open Chart of accounts](https://app.light.inc/accounting/ledger-accounts))
2. Click **+ Create account**, or open an existing account and click **Edit**
3. In the **FX settings** section, set **Entity revaluation settings** and **Group revaluation settings**
4. Click **Save**

**Typical settings by account type** (these follow the account classification described above):

- **Monetary assets & liabilities** (AR, AP, bank, cash, intercompany): **Entity revaluation settings** = *Revalue for entity*, **Group revaluation settings** = *End of period* — revalued at the closing rate and translated to group with CTA.
- **Equity**: *Do not revalue* + *Historical* — held at the original rate, no CTA.
- **Revenue & expense**: *Do not revalue* + *Historical* — held at the transaction-date rate, no CTA.

## Transaction-Level Conversion (at posting)

When a document is posted, Light fetches the rates effective on the posting date and computes the amounts for every line:

- transaction currency → local currency, and
- local currency → group currency.

These amounts are persisted on the line, and the **source of each rate** (system, company override, entity override, or document override) is recorded — giving a complete audit trail of the rate applied to every posting.

## Realized FX (at settlement)

Realized FX gains and losses are recognized when an open foreign-currency item (such as an AP or AR invoice) is cleared or settled. Light computes the difference between:

- the item's value at the original posting-date rate, and
- its value at the clearing-date rate,

and posts the difference to the system **FX gain** / **FX loss** accounts. Where the local-to-group conversion also differs, the group-only component is posted to the **CTA** account. Sub-unit rounding differences arising from the three-currency conversion are isolated to a dedicated **rounding** account, so the double entry stays balanced in all three currencies.

**Example:**
- AR revalued: Owed 100,000 EUR, revalued to 118,000 USD at period-end
- Customer pays: Sends 100,000 EUR, bank converts at 1.19 = 119,000 USD
- You receive 119,000 USD in the bank
- The original invoice was recorded at 120,000 USD
- Realized loss: 120,000 - 119,000 = 1,000 USD

The total P&L impact across periods combines unrealized and realized gains/losses.

## Unrealized FX — Period-End Revaluation

Period-end revaluation is run as a controlled accounting-period close task — not an ad-hoc process. Each accounting period has a set of required tasks that must be completed before the period can be closed:

- **Account Payables** — Close AP for the period
- **Account Receivables** — Close AR for the period
- **Journal Entries** — Close journal entries for the period
- **FX revaluation** — Run and post FX revaluation entries

**Controls and sequencing:**

- The **FX revaluation** task can only run after the period's sub-ledger lock tasks (**Account Payables**, **Account Receivables**, **Journal Entries**) are completed.
- The **prior period's revaluation must already be completed** (or not exist) before the current period's revaluation can run — enforcing strict chronological sequencing and preventing gaps.

### What gets revalued

The run covers the open items and monetary accounts described under **What gets revalued** above — open AP/AR documents and accruals, plus any account whose **Entity revaluation settings** is *Revalue for entity*. Each open balance is taken at the period-end closing rate, and for any account whose **Group revaluation settings** is *End of period* the local→group difference is posted to CTA.

### How the adjustment is calculated

For each population, Light revalues the open foreign-currency balance at the period-end closing rate and compares it to the amount currently on the books:

```
Revalued balance = open balance (original currency) × period-end rate
FX adjustment    = Revalued balance − current carrying amount
```

### How it posts

- A **single FX accounting document is created per run**, dated at period end and posted immediately — it is never left in draft.
- The monetary account is adjusted to its revalued amount; the offsetting entry is posted to the system **unrealized FX gain/loss** account, or to the **CTA** account for the local-to-group translation component.
- Each revaluation line carries a link back to its source document/line, supporting line-level traceability.

Revaluation runs are **idempotent** (protected against duplicate posting) and can be archived or reversed through a controlled reversal that reverses the underlying accounting document. The full history of revaluation documents is retained.

## Running FX Revaluation

To run FX revaluation for a period:

1. Go to **Accounting → Accounting periods** in the sidebar ([open Accounting periods](https://app.light.inc/accounting/accounting-periods))
2. Expand the relevant year and click on the period you want to close (e.g., May 2024)
3. On the **Tasks** page, find the **FX revaluation** row and click **Run revaluations**
4. The **FX revaluation** dialog opens with two sections:
   - **Entities to close** — A list of your entities (legal entities) with checkboxes and a **Last run** column showing when revaluation was last posted for each entity
   - **Document revaluation** — Shows any revaluations that have already been posted for this period
5. Select the entities you want to revalue by checking their checkboxes
6. Click **Post revaluation**

Light calculates the unrealized FX gains and losses for the selected entities and creates the corresponding accounting document automatically. You can view the resulting entries on the [Journal entries](https://app.light.inc/journal-entries) page, linked to the accounting period in which the revaluation was run.

## Reviewing Posted Revaluations

After posting, the **Document revaluation** section of the FX revaluation dialog shows the revaluations that have been posted for the period. You can review these at any time by:

1. Going to **Accounting → Accounting periods** ([open Accounting periods](https://app.light.inc/accounting/accounting-periods))
2. Clicking on the relevant period
3. Clicking **Run revaluations** on the FX revaluation task row

The **Last run** column in the entities list shows the date of the most recent revaluation for each entity.

## Reopening or Reversing a Revaluation

If an FX revaluation task has already been completed for a period, the action button changes from **Run revaluations** to **Reopen**. Reopening reverses the underlying accounting document through a controlled reversal so you can re-run the revaluation if adjustments are needed. Because runs are idempotent, re-running will not double-post, and the history of revaluation documents is retained for audit.

## Multi-Entity Revaluation

If you have multiple legal entities in Light, each entity is revalued independently. The FX revaluation dialog lists all your entities with checkboxes, so you can:
- Select all entities and revalue them at once
- Select individual entities to revalue them one at a time
- Track the **Last run** date for each entity to see which have been revalued

## CTA (Cumulative Translation Adjustment)

CTA captures the difference that arises because asset and liability accounts are re-translated to the closing rate each period (their **Group revaluation settings** is *End of period*), while equity and accumulated P&L stay at historical rates. The net imbalance posts to the system **Currency Translation Adjustment** account, and — as described under **Group FX** above — it adjusts only the group-currency balance (the local amount is nil).

CTA is generated in two places:

- **Period-end revaluation** — for accounts carried at the closing rate.
- **Settlement** — the group-only residual when a foreign-currency item clears (see **Realized FX (at settlement)** above).

## Consolidation (group level)

Consolidation is produced as a **report-time computation**, not as posted consolidation journals. Each entity's results are translated and aggregated into the group presentation currency and summed:

- **Subtotal** — the sum of the in-scope entities' results (in group currency)
- **Eliminations** — computed against a dedicated elimination ledger (intercompany lines flagged for elimination generate reversing entries into this ledger)
- **Total** — subtotal + eliminations

A consolidated report may be presented in local currency only if all in-scope entities share the same functional currency; otherwise it must be presented in the group base currency, which always works across mixed-currency entities. By default consolidation covers all entities in the group (or an explicitly selected set), summed on a flat basis. See [Multi-currency consolidation](/light-space/help-articles/blob/main/articles/10-reporting/10-8-multi-currency-consolidation.md) for details.

## Summary of Standards Alignment

| Area | Treatment in Light | IAS 21 / ASC 830 |
| --- | --- | --- |
| Monetary assets & liabilities | Closing (end-of-month) rate, revalued each period | Best practice |
| Equity | Historical rate, not re-translated | Best practice |
| Income statement | Transaction-date (spot) rate per item | Best practice |
| Translation difference | Posted to CTA (group-only) | Best practice |
| Realized FX on settlement | FX gain/loss vs. original rate | Best practice |
| Consolidation translation | Report-time aggregation in group currency | Best practice |

> **Tax considerations:** Some jurisdictions tax only realized FX gains/losses, and unrealized losses may not be deductible. Consult your tax advisor on the treatment of revaluation entries.

## Best Practices

- **Revalue monthly** — Don't wait until quarter-end; catching changes regularly produces more accurate interim results
- **Close prerequisite tasks first** — Make sure Account Payables, Account Receivables, and Journal Entries are closed before running FX revaluation
- **Revalue all entities** — Ensure every entity with foreign currency exposure is selected when posting revaluation
- **Set account FX settings** — On each balance-sheet account that holds foreign currency, set **Entity revaluation settings** to *Revalue for entity* and **Group revaluation settings** to *End of period*; keep equity and P&L accounts on *Do not revalue* / *Historical*
- **Review before closing** — Check the generated entries on the [Journal entries](https://app.light.inc/journal-entries) page before closing the period
- **Track the Last run date** — Use the Last run column in the FX revaluation dialog to confirm all entities have been revalued for the current period
- **Separate realized vs. unrealized** — Track both types of FX gains/losses for accurate analysis and reporting
- **Document your policy** — Be consistent in how and when you run revaluation across periods

## Related Articles

- [Clearing, FX gain/loss, and CTA](/light-space/help-articles/blob/main/articles/05-general-ledger/5-12-clearing-fx-cta.md)
- [Currency settings](/light-space/help-articles/blob/main/articles/02-organization-setup/2-6-currency-settings.md)
- [When Custom Rates Apply vs System Rates](/light-space/help-articles/blob/main/articles/02-organization-setup/2-12-custom-vs-system-fx-rates.md)
- [Multi-currency consolidation](/light-space/help-articles/blob/main/articles/10-reporting/10-8-multi-currency-consolidation.md)
- [Multi-currency reconciliation](/light-space/help-articles/blob/main/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
- [Multi-entity ledger management](/light-space/help-articles/blob/main/articles/05-general-ledger/5-6-multi-entity-ledger.md)
