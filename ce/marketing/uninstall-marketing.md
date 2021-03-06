---
title: "Uninstall Dynamics 365 for Marketing (Dynamics 365 for Marketing) | Microsoft Docs"
description: "How to remove Dynamics 365 for Marketing from a Dynamics 365 for Customer Engagement instance"
keywords: uninstall;solutions;administration;instances
ms.date: 04/01/2018
ms.service: dynamics-365-marketing
ms.custom: 
  - dyn365-marketing
ms.topic: article
applies_to: 
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
ms.assetid: 76871891-d62c-4496-81f6-60b31bf5e3e6
author: kamaybac
ms.author: kamaybac
manager: shellyha
ms.reviewer:
topic-status: Drafting
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365Mktg
---

# Uninstall Marketing

[!INCLUDE[cc_applies_to_update_9_0_0](../includes/cc_applies_to_update_9_0_0.md)]

You can remove [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] from any [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] instance where you have installed it. After removing it, you'll end up with a free [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] entitlement (license) that you can install on another [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] instance if needed.

The uninstall process has three steps:

1. Prepare to uninstall by removing sample data and customer journeys.
1. Uninstall the [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] services by running the uninstall wizard.
1. Clean up the [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] solutions in [!INCLUDE[pn-dynamics-365](../includes/pn-dynamics-365.md)].

## Prepare to uninstall

Before you uninstall any [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] components, start by removing any sample data and data dependencies from your [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] instance by doing the following:

1. If you have sample data installed, remove it. [!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Manage sample data](additional-settings.md).
1. Remove all customer journeys that include launch-workflow and/or record-updated tiles because these introduce data dependencies that can interfere with the uninstall. You might consider deleting all your journeys if you don't need them anymore. [!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Create automated campaigns with customer journeys](customer-journeys-create-automated-campaigns.md)

## Uninstall the [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] services
The [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] uninstall wizard manages most of the uninstall process. It:

- Removes all [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)], event management, and [!INCLUDE[cc-linkedin-solution](../includes/cc-linkedin-solution.md)] services from your [!INCLUDE[pn-dynamics-365](../includes/pn-dynamics-365.md)] application server.
- Removes your customer-insights services and their data.
- Turns off user syncing from [!INCLUDE[pn-ms-office-365](../includes/pn-ms-office-365.md)] for [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-only users.
- Frees your [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] entitlement (license) for use with another [!INCLUDE[pn-dynamics-365](../includes/pn-dynamics-365.md)] instance if needed.

To run the uninstall wizard:

1. [Open the Dynamics 365 admin center](dynamics-365-admin-center.md).

1. To see a list of applications you have installed, select the **Applications** tab.  
    ![Open the Applications tab](media/update-app-tab.png "Open the Applications tab")

    The list shows a row named **Dynamics 365 for Marketing Application** for each entitlement (license) you have for [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]. Free entitlements (which can't be uninstalled) show a **Status** of **Not configured**. Installed entitlements show a **Status** of **Configured** and include the name of the instance where they are installed as part of their application name.

1. Select the configured [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] entitlement that you want to uninstall, and then select the **Manage** button ![The Manage button](media/update-manage-button.png "The Manage button") in the side panel.

1. The [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] setup wizard opens.  It shows the name of the [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] instance (organization) from which you are about to remove [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]. Confirm that you selected the right one.  
    ![Choose the Uninstall Marketing link](media/uninstall-wizard.png "Choose the Uninstall Marketing link")

1. Under **Other actions**, select **Uninstall Marketing from this org**.

1. Follow the instructions on your screen to confirm and complete the uninstall.

## Remove [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] solutions in [!INCLUDE[pn-dynamics-365](../includes/pn-dynamics-365.md)]
The uninstall wizard removes the [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] services from your [!INCLUDE[pn-dynamics-365](../includes/pn-dynamics-365.md)] server, but it leaves several solutions on your instance. You should clean these up to help keep your instance lean and running smoothly.

> [!NOTE]
> The following procedure lists the uninstall order for solutions that are included in the latest version of [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]. If you are uninstalling an earlier version, then just skip over any solution listed here that you don't see on your installation.

To remove the services:

1. Use the app selector to go to the [!INCLUDE[pn-custom-app-module](../includes/pn-custom-app-module.md)] app.  
    ![The app-selector menu](media/nav-apps-custom-ill.png "The app-selector menu")

1. To view the list of solutions installed in the custom app, go to **Settings** > **Customizations** > **Solutions**.

1. Find each of the following solutions and remove them, one at a time, in the order listed here. To remove a solution, select its check box, and then select **Delete** on the command bar. [!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Install, update, or remove a preferred solution](../admin/install-remove-preferred-solution.md)

    - MicrosoftDynamics_MktEmailTemplates (if present)
    - MicrosoftDynamics_MktPortalsLink
    - MicrosoftDynamics_EvtMgmtPortalsLink
    - MicrosoftDynamics_EvtMgmtVocLink
    - MicrosoftDynamics_MktVocLink
    - MicrosoftDynamics_MktVocIntegration
    - MicrosoftDynamics_GwennolOptimalEmailSendingTime
    - MicrosoftDynamics_MktIntegration
    - MicrosoftDynamics_SocialEngagement
    - MicrosoftDynamics_LinkedInMatchedAudiences
    - MicrosoftDynamics_MktLeadGenLink
    - MicrosoftDynamics_MktConsentManagement
    - MicrosoftDynamics_MktQuotaInfo
    - MicrosoftDynamics_MktPageTemplates (if present)
    - MicrosoftDynamics_MktEvtMgmtLink
    - MicrosoftDynamics_MktLeadManagement
    - MicrosoftDynamics_Marketing
    - MicrosoftDynamics_EventManagement
    - MicrosoftDynamics_ReusableBlocks
    - MicrosoftDynamics_DigitalAssets
    - MicrosoftDynamics_Calendar
    - MicrosoftDynamics_MktVocEmailAnchorSolution
    - SMBMarketingDemoData (if present)

1. If you see any other "anchor" solutions that start with "MicrosoftDynamics_", then you can delete these too. They are probably left over from an earlier version that you upgraded.

1. If you're no longer using the [!include[](../includes/cc-linkedin-solution.md)], then also remove the LinkedInLeadGenIntegration solution.

1. If you're no longer using portal or [!INCLUDE[pn-voice-of-the-customer](../includes/pn-voice-of-the-customer.md)] functionality, you can also delete their related solutions.

### See also

[Open the Dynamics 365 admin center](dynamics-365-admin-center.md)  
[Keep Marketing up to date](apply-updates.md)  
[Manage Marketing instances](manage-marketing-instances.md)  
