# Setting up your organization

This article walks you through creating your company and configuring the initial organizational structure. This is a critical step that defines how Light will organize your financial data across entities and currencies.

[Open in Light →](https://app.light.inc/settings/entities)

## Create your company

When you complete your profile, you'll be prompted to create your first company:

1. Go to **Settings (gear icon) > Entities** (or follow the onboarding prompt)
2. Click **+ Create company**
3. Enter the following information:
   - **Company name** - Your legal company name
   - **Base currency** - Your primary operating currency (e.g., USD, EUR, GBP)
   - **Country** - Your company's primary country of incorporation
   - **Logo** (optional) - Upload your company logo for branded reports and communications
   - **Invoice email** - A dedicated inbox for receiving customer invoices (Light monitors this)
   - **Receipt email** (optional) - For receiving transaction receipts

4. Click **Create company**

Your company is now set up. Light uses the base currency you select as the default for financial reporting and consolidation.

> **Good to know:** You can change most company settings later, but the base currency cannot be modified once set. Choose carefully if you operate in multiple currencies.

## Add legal entities

Most multinational organizations need multiple legal entities for tax, regulatory, or operational reasons. Light handles multi-entity operations natively.

1. Go to **Settings (gear icon) > Entities**
2. Click **+ Create entity**
3. Enter the following details:
   - **Entity code** - A short identifier (e.g., "US-CORP", "UK-LTD", "DE-GMBH")
   - **Display name** - How the entity appears in reports and dropdowns
   - **Legal name** - The registered legal name for compliance
   - **Local currency** - The operating currency for this entity
   - **Country** - Where the entity is registered
   - **Address** - Full legal address including street, city, zip/postal code
   - **VAT number** (optional) - For compliance and reporting
   - **Business registration number** (optional) - e.g., company registration number

4. Click **Create entity**

Repeat for each legal entity you need to manage in Light.

## Configure currency support

Light supports unlimited currencies for international operations:

1. Go to **Settings > Organization > Currencies**
2. Click **Add currency**
3. Select the currency codes you need (e.g., USD, EUR, GBP, CNY)
4. Click **Save**

You can now:
- Create bank accounts in any configured currency
- Record transactions in any currency with automatic FX conversion
- Run consolidated reports across all currencies

> **Tip:** Configure all currencies you plan to use upfront. While you can add currencies later, it's easier to plan ahead if you know your global footprint.

## Set up chart of accounts

Light comes with a default chart of accounts template, but you'll likely customize it for your organization:

1. Go to **Accounting > Chart of accounts** ([Open in Light →](https://app.light.inc/accounting/ledger-accounts))
2. Review the default accounts (Assets, Liabilities, Equity, Revenue, Expenses)
3. Add custom accounts by clicking **+ Create account** and entering:
   - **Account code** - Unique identifier (e.g., "1000", "4010")
   - **Account name** - Display name
   - **Account type** - Asset, Liability, Equity, Revenue, or Expense
   - **Currency** - Which currencies this account supports
   - **Description** - Notes on account usage

4. Organize accounts into sub-accounts by dragging them under parent accounts

You can import accounts from a CSV if you're migrating from a legacy system. Contact support for templates.

## Create expense categories

Expense categories map receipts and card transactions to GL accounts:

1. Go to **Personal > Expenses** (or **Settings (gear icon) > Reimbursement categories**)
2. Click **+ Create category**
3. Enter:
   - **Category name** - e.g., "Office Supplies", "Travel", "Marketing"
   - **GL account** - Which GL account to post to when expenses are categorized here
   - **Budget limit** (optional) - Monthly or annual limit
   - **Approval requirements** - Who must approve expenses in this category
   - **Company entities** - Which entities can use this category

4. Click **Create**

> **Good to know:** Light's AI automatically categorizes receipts based on your categories. The more detailed your category structure, the more accurate AI categorization becomes.

## Define approval workflows

Set up how expenses and bills are approved:

1. Go to **Settings (gear icon) > Workflows**
2. Click **+ Create workflow**
3. Configure:
   - **Workflow name** - e.g., "Standard Expense Approval"
   - **Trigger** - When does this workflow start (e.g., expense amount over $500)
   - **Approvers** - Who approves (specific people or roles)
   - **Order** - Sequential or parallel approvals
   - **Escalation** - What happens if no response in X days

4. Click **Create**

Assign workflows to specific:
- Expense categories
- Cost centers
- Company entities
- User roles

## Enable integrations

Connect your existing tools during setup:

1. Go to **Settings (gear icon) > Integrations**
2. Click **Connect** next to each tool you want to integrate:
   - **Slack** - For approvals and notifications
   - **Salesforce** - Sync customers, opportunities, and revenue
   - **HubSpot** - Sync customer data and activities
   - **Stripe** - Connect payment processing
   - **Airwallex** - Connect business payment accounts
   - **Plaid** - Connect bank accounts
   - **Auth0** - SSO setup (if applicable)

Follow the authentication prompts for each integration. Most take just a few minutes to set up.

## Next steps

Your organization is now configured. Next:
1. [Add team members and define their roles](#)
2. [Connect your first bank account](#)
3. [Start creating invoices, bills, and expenses](#)

## Related articles

- [Adding team members and roles](#)
- [Connecting your first bank account](#)
- [Quick-start checklist](#)
