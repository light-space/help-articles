# Custom Properties (Dimensions)

This article explains how to set up and manage custom properties (also called dimensions) in Light. Custom properties allow you to track additional attributes and dimensions on transactions, documents, and objects.

[Open in Light →](https://app.light.inc/settings/custom-properties)

## What are custom properties?

Custom properties are user-defined fields that extend Light's data model to capture business-specific information. They function as dimensions for analysis and reporting. For example, you might create custom properties to track cost centers, projects, departments, or any other organizational attribute relevant to your business.

> Good to know: Custom properties can be attached to bills, invoices, purchase orders, reimbursements, journal entries, and other transactional objects.

## Types of custom properties

Light supports several input types for custom properties:

- **Single Select**: Choose one value from a predefined list
- **Multi Select**: Choose multiple values from a predefined list
- **Text**: Free-form text entry
- **Numeric**: Numeric values with optional ranges
- **Boolean**: True/false or yes/no flags
- **Date**: Date selection for time-based attributes

## Creating a custom property group

Custom properties are organized into groups. To create a new property group:

1. Navigate to **Settings (gear icon) → Custom properties**
2. Click **+ Create property group**
3. Enter the **Group Name** (e.g., "Cost Center", "Project")
4. Enter the **Internal Name** for system reference (cannot be changed later)
5. Select the **Input Type** that matches your data (single select, text, numeric, etc.)
6. Choose the **Object Types** this property applies to:
   - Bills, Invoices, Purchase Orders, Reimbursements, Journal Entries, etc.
7. Specify **Object Level**:
   - Header: Property applies to the entire document
   - Line: Property applies to individual line items
8. Toggle **Required** if this property must be set
9. Click **Create Group**

## Adding values to a property group

For select-type properties, add the available values:

1. Open the property group you just created
2. Click **Add Value**
3. Enter the **Value Label** (how it appears to users)
4. Enter the **Internal Name** for system reference
5. Add an optional **Description** if needed
6. Click **Add Value**

Repeat this process for each value users can select. You can add values anytime, even after initial creation.

## Setting default values

Default values pre-populate custom properties to streamline data entry:

1. Go to **Settings (gear icon) → Custom properties**
2. Click **Manage Defaults**
3. Choose the **Owner Type**:
   - User: Set defaults for individual team members
   - User Group: Set defaults for groups of users
   - Vendor: Set defaults for specific vendors
4. Select the **User**, **Group**, or **Vendor** as applicable
5. For each property, select the default value(s) to apply
6. Click **Save Defaults**

When users create transactions, default custom property values will be pre-populated based on their user profile.

## Applying custom properties to transactions

When creating or editing a transaction:

1. Locate the **Custom Properties** section in the document form
2. Fill in each required custom property marked with an asterisk (*)
3. For select properties, click the dropdown and choose a value
4. For text/numeric properties, enter the value directly
5. For date properties, select the date from the calendar picker
6. When all required properties are filled, the transaction can be saved

> Tip: Custom properties appear in the same form as your core transaction data, making them easy to populate during transaction entry.

## Organizing properties with groups

Keep related properties together by creating logical groupings:

- Separate properties into distinct groups by business purpose
- Use consistent naming conventions across groups (e.g., all cost-related properties in one group)
- Consider how users will filter and report on properties
- Document the purpose and valid values for each property in your team

## Using custom properties in reports

Custom properties enable powerful filtering and analysis. In reporting modules, use custom property filters to slice data, export values with transactions, and group reports by cost center, project, or department. Create dashboards that pivot by custom property dimensions.

## Deactivating properties

If a property is no longer needed, edit the group, set Status to Deleted, and click Save. Deletion archives the property but retains all historical values.

## Best practices

- Plan your property groups before creation to ensure consistency
- Use clear, descriptive names that users will understand
- Keep the number of required properties reasonable to avoid data entry friction
- Document the purpose and valid values for each property
- Use internal names that are code-friendly (no spaces, special characters)
- Consider setting defaults for properties to reduce manual entry
- Review property usage periodically and archive unused properties
- Test custom properties on a sample transaction before rolling out to your team

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Company Policies](/articles/02-organization-setup/2-8-company-policies)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
