# FX Revaluations

Foreign exchange (FX) revaluation adjusts your GL account balances to reflect current exchange rates. In Light, FX revaluation is a required step in the period-end close process and is run on a per-entity basis.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## Understanding FX Revaluation

FX revaluation addresses the mismatch between when a transaction is recorded and when it settles.

**Example:**
- You invoice an AR customer for 100,000 EUR on January 1 at a rate of 1.20 USD/EUR = 120,000 USD
- You post 120,000 USD to your receivable in the GL
- By January 31 (period-end), the rate has moved to 1.18 USD/EUR
- The receivable is now worth 118,000 USD at the new rate
- Unrealized loss: 120,000 - 118,000 = 2,000 USD

FX revaluation entries record this unrealized gain or loss and adjust GL balances to reflect current exchange rates at period-end.

## Which Accounts Revalue?

Revaluation applies to accounts that hold foreign currency balances that have not yet settled.

**Accounts that typically revalue:**
- Accounts Receivable (in foreign currency)
- Accounts Payable (in foreign currency)
- Cash in foreign currency
- Intercompany payables/receivables
- Forward contracts

**Accounts that typically don't revalue:**
- Fixed assets (valued at historical rate)
- Long-term debt (under hedge accounting, may be valued at spot)

## FX Revaluation in the Period-End Close

