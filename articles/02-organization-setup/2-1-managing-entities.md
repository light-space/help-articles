# Managing Entities

> **What is this page about:** How to create and manage company entities in Light, from setting one up to viewing details, editing, and card onboarding status.

[Open in Light →](https://app.light.inc/settings/entities)

## On this page

- What is a company entity in Light
- How to create a new entity in Light
- How to view entity details in Light
- How to edit entity details in Light
- Card onboarding status in Light
- Best practices for managing entities in Light

## What is a company entity?

A company entity is a distinct legal entity inside your organisation: a parent company, subsidiary, division or any other legally separate business unit. Each entity keeps its own accounting records, VAT number and local currency. If your organisation has more than one legal entity, Light consolidates reporting across all of them.

## Create a new entity

1. Open Light and go to **Settings, **press** Entities** (under **Records**).
2. Click **Create entity**.
3. Fill in the entity details:
   - **Display name** (required): the name shown in Light, e.g. "US Headquarters."
   - **Legal name** (required): the official name registered with authorities.
   - **Country** (required): where the entity is registered.
   - **State**: state or region, if applicable.
   - **Local currency** (required): the entity's primary operating currency. This locks once the entity is created.
   - **VAT** (optional): the entity's VAT identification number.
   - **Business reg. number** (optional): legal registration or company number.
   - **Street**, **Zip/postcode**, **City** (all optional): registered address.
4. Add e-invoicing details, if the entity uses an e-invoicing network:
   - **Network**: Peppol, SDI, Nemhandel, myDATA, VeriFactu or Portuguese Tax Reporting.
   - **EAS code** and **E-invoice address**: required for every network except myDATA and VeriFactu. For myDATA, Light uses the entity's VAT number as the network identifier instead, so you can skip both fields.
5. Click **Create**.

Light assigns an entity code automatically. You can't set or edit this code yourself.

Local currency can't be changed after creation. To use a different currency, create a new entity rather than editing the existing one.

## View entity details

1. Open Light and go to **Settings, **press** Entities**.
2. The entity list shows: **Entity code, Name, Currency, Country, VAT, Business reg. number, Cards** and **Status**.
3. Click any entity to open its detail panel and see every configured field.

## Edit entity details

1. Open Light and go to **Settings, **press** Entities**.
2. Click the entity you want to change.
3. Click **Edit**.
4. Update the fields you need in the **Edit details** dialog. Local currency isn't editable here.
5. Click **Save**.

## Card onboarding status

Each entity has a Cards status showing where it stands with the card issuer:

- **Not onboarded**: the entity hasn't started card setup.
- **In process**: onboarding is underway.
- **Verified**: expense cards are active for this entity.

To activate cards, open the entity's detail panel, scroll to the Cards section, and complete onboarding: provide legal documents and set spending limits.

## Best practices

- Match each entity's local currency to its operating country.
- Confirm VAT and registration numbers before posting transactions.
- Use Display name for names your team will recognise in reports.
- Add e-invoicing details for any entity using Peppol, SDI, Nemhandel, myDATA, VeriFactu or Portuguese Tax Reporting.

## Related articles

- [Currency Settings](https://help.light.inc/organization-setup/currency-settings)
- [Tax and VAT Configuration](https://help.light.inc/organization-setup/tax-vat-configuration)
- [E-invoicing and Peppol](https://help.light.inc/organization-setup/e-invoicing-peppol)
- [Fiscal Year and Accounting Periods](https://help.light.inc/organization-setup/fiscal-year-periods)

---

*Also searched as: company entity setup, subsidiary in Light, legal entity settings, multi-entity accounting, add a business unit or division, entity code, change entity currency, card onboarding status, e-invoicing network setup.*
