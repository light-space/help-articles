# When Custom Rates Apply vs System Rates

Once you've set custom FX rates, it helps to know exactly when Light uses them and when it falls back to market rates — especially if you transact in several currencies.

[Open in Light →](https://app.light.inc/ledger-reports)

## Where custom rates apply

Custom rates are used everywhere Light converts a foreign-currency amount: bills, sales invoices, payments, bank reconciliation, expenses, credit notes, purchase-order matching, and the month-end FX revaluation.

A few areas always use market rates by design and are **not** affected by custom rates: the raw exchange-rate lookup, partner/external API rate feeds, approval-threshold checks, and MRR analytics. These are intentional — for example, MRR stays on market rates so your historical trend doesn't shift when a rate is added.

## The one rule to know: all-or-nothing per conversion

When a conversion is between **two non-EUR currencies** (say USD → GBP) and you've set a custom rate for **only one** of them, Light uses **market rates for that entire conversion** — it never mixes one custom leg with one market leg.

**What this means in practice:** to be sure your custom rates are used everywhere, set a rate for **every non-EUR currency you transact in**, each month. If you set USD but not GBP, any USD↔GBP conversion falls back to market rates for the whole conversion — and the exchange-rates report flags it (see below).

Conversions between EUR and one other currency are always fine — EUR is the reference, so only that one currency needs a rate.

## Seeing where a fallback happened

The exchange-rates report shows, per currency per day, which rate was applied, and flags any conversion that fell back to market rates because a currency was missing. If a figure looks off, that's the first place to check — it usually means a currency is missing a rate for that month.

## Related articles

- [Setting a Custom FX Rate for Your Company](/articles/02-organization-setup/2-10-custom-fx-rates-company)
- [Setting a Custom FX Rate per Entity](/articles/02-organization-setup/2-11-custom-fx-rates-entity)
- [FX Revaluations](/articles/05-general-ledger/5-10-fx-revaluations)
