---
# required metadata

title: Pause service updates through Lifecycle Services (LCS)
description: This topic explans how to pause service updates to your environments.
author: manalidongre
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Developer, IT Pro
# ms.devlang: 
ms.reviewer: sericks
ms.search.scope: Operations
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: Global
# ms.search.industry: 
ms.author: manado
ms.search.validFrom: 2019-3-31 
ms.dyn365.ops.version: Platform update 24 

---

# Pause service updates through Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

This topic explains how to pause updates to your sandbox and production environments by using Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> This feature is available only to customers who are using **version 8.1 and later** or are using **version 7.3**, and who are **not** part of the [First release](../../fin-and-ops/get-started/public-preview-releases.md) program. Microsoft is working to make the feature available to First release customers. For customers who are on version 7.1, 7.2, or 8.0, you can take the update manually using the regular servicing flows.

Microsoft updates your configured sandbox and production environments to the latest service update that Microsoft has released. Microsoft notifies you about upcoming updates to your environments via email and through notifications in LCS. At that point, if you can't proceed with the update for some reason, you can pause it through LCS.

For more information about how to change the configured sandbox environment and set the production update cadence, see [Configure service updates through Lifecycle Services (LCS)](configure-service-updates.md).

## Who can pause service updates?

Only users (customers or partners) who are assigned to the **project owner** role in LCS can pause updates. Additionally, updates can be paused only for **implementation projects**.

Staying current with service updates helps guarantee that customers always run on the latest set of fixes that Microsoft has released, so that they have the best service experience. Therefore, Microsoft doesn't allow updates to be paused indefinitely.

You can't pause updates through LCS if you're more than two updates behind the latest update that Microsoft has released. For example, if you are on version 8.1 and higher, if the last update that Microsoft released is version 8.1.3, customers who are using version 8.1.2 and version 8.1.1 **can** pause updates. However, a customer who is using version 8.1.0 **cannot** ppause updates, because they are more than two updates behind. For customers who are on version 7.3, you get platform updates only. For example, if the last platform update that Microsoft released is Platform update 24, then customers who are on Platform update 23 and update 22 **can** pause. However, if you are on Platform update 21, then you **cannot** pause. 

## What can I pause?

If you decide to pause updates, you have two options:

- Pause updates only to your production environment.
- Pause updates to both your sandbox environment and your production environment.

You can pause a maximum of two continuous updates at a time. (According to other information that may have been communicated to you, you can pause updates for up to three months. These two statements are consistent, because three months corresponds to two updates.) For example, if you're using version 8.1.3, you can pause update version 10.0.0 and update version 10.0.1. However, you can't pause update version 10.0.2. In addition, in the month of April, you can pause the next two updates. However, you will not be able to pause updates scheduled for July, August, and later. Similarly, for customers on version 7.3 for platform only updates, if you’re using Platform update 23 then you can pause update 24 and update 25, but you cannot pause update 26.

> [!IMPORTANT]
>  There is no way to pause more than two updates, regardless of your industry or business schedule. If you are more than 2 updates behind and you find a critical issue during validations in your sandbox environment after the update, you can contact Microsoft Support to pause the update to your production environment. This is only required if you are more than two updates behind and you are unable to use the pause updates functionality available in LCS to pause the update to production.

> If you pause updates to your sandbox environment, updates are automatically paused for your production environment too, because Microsoft always updates configured sandbox environments before production environments.

## How do I pause updates?

To pause updates, follow these steps.

1. In LCS, in your implementation project, open the **Project settings** page.

    This page has a new tab that is named **Update settings**.

2. On the **Update settings** tab, set the **Pause updates** option to **ON**.
3. Select **Edit settings**.
4. In the dialog box that appears, select whether you want to pause updates to your production environment only, or to both your sandbox environment and your production environment.
5. Select **Next**.
6. Select your reason for pausing updates. If you select **Issue found during validations**, you must enter a valid support ticket number. You can add any additional details that will help Microsoft understand why you want to pause updates.
7. When you've finished, select **Confirm**.

You can also edit an existing pause. You can either extend the duration of the pause, so that updates are paused for a longer time, or cancel it, so that updates are resumed. To edit a pause, select **Edit settings**. The limitations about the number of updates that you can pause still apply.

To cancel a pause and resume updates to your environments, set the **Pause updates** option to **OFF**.

Any time that you pause updates or edit an existing pause, a notification appears at the top of the **Update settings** tab. This notification shows what has been paused. An email is also sent to all stakeholders (the project owner and environment manager), to notify them that service updates for the selected environments have been paused. If someone cancels an existing pause and resumes updates, the notification disappears, and an email is sent to inform the stakeholders that updates have resumed.

> [!IMPORTANT]
> You can pause updates through LCS until four hours before the start of the downtime window.

## What happens after the pause duration expires?

Cumulative service updates help guarantee that customers always run on the latest set of fixes that Microsoft has released, so that they have the best service experience. Therefore, Microsoft doesn't allow updates to be paused indefinitely.

There are two ways to cancel pauses, so that updates are resumed:

- Someone manually cancels an ongoing pause, as explained in the previous section.
- The duration that was set for the pause expires, and updates to the configured environments are automatically resumed.

In both cases, an email is sent to inform the stakeholders.

For more information about service updates, see [One Version service updates FAQ](../../fin-and-ops/get-started/one-version.md).
