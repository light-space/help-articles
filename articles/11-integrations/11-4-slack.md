# Slack Integration

Slack is the leading team communication and collaboration platform. Light's Slack integration sends real-time financial notifications and alerts directly to your team, keeping everyone informed about important financial events without leaving Slack.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Slack integration enables:

- **Financial alerts**: Notifications for overdue invoices, low cash balances, budget overages
- **Approval workflows**: Request and approve transactions directly in Slack
- **Daily summaries**: Automated daily financial summaries (revenue, expenses, cash position)
- **Custom notifications**: Configure which events trigger Slack messages
- **Interactive messages**: Click actions in Slack (approve, deny, view details)

This keeps your team informed and enables collaboration on financial decisions.

## Setting up Slack integration

To connect Slack:

1. Navigate to **Settings (gear icon) > Integrations > Slack**
2. Click **Connect**
3. You're redirected to Slack to authorize
4. Select the Slack workspace and channel where Light notifications should appear
5. Review the permissions Light is requesting
6. Click **Authorize**
7. Light confirms the connection and sends a test message

Next, configure what notifications you want.

## Configuring notifications

Define which financial events trigger Slack messages:

1. Navigate to **Settings (gear icon) > Integrations > Slack > Notifications**
2. Toggle on notifications you want:

   **Invoice notifications**:
   - Invoice created (notify when new invoice is entered)
   - Invoice overdue (notify when invoice is due or past due)
   - Invoice paid (notify when customer pays)

   **Cash notifications**:
   - Daily cash summary (notify every morning with cash position)
   - Low cash alert (notify if cash drops below threshold)
   - Large transaction (notify for large deposits or payments)

   **Budget notifications**:
   - Budget variance (notify when spending exceeds budget by threshold)
   - Category overage (notify when specific expense category exceeds budget)

   **AP notifications**:
   - Bill due (notify when supplier bill comes due)
   - Payment made (notify when you pay a vendor)

3. For each notification, configure:
   - Threshold (e.g., "notify if cash < $100,000")
   - Frequency (e.g., "once per day")
   - Recipient channel (which Slack channel receives the notification)
4. Save configuration

## Daily financial summary

Configure daily automated summaries:

1. Navigate to **Slack > Daily Summary**
2. Select **Enable Daily Summary**
3. Choose summary contents:
   - Cash position and changes
   - Daily revenue total
   - Daily expense total
   - Net income
   - Major transactions
4. Select time for daily delivery (e.g., 8am every business day)
5. Select destination channel
6. Save

Every morning, your team automatically gets a financial snapshot.

## Overdue invoice alerts

Keep track of outstanding receivables:

1. Configure **Invoice Overdue** notification
2. Set threshold: Alert when invoice is X days past due (e.g., 30 days)
3. Slack message includes:
   - Customer name
   - Invoice number and amount
   - Days past due
   - Link to invoice in Light for quick follow-up
4. Team members can click to view or take action

This ensures no invoice gets forgotten.

## Low cash alerts

Critical for cash management:

1. Configure **Low Cash Alert**
2. Set threshold: Alert when cash drops below X amount (e.g., $50,000)
3. Slack message includes:
   - Current cash balance
   - Percent of monthly operating expense
   - Forecast (based on outstanding AR/AP)
   - Recommendation to address cash shortfall
4. Enable escalation: If cash remains low, escalate to CFO after X hours

This prevents cash emergencies.

## Budget variance alerts

Monitor spending discipline:

1. Configure **Budget Variance** notification
2. Set threshold: Alert when actual > budget by X% (e.g., 10%)
3. Configure by department or overall
4. Slack message includes:
   - Department/account
   - Budgeted vs. actual amount
   - Variance percentage
   - Link to variance report
5. Department manager can acknowledge or dispute variance

This promotes spending accountability.

## Interactive Slack messages

Slack messages can include buttons for quick actions:

**Approve transaction**:
- Manager receives Slack message: "Invoice ABC from Vendor X for $10,000 awaiting approval"
- Manager clicks "Approve" button in Slack
- Light records approval
- No need to log in to Light

**View details**:
- Click "View Details" to see full transaction information
- Opens Light in browser to detailed view

**Deny/Reject**:
- For disputes or rejections, comment in Slack thread
- Light records the comment for audit trail

## Customizing message content

Configure what information appears in Slack notifications:

1. Navigate to **Slack > Message Templates**
2. For each notification type, customize:
   - Message heading
   - What data to include
   - Formatting (bold, emoji, color)
   - Call-to-action buttons
3. Use template variables ({{customer_name}}, {{amount}}, {{due_date}})
4. Save template

> Tip: Keep messages concise. Include enough detail to understand the issue but prompt quick action without forcing users to click.

## Approval workflows in Slack

Streamline approval workflows through Slack:

1. When a transaction requires approval, Slack notifies the approver
2. Approver reviews details in Slack message
3. Approver clicks "Approve" or "Deny" in Slack
4. Light records the decision with timestamp
5. Workflow proceeds (transaction posts, or feedback sent to creator)

This eliminates email approval bottlenecks.

## Grouping notifications by channel

Organize notifications by channel:

1. Create separate Slack channels:
   - **#finance-alerts**: Critical alerts (cash, overdue invoices)
   - **#daily-summary**: Daily financial reports
   - **#ap-approvals**: AP invoice approvals
   - **#ar-approvals**: AR invoice approvals
2. Configure notifications to post to appropriate channels
3. Team members subscribe to channels relevant to their role

This prevents notification overload and keeps channels focused.

## Troubleshooting Slack integration

**Messages not appearing**: Verify Light is authorized in your Slack workspace, check that the notification is enabled and threshold hasn't been met, test with manual trigger.

**Wrong channel**: Verify the channel is specified correctly in notification settings, ensure Light app has permission to post to that channel.

**Integration disconnected**: Re-authorize Slack integration, verify your Slack account hasn't revoked Light's permissions.

**Too many notifications**: Adjust thresholds to reduce noise, consider using Daily Summary instead of individual notifications.

## Monitoring Slack activity

Track Slack integration usage:

1. Navigate to **Settings (gear icon) > Integrations > Slack > Activity Log**
2. View:
   - Messages sent (count and content)
   - Failed messages
   - User interactions (approvals, denials)
3. Analyze whether notifications are effective

## Disabling specific notifications

If certain alerts are too noisy:

1. Navigate to **Slack > Notifications**
2. Toggle off notifications you don't want
3. Keep critical ones (low cash, large transactions)

You can always re-enable later.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Microsoft Teams integration](11-5-microsoft-teams.md)
- [Real-time dashboards and KPIs](../10-reporting/10-12-dashboards-kpis.md)
