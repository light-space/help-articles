# Italian SDI e-invoicing

SDI (Sistema di Interscambio) is Italy's mandatory e-invoicing system, operated by the Italian tax authority (Agenzia delle Entrate). Light sends and receives SDI invoices through its integration with Invopop. This article covers registering an Italian entity with SDI and routing incoming invoices to Light.

[Open in Light →](https://app.light.inc/settings/entities)

> Good to know: SDI is specific to Italy. For cross-border EU e-invoicing, see the [Peppol article](/articles/02-organization-setup/2-7-e-invoicing-peppol).

## Registering your entity with SDI

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities) and open your Italian entity
2. Make sure the entity's country is set to **Italy** and its **VAT number** (Partita IVA) is filled in. A **Business registration number** (Codice Fiscale) is also recommended
3. In the **E-invoicing** section, click **Add**
4. Select the **Invopop** provider and the **SDI** network
5. Choose a **Registration type**: **Sending and receiving** (default) or **Sending only**
6. Click **Next**

Registration is fully automatic, with no document verification step. It shows as **Processing** while the registration completes, then turns **Active**. If it fails, the onboarding details show the reason. Fix it (for example, an invalid Partita IVA) and start the registration again by clicking **Add** in the entity's **E-invoicing** section.

> Good to know: SDI does not use an EAS code or e-invoice address, so these fields stay empty on your entity. This is expected.

If you chose **Sending and receiving**, there is one more step: register the Codice Destinatario below so incoming invoices reach Light.

## Route incoming invoices to Light (Codice Destinatario)

SDI delivers incoming invoices based on the Codice Destinatario registered with the tax authority. To receive supplier invoices in Light, register Invopop's code `JKKZDGR` for each Italian entity:

1. Log in to the [Agenzia delle Entrate portal](https://ivaservizi.agenziaentrate.gov.it/portale/) with credentials for the company being registered (SPID, CIE, CNS, or Entratel)
2. Open **Fatture e Corrispettivi**
3. In the **Fatturazione elettronica** box, select **Registrazione delle modalità di ricezione della fattura elettronica**
4. Choose the **Codice Destinatario** option and enter `JKKZDGR`
5. Confirm with **Conferma**

Incoming invoices now appear in Light automatically. Until you complete this step, supplier invoices won't reach Light.

> Important: Registering `JKKZDGR` replaces any previously registered Codice Destinatario. Complete the switch before decommissioning your old invoicing channel.

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
