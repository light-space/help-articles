# Managing Entities

This article explains how to create and manage company entities in Light, which represent your legal entities, subsidiaries, and operating divisions within your organization.

[Open in Light →](https://app.light.inc/settings/entities)

## What are company entities?

A company entity represents a distinct legal entity within your organization. This might be a parent company, a subsidiary, a division, or any legally separate business unit. Each entity can operate independently with its own accounting records, VAT numbers, and local currency settings. Multi-entity organizations can consolidate reporting across all entities within Light.

> Good to know: You can organize entities hierarchically, with parent-subsidiary relationships that reflect your corporate structure.

## Creating a new entity

1. Navigate to **Settings (gear icon) → Entities**
2. Click **+ Create entity**
3. Fill in the required information:
   - **Entity Code**: A unique identifier for the entity (e.g., "US-HQ", "EU-SUBSIDIARY")
   - **Display Name**: The display name as it appears in Light (e.g., "US Headquarters")
   - **Legal Name**: The official legal name registered with authorities
   - **Local Currency**: The primary currency for this entity's operations
   - **Country**: The country where the entity is registered
   - **Address**: Full business address including street, city, postal code
4. Add optional details:
   - **VAT Number**: The entity's VAT identification number
   - **Business Registration Number**: Legal registration or company number
   - **EAS Code**: Electronic Address Scheme identifier for e-invoicing
   - **E-invoice Address**: Peppol network address if using e-invoicing
5. Click **Create Entity**

## Editing entity details

1. Go to **Settings (gear icon) → Entities**
2. Find the entity in the list and click **Edit**
3. Update the information you need to change
4. Click **Save Changes**

Entity codes and local currency cannot be modified after creation. If you need to change these, you'll need to create a new entity.

## Entity hierarchy and relationships

You can establish parent-subsidiary relationships to reflect your organizational structure:

1. When creating or editing an entity, select **Parent Entity** if this entity is a subsidiary
2. The parent entity field allows you to link subordinate entities to a parent company
3. This hierarchy is used for consolidation and reporting purposes in Light

> Tip: Set up your entity hierarchy to match your corporate structure before adding accounts and transactions.

## Entity status

Entities have three possible statuses:

- **Active**: The entity is in use and transactions can be posted to it
- **Hidden**: The entity exists but is not displayed in lists (useful for archiving without deletion)
- **Inactive**: The entity is no longer operational

To change an entity's status, edit the entity and update the **Status** field.

## Deactivating or archiving entities

If an entity is no longer active but you need to retain historical records:

1. Edit the entity
2. Change the **Status** to **Hidden** or **Inactive**
3. Click **Save Changes**

Active entities cannot be deleted, but changing status to Hidden or Inactive effectively removes them from active workflows while preserving all historical data.

## Best practices

- Use consistent entity codes across your organization for easier identification
- Ensure each entity's local currency matches its operating country when possible
- Verify VAT and registration numbers are accurate before posting transactions
- Set up the complete entity hierarchy before beginning transactions
- Use the Display Name field for user-friendly names that will appear in reports and interfaces

## Related articles

- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
