# Custom Properties (Dimensions)

This article explains how to set up and manage custom properties (also called dimensions) in Light. Custom properties allow you to track additional attributes and dimensions on transactions, documents, and objects.

[Open in Light →](https://app.light.inc/settings/custom-properties)

## What are custom properties?

Custom properties are user-defined fields that extend Light's data model to capture business-specific information. They function as dimensions for analysis and reporting. For example, you might create custom properties to track cost centers, projects, departments, or any other organizational attribute relevant to your business.

> Good to know: Custom properties can be attached to various object types including bills, invoices, purchase orders, card transactions, contracts, products, and customers.

## Types of custom properties

Light supports several field types for custom properties:

- **Single select**: Choose one value from a predefined list
- **Multiple select**: Choose multiple values from a predefined list
- **Number**: Numeric value entry
- **Text**: Free-form text entry
- **Boolean**: Yes/no value
- **Date**: Date selection for time-based attributes

## Viewing custom properties

1. Navigate to [**Settings (gear icon) → Custom properties**](https://app.light.inc/settings/custom-properties) (under the Records section)
2. The list displays all custom properties with columns for **Label**, **Internal name**, **Field type**, **Object**, and **Level**
3. By default, the list is filtered to show only **Active** properties
4. Use the **Search** bar to find specific properties
5. Click **Columns** to customize which columns are displayed

## Creating a custom property

1. Navigate to [**Settings (gear icon) → Custom properties**](https://app.light.inc/settings/custom-properties)
2. Click **+ Create property**
3. Fill in the property details:
   - **Object group**: Select whether this property applies at the **Header** (entire document) or **Lines** (individual line items) level
   - **Object**: Choose which object types this property applies to (e.g., Bill, Invoice, Card Transaction, Purchase Order, Contract, Product, Customer)
   - **Label**: The display name for this property (e.g., "Project", "Cost Center")
   - **Internal name**: A system reference name (auto-generated from label, cannot be changed later)
   - **Context**: Optional description of the property's purpose
   - **Required**: Toggle on if this property must be filled in
   - **Field type**: Select the data type (Single select, Multiple select, Number, Text, Boolean, or Date)
4. Click **Create**

## Adding values to a select property

For single select and multiple select properties, you need to add the available values:

1. Open the property by clicking on it in the list
2. Scroll down to the **Values** section
3. Click **+ Add item**
4. Fill in the value details:
   - **Label**: How the value appears to users
   - **Internal name**: System reference name
   - **Context**: Optional description of this value
5. Repeat for each value users can select

You can add values at any time, even after the property is already in use.

## Editing a custom property

1. Open the property by clicking on it in the list
2. Click **Edit** in the top-right corner
3. Update the property fields as needed
4. Save your changes

Internal names cannot be changed after creation.

## Deactivating properties

If a property is no longer needed, you can deactivate it. Inactive properties are removed from future transactions, but historical values are retained.

1. Open the property
2. Click **Edit** in the top-right corner
3. Toggle the **Active** switch OFF
4. In the confirmation dialog, click **Deactivate**
5. Click **Save** to apply the change

To reactivate a property, toggle the **Active** switch back ON and save. Inactive properties display an **Inactive** badge.

## Applying custom properties to transactions

When creating or editing a transaction:

1. Locate the custom properties fields in the document form
2. Fill in each required custom property marked with an asterisk (*)
3. For select properties, click the dropdown and choose a value
4. For text properties, enter the value directly
5. For date properties, select the date from the calendar picker
6. When all required properties are filled, the transaction can be saved

## Editing custom properties on published documents

You can add, change, or remove line-item custom properties on contracts, sales invoices, and customer credits even after the document has been published. There's no need to void and recreate a document just to correct a tag.

1. Open a published contract, sales invoice, or customer credit
2. Enter edit mode on the line item you want to update
3. Add a missing custom property, change an existing value, or remove one entirely
4. Confirm the changes when prompted, then save

A few things to keep in mind:

- **Only custom properties are editable.** Amounts, tax codes, descriptions, and other revenue- or ledger-impacting fields stay locked after publishing.
- **Changes are confirmed before saving.** A confirmation step appears before your edits are committed to the published document.
- **Every change is tracked.** Edits appear in the document's modification history for a full audit trail.
- **The line item re-locks after saving.** To make further changes, re-enter edit mode on the line item.

No additional permission is required — editing follows your existing user permissions.

## Best practices

- Plan your properties before creation to ensure consistency
- Use clear, descriptive labels that users will understand
- Keep the number of required properties reasonable to avoid data entry friction
- Use internal names that are code-friendly (no spaces, special characters)
- Use the Context field to document the purpose of each property and its values
- Review property usage periodically and deactivate unused properties
- Test custom properties on a sample transaction before rolling out to your team

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Company Policies](/articles/02-organization-setup/2-8-company-policies)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
