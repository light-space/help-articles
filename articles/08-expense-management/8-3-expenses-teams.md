# Submitting Expenses via Teams

Microsoft Teams users can submit expenses directly from Teams without leaving their chat application. The Light bot integrates with Teams to handle receipt processing and approval tracking inline.

[Open in Light →](https://app.light.inc/expenses)

## Setting Up Teams Integration

### Installation

1. Navigate to **Settings** > **Integrations** > **Microsoft Teams**
2. Click **Connect Teams**
3. Follow OAuth flow to authorize Light in your Teams organization
4. Select the Teams workspace to integrate
5. Light bot is installed and ready

### Configuration

After installation, configure:

1. Select **channels** where expense bot should be active:
   - Private DMs (employees can DM bot directly)
   - #expenses team channel
   - Department or project channels

2. Set **notification preferences**:
   - When to notify about expense status
   - Who gets notifications

3. Enable **auto-processing**:
   - Automatically process receipts, or
   - Require manual confirmation first

4. Click **Save**

## Submitting an Expense via Teams

### Direct Message to Light Bot

Fastest method for submitting receipts:

1. Open Teams and find **Light** or **Expenses** bot in your contacts
2. Click **New Expense** or type `/expense`
3. An adaptive card appears with entry fields:
   - **Receipt File**: Click to attach image/PDF
   - **Amount**: Dollar amount (pre-filled if receipt has it)
   - **Category**: Dropdown with spending categories
   - **Description**: What was purchased
   - **Date**: When expense occurred

4. Fill in details and click **Submit**

Light processes the receipt and sends an update card showing extracted data.

### Posting in Team Channel

Submit expense in team or project channel:

1. In Teams channel, click the **attachments** icon
2. Upload receipt image (JPG, PNG) or PDF
3. In the message, mention **@Light Expenses** and describe:
   - "Process this receipt for software subscription"

4. Light bot responds asking to confirm extraction
5. Click **Looks Good** or **Edit** to correct
6. Expense is submitted for approval

### Sharing Meeting Receipts

For expenses during Teams meetings:

1. During meeting, share receipt screen or upload file
2. Teams message automatically captures for Light
3. Light processes and asks for confirmation
4. Confirm in Teams chat, stay in meeting

No need to leave the meeting to submit.

## Reviewing Extracted Data in Teams

After submitting, Light sends an update card:

**"Receipt processed - Please confirm details"**

The card displays:
- **Merchant**: Shop or restaurant name
- **Date**: Purchase date
- **Amount**: Total cost
- **Category**: Suggested spending category
- **Buttons**: "Looks Good" or "Edit"

### Confirming Extraction

**If correct:**
1. Click **Looks Good**
2. Card updates: "Submitted for approval"
3. Card shows status of manager approval

**If needs correction:**
1. Click **Edit**
2. Modal appears with editable fields
3. Correct merchant, amount, date, or category
4. Click **Fixed** to resubmit
5. Light sends new update card to confirm

### Adding Context

Before confirming, add notes about the expense:

1. On the confirmation card, click **Add Notes**
2. Type description of the expense:
   - "Client dinner with Acme Corp"
   - "Travel for customer visit"
   - "Office supplies for Q1"

3. Click **Add**
4. Notes appear on card for manager to see

## Tracking Reimbursement Status

Light sends status updates via Teams:

1. **Submitted**: "Expense submitted to [Manager]"
2. **Approved**: "[Manager] approved your $X expense"
3. **Requested Changes**: "[Manager] needs clarification on your expense"
4. **Paid**: "Reimbursement of $X was deposited"

Click cards to see full details.

### Checking Your Expense Status

Ask Light for updates anytime:

1. DM Light bot or type in team channel: `/expense status`
2. Light responds with card listing:
   - Pending approval (how long pending)
   - Approved but not paid
   - Paid (with payment reference)
   - Denied (with reason)

3. Click any expense to expand and see details

## Batch Submitting Multiple Expenses

Submit multiple receipts in Teams:

1. In DM with Light, click **New Expense**
2. Select **Multiple Receipts** option
3. Attach multiple files (or upload one, then click **Add Another**)
4. Fill in details for first receipt
5. Click **Next** to move to second receipt
6. Repeat for all receipts
7. Click **Submit All**

Light processes all at once; you get one confirmation card.

## Team Expense Splits

For expenses shared by multiple people:

1. Submit expense normally
2. In confirmation card, click **Share with Team Members**
3. Select teammates to split with (checkboxes)
4. Light calculates individual shares
5. Click **Confirm Split**

Each team member gets notification of their share. Each person is reimbursed their portion.

## Adaptive Cards and Rich Experience

Teams messages show as adaptive cards with:

- **Visual data**: Amount, date, category shown prominently
- **Quick actions**: Approve, reject, or edit with single click
- **Context**: Notes from employee visible without opening new window
- **Real-time updates**: Card updates as status changes

No need to click to another app to see expense details.

## Receipt Attachment Best Practices

For best AI extraction:

1. **Quality**: Take clear photo with good lighting (natural light preferred)
2. **Angle**: Photo should be straight-on, not at angle
3. **Framing**: Full receipt in frame, not cropped
4. **Format**: JPG, PNG (best) or PDF (also works)
5. **Size**: File size less than 5MB

Light's guidance dialog in Teams shows photo examples.

## Teams Notifications

Control how you're notified about expense status:

1. Go to Teams **Settings** > **Notifications**
2. Find **Light Expenses**
3. Choose notification style:
   - Banner and feed
   - Banner only
   - Feed only
   - Quiet (read in Teams only, no notification)

4. Save preferences

## Troubleshooting Common Issues

### Receipt Couldn't Be Read

Light message: "I couldn't process this receipt. Can you help?"

Options:
- **Retake Photo**: Click to provide better photo
- **Manual Entry**: Type details instead
- **Try Later**: Resubmit the same file later

Click option and continue.

### Wrong Category Assigned

1. In confirmation card, click **Edit**
2. Change Category dropdown to correct one
3. Light learns from the change
4. Click **Fixed**

### Double Submission

If you accidentally submit the same receipt twice:

1. Light detects duplicate
2. Sends message: "This looks like a duplicate. Should I skip it?"
3. Click **Skip** to discard second copy
4. Only original is processed

## Mobile Teams App

Submitting via Teams mobile:

1. Open Light bot in Teams mobile app
2. Click **New Expense**
3. **Camera button** to take receipt photo in-app
4. Fill in amount, category, description
5. Click **Submit**

All same functionality as desktop Teams.

## Related Articles

- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Submitting expenses via email](/articles/08-expense-management/8-4-expenses-email.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
