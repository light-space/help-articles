# Sphere SOP - Light Customer Onboarding

## Sphere Integration (Tax Engine)

Sphere is an internal/external tax calculation engine used by Light to compute taxes for AR transactions. Once enabled, Light routes tax calculation requests to Sphere using predefined mappings and entity configuration.

### Integration capabilities

The Sphere integration enables:

- **Tax calculation**: Automatic tax calculation via Sphere for AR transactions
- **Entity-level configuration**: Enable/disable Sphere per entity
- **Mapping-based processing**: Uses Light IDs (customers, products) shared with Sphere
- **Flexible activation**: Controlled via database configuration (`sphere_company_entity`)
- **Future extensibility**: Planned API + Backoffice UI support

## Setting up Sphere integration

Unlike Avalara AvaTax, Sphere is **not connected via OAuth**. Setup is manual and requires coordination with the Sphere team.

### 1. Share Light IDs with Sphere

Ensure the customer provides required mappings to Sphere:

- **Customer Light IDs**
- **Product Light IDs**

These mappings are required because:

- Sphere uses them internally to identify entities
- Tax calculation requests depend on these mappings being correctly configured

### 2. Retrieve Sphere Company Code

- Request the **Sphere "code"** for the company entity from Sphere team
- This serves as a reference identifier in Sphere

**Important notes:**

- This field is **optional**
- If not provided → use `DEFAULT`

### 3. Create Sphere entity record in Monolith

Create a record in:

```
sphere_company_entity
```

Populate required fields, including:

- `company_entity_id`
- `sphere_code` (or `DEFAULT`)
- `status`

### 4. Activate Sphere

Set:

```
status = ACTIVE
```

Once active:

- All **AR tax calculations** for that entity will be routed to Sphere
- Light will use Sphere as the **tax engine**

## Transaction processing with Sphere

When creating an AR invoice:

1. Light prepares transaction payload:
   - Customer (via Light ID)
   - Products (via Light ID)
   - Invoice amounts
2. Light sends request to Sphere
3. Sphere:
   - Matches IDs using provided mappings
   - Calculates applicable tax
   - Returns tax result
4. Light:
   - Applies returned tax to invoice
   - Displays tax values to user

## Disabling Sphere

To disable Sphere:

```
status = INACTIVE
```

### Behavior after disabling:

- New transactions → **will NOT use Sphere**
- Existing documents:
  - Still retain `tax_engine = SPHERE`
  - Require separate handling

## Handling existing documents (Important)

Disabling Sphere **does not automatically migrate existing drafts**.

### Current limitation:

- Draft invoices may still:
  - Reference Sphere
  - Attempt to use Sphere logic

## Recommended future enhancement

To properly support disabling:

### 1. Draft migration endpoint

Create an endpoint to:

- Find all **draft documents**
- Where:

```
tax_engine = SPHERE
```

- Update to:

```
tax_engine = LIGHT
```

This ensures:

- Clean transition
- No dependency on Sphere after disabling

### 2. Backoffice UI support

Add UI to:

- Enable / disable Sphere per entity
- Manage Sphere configuration
- Trigger draft migration

### 3. Align with AvaTax behavior

- Petar has implemented similar logic for AvaTax
- Sphere should **mimic the same approach** for consistency

## Troubleshooting Sphere

**Tax not calculated**

- Verify Light IDs are shared with Sphere
- Ensure mappings exist in Sphere system
- Confirm `status = ACTIVE`

**Wrong tax result**

- Check product/customer mapping accuracy
- Validate payload being sent to Sphere

**Sphere not triggered**

- Verify entity exists in `sphere_company_entity`
- Confirm status is ACTIVE

## Summary

- Sphere is **manually configured**, not OAuth-based
- Activation is controlled via **database flag**
- Correct **ID mapping is critical**
- Disabling requires **additional cleanup for draft documents**
- Future improvements should focus on **API + UI + migration tooling**
