# Setting a Custom FX Rate for Your Company

By default, Light converts foreign-currency amounts using daily market rates, sourced automatically. If your business reports on fixed monthly FX rates — for example, a rate negotiated with your bank — you can have Light use your rate instead, so your books, payments, and month-end revaluation match your bank rather than the market.

[Open in Light →](https://app.light.inc/ledger-reports)

## What a custom rate does

A custom rate (an "FX rate override") pins the conversion rate for one currency, for one month, across your whole company. Once set, every flow that converts that currency — bills, sales invoices, payments, bank reconciliation, expenses, credit notes, purchase-order matching, and the month-end FX revaluation — uses your rate instead of the market rate.

## How to set one

There is no self-serve screen in this version — to set a custom rate, contact Light support with:

- **Currency** — the currency you want to pin (e.g. USD, GBP, CZK). It must not be EUR (see below).
- **Rate** — expressed as **how much one unit of the currency is worth in EUR**. For example, "1 CZK = 0.04 EUR." This is the same direction Light shows rates elsewhere.
- **Month** — the month the rate applies from.

Support will confirm the rate back to you before it takes effect.

> Self-serve setup from your organization settings is planned for a future release.

## How custom rates behave

- **Monthly.** One rate per currency per month. A rate can't change part-way through a month — set a new rate for the next month instead.
- **Forward-looking.** A rate applies to transactions dated on or after the 1st of its month. Already-posted journal entries are never recalculated, so closed periods don't move.
- **EUR is the reference currency.** You give each currency's value in EUR, and Light derives the cross-rates between your currencies from that. EUR itself can't be overridden — it's the anchor.
- **Set every currency you use.** For a conversion between two non-EUR currencies (e.g. USD ↔ GBP), both currencies need a custom rate that month. If only one does, Light uses market rates for that whole conversion — see [When Custom Rates Apply vs System Rates](/articles/02-organization-setup/2-12-custom-vs-system-fx-rates).

## Checking which rate was applied

Light records, for every conversion, whether your custom rate or the market rate was used. The exchange-rates report shows this per currency per day — check there (or ask support) to confirm your rates are being applied as expected.

## Related articles

- [Setting a Custom FX Rate per Entity](/articles/02-organization-setup/2-11-custom-fx-rates-entity)
- [When Custom Rates Apply vs System Rates](/articles/02-organization-setup/2-12-custom-vs-system-fx-rates)
- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
