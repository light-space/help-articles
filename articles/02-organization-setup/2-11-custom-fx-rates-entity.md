# Setting a Custom FX Rate per Entity

If your organization has more than one entity, you can set a custom FX rate for a **specific entity** instead of the whole company. This is useful when entities settle the same currency at different negotiated rates.

[Open in Light →](https://app.light.inc/ledger-reports)

## How entity and company rates work together

For any transaction, Light resolves the FX rate in this order:

1. **Entity rate** — a custom rate set for that transaction's entity
2. **Company rate** — a custom rate set for the whole company
3. **System rate** — the daily market rate (the fallback)

So an entity rate always wins for that entity, and a company-wide rate covers every entity that doesn't have its own. You can mix the two: set one company-wide rate as the default and a different rate for the one entity that needs it.

## How to set one

As with company rates, this is set by Light support (no self-serve screen yet). Provide the same details — currency, rate (how much 1 unit of the currency is worth in EUR — e.g. "1 CZK = 0.04 EUR"), and month — **plus the entity** the rate applies to.

> If you're not sure which entity a transaction belongs to, support can help you confirm before setting the rate.

## Things to keep in mind

- The monthly, forward-looking, and EUR-reference rules are identical to company-wide rates — see [Setting a Custom FX Rate for Your Company](/articles/02-organization-setup/2-10-custom-fx-rates-company).
- Setting an entity rate does **not** remove the company-wide rate; it only takes precedence for that entity.

## Related articles

- [Setting a Custom FX Rate for Your Company](/articles/02-organization-setup/2-10-custom-fx-rates-company)
- [When Custom Rates Apply vs System Rates](/articles/02-organization-setup/2-12-custom-vs-system-fx-rates)
- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
