# Managing Entities

This article explains how to create and manage company entities in Light, which represent your legal entities, subsidiaries, and operating divisions within your organization.

[Open in Light →](https://app.light.inc/settings/entities)

## What are company entities?

A company entity represents a distinct legal entity within your organization. This might be a parent company, a subsidiary, a division, or any legally separate business unit. Each entity can operate independently with its own accounting records, VAT numbers, and local currency settings. Multi-entity organizations can consolidate reporting across all entities within Light.

## Creating a new entity

1. Navigate to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities) (under the Records section)
2. Click **+ Create entity**
3. Fill in the entity details:
   - **Display name**: The name as it appears in Light (e.g., "US Headquarters")
   - **Legal name**: The official legal name registered with authorities
   - **VAT** (optional): The entity's VAT identification number
   - **Business reg. number** (optional): Legal registration or company number
   - **Street** (optional): Street address
   - **Zip / postcode** (optional): Postal code
   - **City** (optional): City name
   - **Country**: The country where the entity is registered
   - **State**: State or region (if applicable)
   - **Local currency**: The primary currency for this entity's operations
4. Optionally fill in **E-invoicing** details:
   - **EAS code**: Electronic Address Scheme identifier for e-invoicing
   - **E-invoice address**: Peppol network address if using e-invoicing
5. Click **Create**

An entity code is automatically assigned to each new entity.

## Viewing entity details

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. The entity list displays columns for **Entity code**, **Name**, **Currency**, **VAT**, and **Cards**
3. Click on any entity to open its detail panel, which shows all configured fields

## Editing entity details

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click the entity you want to modify
3. Click **Edit** in the detail panel
4. Update the information in the **Edit details** dialog
5. Click **Save**

Local currency cannot be modified after creation. If you need to change it, you'll need to create a new entity.

## Cards

Each entity has a **Cards** section that manages expense card onboarding for that entity. The Cards status shows whether the entity has been onboarded with the card issuer:

- **Not onboarded**: The entity has not yet been set up for expense cards
- **In process**: Card onboarding is underway
- **Active**: Expense cards are enabled for this entity

To activate expense cards, open the entity detail panel, scroll to the Cards section, and follow the onboarding steps to provide legal documents and set limits.

## Best practices

- Ensure each entity's local currency matches its operating country when possible
- Verify VAT and registration numbers are accurate before posting transactions
- Use the Display name field for user-friendly names that will appear in reports and interfaces
- Fill in e-invoicing details (EAS code and e-invoice address) if you plan to use Peppol

## Related articles

- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
