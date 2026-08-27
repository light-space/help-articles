# HRM Integration (Finch)

Light connects to your HRM (Human Resource Management) system through Finch, so your employee directory keeps your Light users up to date.

[Open in Light →](https://app.light.inc/settings/integrations)

## What is this page about

This page covers how Light connects to your HRM system through Finch, which employee details arrive in Light, how often they refresh, and what Light needs from you to set the connection up. Read it before you start so you know what to have ready.

**On this page**

- How Light connects to HRM systems
- Data synced into Light
- Sync frequency
- User behaviour in Light
- Integration steps
- What Light needs from you
- Key points
- Related articles

## How Light connects to HRM systems

Light connects to HRM systems through **Finch**, a secure third-party connector that lists more than 200 supported HRM providers worldwide.

Check your own provider on Finch's list: [Finch Integrations](https://www.tryfinch.com/integrations). Your Customer Success Manager can confirm compatibility if you are unsure.

## Data synced into Light

Light imports your **employee directory** from your HRM and writes these details to each Light user:

- First and last name
- Email address
- Address, including street, city, postcode, and country
- Manager relation
- Active or inactive status

Entity comes from the HRM field you nominate. Until that mapping is in place, Light assigns new users to your default entity.

**Note:** The sync covers your employee directory. Pay and payroll figures stay in your HRM system, since Light requests only directory, individual, and employment data from Finch.

Light can also carry an HRM field such as department, team, or business unit into Light **groups**. Ask Light to add that mapping when you set up.

## Sync frequency

Finch notifies Light whenever an employee record changes, and Light processes those updates every 20 minutes.

Your first load of employees arrives on a separate initial sync, which runs as soon as Finch finishes its first pull of your organisation data. How long that takes depends on your provider.

How often Finch refreshes data from your HRM system after that also depends on your provider, typically daily or weekly.

## User behaviour in Light

When the HRM sync runs:

- Light creates a user for each employee who is **active** at the time of the sync, and adds them to the **Users** list
- Light deactivates a user when the matching employee is deactivated or terminated in your HRM, and keeps that user's history in place
- New users created by the sync receive the invoice approver role. Ask Light if you want a different default role

## Integration steps

### Step 1: Connect your HRM in Light

1. Go to **Settings (gear icon) → Integrations**
2. Click **Add integration**, then choose **HRM**
3. Read the **HRM Integration Charges** notice. HRM integration may add charges depending on your plan, and clicking **Confirm** accepts them. Contact Light support first if you want the details
4. Click **Confirm** to open the Finch login widget
5. Sign in with your **HRM admin credentials**

### Step 2: Light configures the mapping

Light's team then sets up the data mapping in the **HRM sync workflow**, using the details you supply below. This includes which HRM field identifies each employee's entity, which role new users receive, and any group mapping you have asked for.

### Step 3: First sync

Once the mapping is in place, Finch's first pull of your organisation data triggers the initial sync and your employees appear under **Users**.

## What Light needs from you

1. **Entity mapping field**
   - Which HRM field should Light use to identify each employee's **Entity**?
   - Examples: "Country of Employment", "Legal Entity", "Location"
   - Give the **exact field name**
2. **Group mapping field (optional)**
   - To carry department, team, or business unit information into Light, name the HRM field that holds it
   - Light maps that field onto user **groups**
   - Examples: "Department", "Team", "Business Unit"
3. **A different default role (optional)**
   - New users receive the invoice approver role unless you ask for another one
   - Tell Light which role you want new synced users to start with

**General rule**

| HRM Field name | HRM Field value | ⇒ | Light Field Name | Light Field value |
|---|---|---|---|---|
| | | ⇒ | | |

## Key points

- Light connects to HRM systems via **Finch**
- Light creates and deactivates Light users from your HRM data
- Light's team configures the mapping, using the entity field you nominate
- New synced users receive the invoice approver role by default
- The sync covers your employee directory, and pay figures stay in your HRM
- HRM integration may add charges depending on your plan

## Related articles

- [Integrations overview](https://light.inc/help/integrations/integrations-overview)
- [User roles and permissions](https://light.inc/help/user-management/roles-permissions-overview)
