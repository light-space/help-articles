# Revenue Schedules and Deferred Revenue

Revenue schedules in Light handle multi-period revenue recognition under ASC 606 standards. They determine when subscription and contract revenue is recognized in your GL.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Understanding Deferred Revenue

Deferred revenue occurs when you receive payment (or invoice) before delivering services. You must recognize revenue only as services are provided or goods are delivered. Light automates this through revenue schedules.

Example: A customer pays $1,200 upfront for a 12-month software subscription. You recognize $100 revenue each month for 12 months.

## Setting Up Revenue Schedules

### From a Contract

1. Open a contract with multi-period revenue
2. Navigate to **Revenue Recognition**
3. Click **Create Schedule**
4. Choose the **Recognition Method**:
   - **Upfront**: Entire amount on invoice date
   - **Straight-line**: Equal amounts over contract period
   - **Custom**: Define specific amounts per period

5. Set the **Start Date** (usually invoice date)
6. Set the **End Date** (usually contract end date)
7. Light calculates the schedule and shows projected recognition dates
8. Review the schedule
9. Click **Save**

### Manual Revenue Schedule

1. Navigate to **Revenue Schedules**
2. Click **Create Schedule**
3. Enter **Schedule Name** (e.g., "Acme Corp License 2024")
4. Select the **Invoice**
5. Choose the **Company Entity**
6. Set schedule details based on the method chosen
7. Click **Create**

> Good to know: Revenue schedules are created in DRAFT state. Post the schedule to create GL entries.

## Revenue Recognition Methods

### Upfront Recognition

Recognize the entire invoice amount immediately:

- Used for one-time products or services
- GL entry created on invoice posting date
- No deferred revenue GL account needed

### Straight-Line Recognition

Divide revenue equally across periods:

- Default for subscriptions and recurring services
- Light calculates equal amounts per period
- GL creates deferred revenue account entries monthly
- Most common for SaaS businesses

### Custom Recognition

Define specific amounts for each period:

1. Choose Custom method
2. Click **Edit Schedule**
3. For each period, enter:
   - **Period Start Date**
   - **Period End Date**
   - **Recognition Amount**

4. Light validates that amounts total the invoice amount
5. Click **Save**

Use custom recognition for tiered delivery or milestones.

## Schedule States and Posting

Revenue schedules progress through states:

- **DRAFT**: Created but no GL entries
- **POSTED**: GL entries created; revenue recognized as scheduled
- **COMPLETED**: All periods recognized
- **ARCHIVED**: No longer active

To post a schedule:

1. Open the schedule
2. Click **Post Schedule**
3. Light creates GL entries for all periods
4. Verify the GL entries in the GL module
5. Click **Confirm**

## Viewing Revenue Recognition

### Schedule Details

1. Open a revenue schedule
2. View the **Recognition Schedule** table showing:
   - Period start and end dates
   - Amount to recognize in each period
   - Posting date (usually period end date)
   - GL accounts used (deferred revenue and revenue)
   - Status (pending, posted, recognized)

3. Click into individual periods to see GL entries

### Revenue Dashboard

View all active revenue schedules:

1. Navigate to **Revenue Schedules Dashboard**
2. See total deferred revenue across all schedules
3. View upcoming recognition by month/quarter
4. Drill down into schedules
5. Filter by customer, contract, or period

## Modifying Revenue Schedules

### Amending a Schedule

If circumstances change (contract extended, price adjusted):

1. Open the posted schedule
2. Click **Amend Schedule**
3. Adjust the end date or amounts
4. Light calculates adjustment GL entries
5. Review the adjustment
6. Click **Save**

The amended schedule maintains history of both old and new terms.

### Canceling a Schedule

To reverse a revenue schedule completely:

1. Open the schedule
2. Click **Cancel Schedule**
3. Light reverses all GL entries for unrecognized periods
4. Periods already recognized remain in GL
5. Schedule status becomes CANCELLED

Use this if a contract is terminated early.

## Multi-Currency Schedules

For contracts in non-functional currency:

1. Create the revenue schedule as normal
2. Light shows the schedule in the contract currency
3. GL entries are created in functional currency using posting date FX rate
4. Overriding FX rates: Open the schedule and adjust as needed

## Contract Performance Obligations

For contracts with multiple services:

1. Create separate line items on the contract for each service
2. Create separate revenue schedules for each line item
3. Each schedule recognizes its portion independently
4. Totals across schedules match the contract amount

This ensures each performance obligation is recognized correctly.

## Testing Revenue Recognition

Before posting schedules to GL:

1. Open the schedule in DRAFT
2. Click **Test GL Entries**
3. Review proposed GL entries without posting
4. Light shows:
   - Debit/credit accounts and amounts
   - Posting dates
   - GL line descriptions

5. Click **Post** to commit, or **Cancel** to revise

## Deferred Revenue GL Account

Light typically creates accounts for:

- **Deferred Revenue**: Liability account (credit balance) for unrecognized revenue
- **Revenue**: Income account (credit balance) where revenue is recognized

Configure these accounts in GL settings. Different revenue accounts can be used based on revenue type or customer segment.

## Related Articles

- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Multi-entity AR operations](/articles/06-accounts-receivable/6-11-multi-entity-ar.md)
