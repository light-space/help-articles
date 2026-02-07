# Microsoft Teams Integration

Microsoft Teams is the enterprise messaging and collaboration platform used by many organizations. Light's Teams integration sends real-time financial notifications and enables approval workflows directly within Teams, just like the Slack integration.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Teams integration enables:

- **Financial alerts**: Notifications for overdue invoices, low cash, budget overages
- **Approval workflows**: Request and approve transactions in Teams
- **Daily summaries**: Automated daily financial summaries
- **Custom notifications**: Configure which events trigger Teams messages
- **Interactive cards**: Click actions in Teams (approve, view details)

This integrates Light's financial alerts into your existing Teams communication.

## Setting up Teams integration

To connect Teams:

1. Navigate to **Settings (gear icon) > Integrations > Microsoft Teams**
2. Click **Connect**
3. You're redirected to Microsoft to authorize
4. Sign in with your Microsoft 365 account
5. Select the Teams workspace and channel where notifications appear
6. Review permissions Light is requesting
7. Click **Authorize**
8. Light confirms the connection and sends a test message

Next, configure which notifications you want.

## Configuring Teams notifications

Define which financial events trigger Teams messages:

1. Navigate to **Settings > Integrations > Teams > Notifications**
2. Toggle on notifications:

   **Invoice notifications**:
   - Invoice created
   - Invoice overdue (configurable threshold)
   - Invoice paid

   **Cash notifications**:
   - Daily cash summary
   - Low cash alert (with configurable threshold)
   - Large transaction alert

   **Budget notifications**:
   - Budget variance (when actual exceeds budget by configured %)
   - Category overage
   - Department spending limits

   **AP notifications**:
   - Supplier bills coming due
   - Payments made

3. For each notification, set:
   - Alert threshold (e.g., "alert if cash < $50,000")
   - Frequency (daily, weekly, or on-demand)
   - Recipient team/channel
4. Save

## Daily financial summaries in Teams

Automate daily financial updates:

1. Navigate to **Teams > Daily Summary**
2. Select **Enable Daily Summary**
3. Choose what to include:
   - Cash position and movement
   - Revenue (daily total)
   - Expenses (daily total)
   - Net income
   - Top transactions
   - Budget variance summary
4. Set delivery time (e.g., 8am weekdays)
5. Select destination channel
6. Save

Your team receives a daily financial snapshot in Teams without manual work.

## Overdue invoice notifications in Teams

Track AR aging in Teams:

1. Configure **Invoice Overdue** notification
2. Set threshold: Alert at 30 days past due (or your preference)
3. Teams message includes:
   - Customer name
   - Invoice number and amount
   - Days past due
   - Link to invoice in Light
4. Team member clicks "View Invoice" to open Light
5. Or click "Send Reminder" to trigger customer payment reminder

This ensures AR doesn't fall through the cracks.

## Low cash warnings

Critical alerts for cash management:

1. Configure **Low Cash Alert**
2. Set threshold: Alert when cash drops below specified amount
3. Teams message shows:
   - Current cash balance
   - Daily burn rate
   - Runway (estimated days until cash runs out)
   - Forecast based on committed AR/AP
   - Suggested actions (reduce spending, accelerate collections)
4. Enable escalation: Escalate to CFO after 24 hours if not addressed

This prevents cash emergencies through real-time visibility.

## Budget variance alerts in Teams

Monitor departmental spending:

1. Configure **Budget Variance** notification
2. Set threshold: Alert when actual exceeds budget by 10% (configurable)
3. Filter by department or account
4. Teams message includes:
   - Department/account name
   - Budgeted vs. actual amount
   - Variance percentage
   - YTD spending trend
   - Link to variance report
5. Department manager can acknowledge in Teams

This drives spending accountability through visible alerts.

## Approval workflows in Teams

Enable approval workflows within Teams:

1. When a transaction requires approval, Teams notifies the approver
2. Approval card appears in Teams with:
   - Transaction summary (type, amount, description)
   - "Approve" and "Deny" buttons
3. Approver clicks button
4. Light records approval with timestamp and user
5. Transaction status updates (proceeds or returns to creator)

This eliminates back-and-forth emails.

## Interactive Teams cards

Teams messages support rich formatting:

**Approval card**:
- Shows transaction details clearly
- Approve/Deny buttons
- Link to full details in Light
- Comment field for feedback

**Alert card**:
- Shows metric (cash, overdue AR, budget variance)
- Threshold and current value
- Visual indicator (green/yellow/red)
- Action link

**Summary card**:
- Daily financial snapshot
- Multiple metrics at a glance
- Drill-down links to Light

## Customizing notification messages

Control what appears in Teams:

1. Navigate to **Teams > Message Templates**
2. For each notification type, customize:
   - Message title
   - Content fields
   - Color and formatting
   - Action buttons
   - Call-to-action
3. Use template variables ({{customer_name}}, {{amount}}, {{days_overdue}})
4. Preview how message will appear
5. Save

Keep messages clear and actionable.

## Channel organization

Structure Teams for financial notifications:

1. Create dedicated channels:
   - **#finance-alerts**: Critical alerts (low cash, major transactions)
   - **#daily-summary**: Daily financial reports
   - **#ap-approvals**: Payable invoice approvals
   - **#ar-aging**: Overdue receivables tracking
   - **#budget-variance**: Spending alerts
2. Configure notifications to post to appropriate channels
3. Users follow channels relevant to their role

This prevents notification overwhelm and keeps channels focused.

## Managing notification volume

If you're receiving too many notifications:

1. Increase alert thresholds (e.g., alert only when > $50,000 instead of > $10,000)
2. Reduce frequency (weekly instead of daily)
3. Use Daily Summary instead of individual alerts
4. Disable less critical notification types
5. Filter by department or entity

Balance insight with signal-to-noise ratio.

## Testing the integration

Before relying on Teams notifications:

1. Navigate to **Teams > Test Connection**
2. Send a test message to verify connectivity
3. Check that message appears in your Teams channel
4. Click on message to verify links to Light work
5. If using approval workflows, test approval process

This ensures the integration is working before critical alerts depend on it.

## Troubleshooting Teams integration

**Messages not appearing**: Verify Light is authorized in Teams, check that notification is enabled, verify the channel exists and Light has permission to post.

**Wrong channel**: Verify channel name in notification settings, ensure Light app can access that channel.

**Integration disconnected**: Re-authorize Teams integration through Settings, verify your Microsoft 365 account hasn't revoked Light permissions.

**Approval not working**: Ensure approver has Light account, verify approval workflow is configured, test with manual approval trigger.

**Too many notifications**: Adjust thresholds to reduce volume, consider consolidating into Daily Summary.

## Monitoring Teams activity

Track Teams integration usage:

1. Navigate to **Settings > Integrations > Teams > Activity**
2. View:
   - Messages sent (count, content, timestamps)
   - Failed messages (with error details)
   - User interactions (approvals, denials)
   - Effectiveness (are users acting on notifications?)

Use this to optimize notification configuration.

## Exporting Teams conversation history

Archive important notifications:

1. In Teams channel, use Teams' export feature to save channel history
2. Includes all Light notifications
3. Useful for audit trail and compliance

Light also maintains server-side records of all notifications sent.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Slack integration](11-4-slack.md)
- [Real-time dashboards and KPIs](../10-reporting/10-12-dashboards-kpis.md)
