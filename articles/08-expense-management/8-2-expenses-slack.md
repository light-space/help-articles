# Submitting Expenses via Slack

Submitting expenses through Slack offers the fastest, most convenient method for employees. Submit receipts without leaving Slack, approve extracted data with a click, and track reimbursement status inline.

[Open in Light →](https://app.light.inc/expenses)

## Setting Up Slack Integration

### Installation

1. Navigate to **Settings** > **Integrations** > **Slack**
2. Click **Connect Slack Workspace**
3. Follow OAuth flow to authorize Light in your Slack workspace
4. Select the Slack workspace to integrate
5. Light bot is installed and ready to use

### Configuration

After installation, configure:

1. Select **channels** where expense bot should be active:
   - Personal DMs (employees can DM bot privately)
   - #expenses channel (for team submissions)
   - Department channels

2. Set **notifications**: How and when to notify about approvals

3. Enable **AI auto-processing**: Automatically extract or require manual review

4. Click **Save**

## Submitting an Expense via Slack

### Direct Message to Light Bot

Fastest method for simple receipts:

1. Open Slack and find the **Light** (or **Expenses**) bot
2. Click **New Expense** or type `/expense`
3. A modal appears to enter details:
   - **Amount** (optional if uploading receipt)
   - **Category**: Select from dropdown (Travel, Meals, etc.)
   - **Description**: What was purchased
   - **Date**: When expense occurred

4. Click **Add Receipt** to attach image/PDF
5. Click **Submit**

Light processes the receipt and sends you a link to review extracted data.

### Posting Receipt in Channel

Submit receipt in #expenses or project channel:

1. In Slack, upload receipt image or PDF (using file upload button)
2. Reply to the message with: "Hey Light, process this expense"
3. Light bot responds asking for category and description
4. Enter category and notes in the thread
5. Light acknowledges and processes

### Forwarding Email Receipts

Forward email receipts to Light's Slack:

1. In email, use the "Forward to Slack" action (if available)
2. Forward to Light's email integration address: **expenses@light-slack.company.com**
3. Light captures the email and sends Slack notification
4. Click notification link to verify and submit

## Reviewing Extracted Data

After submitting, Light processes the receipt and sends you a message:

**"I found the following receipt details. Does this look right?"**

The message shows:
- **Merchant Name**: Where you shopped
- **Date**: When purchase occurred
- **Amount**: How much was spent
- **Category**: Suggested category

### Confirming or Correcting

**If correct:**
1. Click **Looks Good** or react with ✓
2. Expense is submitted for approval
3. You'll be notified when manager approves

**If something is wrong:**
1. Click **Edit** or **Need to Fix**
2. Light shows a modal to correct:
   - Merchant name
   - Amount
   - Date
   - Category
   - Add notes

3. Click **Fixed** to resubmit

### Adding Receipt Notes

Add context to help manager with approval:

1. After confirming details, click **Add Notes**
2. Describe the expense:
   - "Client dinner with Acme Corp team"
   - "Team office supplies for Q1 planning"
   - "Flight to SF for customer visit"

3. Click **Save**

Notes are visible to manager when reviewing.

## Tracking Reimbursement Status

After submitting, Light sends status updates:

1. **Submitted Notification**: "Your expense for $X has been submitted to [Manager Name]"
2. **Approval Notification**: "[Manager Name] approved your $X expense"
3. **Reimbursement Notification**: "Your reimbursement of $X is being processed"
4. **Payment Notification**: "Reimbursement of $X was paid to your account"

Click notifications to see more details.

### Checking Status in Slack

Ask Light for your expense status:

1. Type `/expense status` in Slack
2. Light responds with list of your recent expenses:
   - Pending approval
   - Approved but not paid
   - Paid
   - Rejected

3. Click any expense to see full details (amount, date, approval notes)

## Batch Submitting Multiple Receipts

Submit multiple expenses at once:

1. In Slack, click **New Expense**
2. Instead of uploading one receipt, select **Upload Multiple**
3. Click **Add Receipt** multiple times to add several receipts
4. Fill in details for first receipt
5. Click **Next** to go to next receipt
6. Fill in details for each
7. Click **Submit All**

Light processes all receipts together and sends one confirmation.

## Sharing Expenses with Team

For team expenses (shared meal, supplies):

1. Submit the expense normally
2. In the extraction confirmation, click **Share with Team**
3. Select teammates to split the cost:
   - Click checkboxes to select people
   - Light shows split amount for each person

4. Click **Confirm Split**

Each team member is notified of their share; splits are tracked for reimbursement.

> Tip: For team dinners, one person submits the receipt and it's automatically split among attendees.

## Receipt Photo Tips

For best AI extraction results:

1. **Good Lighting**: Take photo in bright area (natural light best)
2. **Full Receipt**: Include entire receipt in frame, not just part
3. **Flat Surface**: Place receipt flat before photographing (not at angle)
4. **Focus**: Focus camera on receipt before snapping
5. **Landscape**: Take photo in landscape orientation
6. **Recent**: Use receipts within a few weeks (ink doesn't fade)

Light's mobile app includes a guide with visual examples.

## Common Issues and Troubleshooting

### Extraction Didn't Work

If Light couldn't read the receipt:

1. Light sends message: "I couldn't read this receipt clearly. Can you help?"
2. Options:
   - **Retake Photo**: Take a better photo of same receipt
   - **Manual Entry**: Manually enter amount, merchant, date
   - **Ask Later**: Try resubmitting later

3. Select option and proceed

### Receipt Image Too Blurry

1. Light indicates extraction was low confidence
2. Click **Retake Photo**
3. Use tips above for better photo
4. Resubmit

### Wrong Category Suggested

1. In the confirmation, click **Edit**
2. Change category to correct one
3. Light learns from correction (future similar receipts improve)
4. Click **Fixed** to resubmit

## Slack Slash Commands

Quick commands available in Slack:

- `/expense` - Start new expense submission
- `/expense status` - Check your expense status
- `/expense recent` - Show last 5 submissions
- `/expense help` - Show available commands

Type the command in any channel where Light bot is active.

## Privacy and Security

Your expense submissions in Slack:

- **Encrypted**: Receipts are encrypted in transit and at rest
- **Private**: Only you and your manager can see your expenses
- **Compliant**: GDPR and SOC 2 compliant
- **No Storage**: Receipt photos are deleted after processing (only metadata retained)

## Related Articles

- [Submitting expenses via Teams](/articles/08-expense-management/8-3-expenses-teams.md)
- [Submitting expenses via email](/articles/08-expense-management/8-4-expenses-email.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
