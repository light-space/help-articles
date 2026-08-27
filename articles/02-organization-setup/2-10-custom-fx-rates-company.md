# Setting a Custom FX Rate for Your Company in Light

> **What is this page about:** How custom FX rates work for your company in Light, how they interact with entity-level rates, how to request one from support, how monthly behavior works, what happens when only one currency in a pair has a custom rate, and how to check which rate was applied to a transaction.

## **On this page**

- What a custom rate does in Light
- How to set a custom rate in Light
- How custom rates behave in Light
- Checking which rate was applied in Light
- Related articles

In Light, a custom rate lets you pin the currency conversion used for a given currency and month, instead of the daily market rate — so your books, payments, and month-end revaluation match a rate you've agreed elsewhere (for example, with your bank), rather than the market.

By default, Light converts foreign-currency amounts using daily market rates, sourced automatically. If your business reports on fixed monthly FX rates, you can have Light use your rate instead.

*(Link to be confirmed before publishing — the current "Open in Light" link doesn't lead to this feature.)*

## What a custom rate does in Light

A custom rate pins the conversion rate for one currency, for one month. It can be set for your whole company or scoped to a single entity — if both exist for the same currency and month, the entity-level rate takes priority. Once set, every flow that converts that currency — bills, sales invoices, payments, bank reconciliation, expenses, credit notes, purchase-order matching, and the month-end FX revaluation — uses your rate instead of the market rate.

## How to set a custom rate in Light

Setting a custom rate isn't self-serve yet — there's no screen for it in the product, so contact Light support with:

- **Currency** — the currency you want to pin (e.g. USD, GBP, CZK). It must not be EUR (see below).
- **Rate** — expressed as **how much one unit of the currency is worth in EUR**. For example, "1 CZK = 0.04 EUR." This is the same direction Light shows rates elsewhere.
- **Month** — the month the rate applies to.
- **Scope** — whether the rate should apply across your whole company, or just one entity.

Support will confirm the rate back to you before it takes effect.

> Self-serve setup from your organization settings is planned for a future release. Day-level rate overrides (rather than a full month) are also planned for a future release.

## How custom rates behave in Light

- **Monthly.** One rate per currency per month. A rate can't change part-way through a month — set a new rate for the next month instead.
- **Month-scoped.** A rate applies to transactions dated in its month only — it doesn't carry forward to later months, so set a rate for each month you want covered. Already-posted journal entries are never recalculated, so closed periods don't move.
- **EUR is the reference currency.** You give each currency's value in EUR, and Light derives the cross-rates between your currencies from that. EUR itself can't be overridden — it's the anchor.
- **Set every currency you use.** For a conversion between two non-EUR currencies (e.g. USD ↔ GBP), both currencies need a custom rate that month. If only one does, Light uses market rates for that whole conversion — see When Custom Rates Apply vs System Rates.

## Checking which rate was applied in Light

Light keeps track of which rate was applied to each transaction, including cases where a conversion fell back to the market rate. There's no self-serve screen for viewing this yet — if you want to confirm a specific conversion used your custom rate rather than the market rate, ask Light support and they can check for you.

## Related articles

- [Setting a Custom FX Rate per Entity](https://light.inc/help/organization-setup/custom-fx-rates-entity)
- [When Custom Rates Apply vs System Rates](https://light.inc/help/organization-setup/custom-vs-system-fx-rates)
- [Currency Settings](https://light.inc/help/organization-setup/currency-settings)