In Light, FX revaluation is part of the [period-end close workflow](https://app.light.inc/accounting/accounting-periods). Each accounting period has a set of required tasks that must be completed before the period can be closed:

- **Account Payables** — Close AP for the period
- **Account Receivables** — Close AR for the period
- **Journal Entries** — Close journal entries for the period
- **FX revaluation** — Run and post FX revaluation entries

All four tasks are marked **Required**. The order they appear may vary by period, but all must be completed before you can close the period.

> **Note:** The prior accounting period must be closed before you can complete tasks in the current period.

## Running FX Revaluation

To run FX revaluation for a period:

1. Go to **Accounting > Accounting periods** in the sidebar ([open Accounting periods](https://app.light.inc/accounting/accounting-periods))
2. Expand the relevant year and click on the period you want to close (e.g., May 2024)
3. On the **Tasks** page, find the **FX revaluation** row and click **Run revaluations**
4. The **FX revaluation** dialog opens with two sections:
   - **Entities to close** — A list of your entities (legal entities) with checkboxes and a **Last run** column showing when revaluation was last posted for each entity
   - **Document revaluation** — Shows any revaluations that have already been posted for this period
5. Select the entities you want to revalue by checking their checkboxes
6. Click **Post revaluation**

Light will calculate the unrealized FX gains and losses for the selected entities and create the corresponding journal entries automatically. You can view these entries on the [Journal entries](https://app.light.inc/journal-entries) page.

## Revaluation Entries

When you post a revaluation, Light generates journal entries that:
- Adjust asset and liability accounts to reflect the current exchange rate at period-end
- Record the offsetting unrealized FX gain or loss

These entries appear on the [Journal entries](https://app.light.inc/journal-entries) page and are linked to the accounting period in which the revaluation was run.

## Reviewing Posted Revaluations

After posting, the **Document revaluation** section of the FX revaluation dialog shows the revaluations that have been posted for the period. You can review these at any time by:

1. Going to **Accounting > Accounting periods** ([open Accounting periods](https://app.light.inc/accounting/accounting-periods))
2. Clicking on the relevant period
3. Clicking **Run revaluations** on the FX revaluation task row

The **Last run** column in the entities list shows the date of the most recent revaluation for each entity.

## Reopening a Closed FX Revaluation

If an FX revaluation task has already been completed for a period, the action button changes from **Run revaluations** to **Reopen**. Clicking **Reopen** allows you to re-run the revaluation if adjustments are needed.

## FX Gain and Loss

FX revaluation produces two types of gains and losses:

**Unrealized FX Gain/Loss** — Recorded when revaluation is posted at period-end. These reflect the change in value of unsettled foreign currency balances based on current exchange rates. They may flow through the income statement (P&L) or be deferred to Other Comprehensive Income (OCI), depending on your accounting framework.

**Realized FX Gain/Loss** — Recorded when a foreign currency transaction actually settles (e.g., when a customer pays an invoice or when you pay a vendor). This is the final, actual gain or loss based on the rate at settlement.

## Settlement and Realized Gains/Losses

When a previously revalued item settles, the realized gain or loss is recorded.

**Example:**
- AR revalued: Owed 100,000 EUR, revalued to 118,000 USD at period-end
- Customer pays: Sends 100,000 EUR, bank converts at 1.19 = 119,000 USD
- You receive 119,000 USD in the bank
- The original invoice was recorded at 120,000 USD
- Realized loss: 120,000 - 119,000 = 1,000 USD

The total P&L impact across periods combines unrealized and realized gains/losses.

## Revaluation at Period-End

The typical period-end workflow is:

1. Post all transactions for the period (invoices, payments, journal entries)
2. Go to [Accounting periods](https://app.light.inc/accounting/accounting-periods) and open the period
3. Close **Account Payables**, **Account Receivables**, and **Journal Entries** tasks
4. Run **FX revaluation** for all relevant entities
5. Review the revaluation entries on the [Journal entries](https://app.light.inc/journal-entries) page
6. Click **Close period** to finalize

Revaluation should be run after all other transactions are posted but before the period is closed, so that FX gains and losses are included in the period's results.

## Multi-Entity Revaluation

If you have multiple legal entities in Light, each entity is revalued independently. The FX revaluation dialog lists all your entities with checkboxes, so you can:
- Select all entities and revalue them at once
- Select individual entities to revalue them one at a time
- Track the **Last run** date for each entity to see which have been revalued

## Regulatory Considerations

**US GAAP (ASC 830):**
- Temporal method typically used for remeasurement
- Unrealized gains/losses generally flow to the income statement (P&L)

**IFRS (IAS 21):**
- Current method typically used for translation
- Unrealized gains/losses may flow to Other Comprehensive Income (OCI) rather than P&L
- Different treatment can significantly impact reported earnings

**Tax considerations:**
- Some jurisdictions tax only realized FX gains/losses
- Unrealized losses may not be deductible
- Consult your tax advisor on the treatment of revaluation entries

## CTA (Cumulative Translation Adjustment)

For consolidation of foreign subsidiaries, translation differences may arise when converting a subsidiary's GL from its local currency to the group currency. These are posted to a Cumulative Translation Adjustment (CTA) account in equity. When a subsidiary is disposed of, the CTA is realized and flows to P&L.

## Best Practices

- **Revalue monthly** — Don't wait until quarter-end; catching changes regularly produces more accurate interim results
- **Close prerequisite tasks first** — Make sure Account Payables, Account Receivables, and Journal Entries are closed before running FX revaluation
- **Revalue all entities** — Ensure every entity with foreign currency exposure is selected when posting revaluation
- **Review before closing** — Check the generated journal entries on the [Journal entries](https://app.light.inc/journal-entries) page before closing the period
- **Track the Last run date** — Use the Last run column in the FX revaluation dialog to confirm all entities have been revalued for the current period
- **Separate realized vs. unrealized** — Track both types of FX gains/losses for accurate analysis and reporting
- **Document your policy** — Be consistent in how and when you run revaluation across periods

## Related Articles

- [Multi-currency reconciliation](/light-space/help-articles/blob/main/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
- [Multi-entity ledger management](/light-space/help-articles/blob/main/articles/05-general-ledger/5-6-multi-entity-ledger.md)
- [Clearing, FX gain/loss, and CTA](/light-space/help-articles/blob/main/articles/05-general-ledger/5-12-clearing-fx-cta.md)
