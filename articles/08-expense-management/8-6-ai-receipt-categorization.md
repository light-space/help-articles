# AI Receipt Categorization

Light's AI automatically categorizes expenses and assigns them to GL accounts based on receipt content and merchant information. Machine learning improves accuracy over time as the system learns your spending patterns.

[Open in Light →](https://app.light.inc/expenses)

## How AI Categorization Works

When you submit a receipt, Light's AI:

1. **Analyzes Receipt Content**: Reads merchant name, items, and amount
2. **Identifies Merchant**: Matches to known merchants (airlines, hotels, restaurants)
3. **Predicts Category**: Based on merchant type and items
4. **Suggests GL Account**: Maps category to appropriate GL account
5. **Assesses Confidence**: Shows how certain the AI is about the categorization
6. **Learns from Corrections**: Improves when you correct predictions

> Good to know: Light's AI achieves 92%+ accuracy on standard receipts, with accuracy improving as you submit more expenses.

## Spending Categories

Light includes standard categories:

**Travel**
- Flights
- Hotels
- Ground transportation (taxi, Uber, parking)
- Rental cars
- Train/bus travel

**Meals**
- Restaurant meals
- Coffee/beverages
- Work meals/working lunches
- Client entertainment

**Office Supplies**
- Paper, pens, office equipment
- Computer accessories
- Furniture and fixtures
- Technology equipment

**Professional Development**
- Training courses
- Conferences
- Books and subscriptions
- Certifications

**Client Entertainment**
- Client meals
- Gifts under threshold
- Event attendance for clients

**Other**
- Miscellaneous expenses
- Unusual categories not fitting above

Your company can create custom categories tailored to your business.

## AI Category Suggestions

### Review Suggested Category

After submitting receipt:

1. Light shows **Category Suggestion**:
   - **Suggested Category**: AI's recommendation (e.g., "Travel - Hotel")
   - **Confidence Level**: High/Medium/Low certainty
   - **Reason**: Why Light thinks this category

2. Review the suggestion:
   - **Looks right**: Click **Confirm** to accept
   - **Wrong category**: Click **Change** to select correct one

### Overriding Suggestions

If Light categorizes incorrectly:

1. Tap **Change Category** or **Edit**
2. Browse or search available categories
3. Select correct category
4. Light acknowledges and learns from correction
5. Future similar expenses improve

## GL Account Mapping

Each spending category maps to GL accounts:

**Travel → GL Accounts**
- 6100 Travel Expenses
- 6110 Airfare
- 6120 Hotels
- 6130 Ground Transportation

**Meals → GL Accounts**
- 6200 Meals & Entertainment
- 6210 Meals & Incidentals
- 6220 Client Entertainment

When you categorize expense:

1. Light automatically assigns GL account based on category
2. GL account shows on expense record
3. Finance team can see which account expense will post to
4. You can override GL account if needed

## Merchant Recognition

Light maintains database of common merchants:

**Recognized Merchants** (no category needed):
- Delta Air Lines → Travel - Airfare
- Hilton Hotels → Travel - Hotel
- Uber → Travel - Ground Transportation
- Starbucks → Meals
- Apple → Technology (or varies by context)

**Unrecognized Merchants**:
- Small local businesses
- One-time vendors
- International merchants not in database

Light asks you for category for unrecognized merchants.

## Training the AI

Light improves through your feedback:

### Corrections Help Learning

When you correct a category:

1. Light notes: "User corrected Starbucks from Meals to Office Supplies"
2. Context: Receipt showed office supplies, not food
3. AI learns: In future, when Starbucks receipt shows office supplies, categorize differently
4. Database updates: Helps other employees with similar expenses

### Frequency Improves Accuracy

The more you use Light:

1. After 10-20 expenses: AI understands your category preferences
2. After 50+ expenses: Accuracy approaches 95%+
3. System adapts: Learns what **you** categorize as what
4. Personalization: Expenses in your context are categorized better

### Company-Level Learning

Across your company:

1. Light learns from all employee corrections
2. All employees benefit from collective learning
3. Common mistakes are caught early
4. Shared merchants improve across company

## Custom Categories

### Creating Custom Categories

For company-specific needs:

1. Navigate to **Settings** > **Spending Categories**
2. Click **Create Category**
3. Enter:
   - **Category Name**: (e.g., "Contractor Services")
   - **Description**: What's included
   - **GL Account**: Where expenses post
   - **Spending Limit**: Max per expense (if applicable)
   - **Requires Approval**: If over threshold

4. Click **Create**

5. AI learns the new category over time

### Custom Category Examples

- **Software Subscriptions**: Monthly SaaS tools
- **Contractor Payments**: 1099 contractors and freelancers
- **Client Reimbursements**: Amounts to reimburse clients
- **Equipment Maintenance**: Repairs and service contracts

Add categories that match your business.

## Confidence Scores

Light shows how confident the AI is:

- **High (Green)**: 90%+ confident in category
- **Medium (Yellow)**: 70-89% confident
- **Low (Red)**: Below 70% confident

### Acting on Confidence Levels

**High Confidence**:
- Trust the suggestion
- Auto-approve if policy allows
- Rarely needs correction

**Medium Confidence**:
- Review the suggestion
- Correct if needed
- Provides feedback

**Low Confidence**:
- Manual category selection required
- Light can't confidently categorize
- You must provide the category

## Policy-Based Categorization

Enforce company rules through categories:

### Spending Limits by Category

Each category can have limits:

- **Travel - Meals**: $75 per meal
- **Client Entertainment**: $500 per event
- **Office Supplies**: $100 per receipt

Light flags expenses exceeding limits for manager review.

### Pre-Approval Rules

Some categories require pre-approval:

- **Professional Development**: Over $500
- **Client Entertainment**: Over $250
- **Contractor Services**: Any amount

Light routes these to manager automatically.

## Merchant-Level Overrides

Set category preferences by merchant:

1. Navigate to **Settings** > **Merchant Rules**
2. Add merchant name (e.g., "Starbucks")
3. Set **default category**: What to use for this merchant
4. Set **spending limit**: Cap per transaction
5. Light applies rule to all Starbucks receipts from all employees

Useful for common merchants with consistent spending patterns.

## Categorization Analytics

Track categorization patterns:

1. Navigate to **Reports** > **Spending by Category**
2. View:
   - **Total spending** by category
   - **Trend**: Is category increasing/decreasing
   - **Top merchants**: Who employees buy from most
   - **Accuracy**: How often AI categorization was correct

3. Filter by:
   - Employee
   - Department
   - Time period
   - Category

Use to understand spending patterns and improve policies.

## Improving Accuracy

Tips for better AI categorization:

### Providing Clear Receipts

- **Good receipt photos**: Merchant name and items clear
- **Details visible**: Itemized breakdown (not just total)
- **Non-blurry**: Clear, legible text

Light extracts better information from clear receipts.

### Adding Descriptions

1. When submitting, include brief note:
   - "Client dinner - Acme Corp"
   - "Conference registration"
   - "Travel software subscription"

2. AI uses description context
3. Categorization improves

### Correcting Consistently

1. If Light suggests wrong category, correct it
2. Be consistent in your corrections
3. System learns your preferences
4. Future suggestions improve

## Handling Edge Cases

Some expenses don't fit standard categories:

**Multi-Category Expenses**:
- Lunch with supplies shopping (Meals + Office Supplies)
- Light lets you split across categories
- Each portion can have different GL account

**One-Time Unusual Expenses**:
- Once-off payment not fitting standard categories
- Choose closest category or create custom
- Light notes it as unusual for manager review

## Related Articles

- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md)
- [Expense reports and analytics](/articles/08-expense-management/8-14-expense-reports.md)
