---
title: Einblick in E-Mails von neue Domänen, die weitergeleitet werden
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie den Einblick in die E-Mail-Weiterleitung neuer Domänen im E-Mail-Flussdashboard im Security & Compliance Center verwenden, um zu untersuchen, ob ihre Benutzer Nachrichten an externe Domänen weiterleiten, an die noch nie weitergeleitet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029858"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="0447d-103">Neue Domänen, die E-Mail-Einblicke im Security & Compliance Center weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="0447d-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0447d-104">Es gibt gültige geschäftliche Gründe für die Weiterleitung von E-Mail-Nachrichten an externe Empfänger in bestimmten Domänen.</span><span class="sxs-lookup"><span data-stu-id="0447d-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="0447d-105">Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an eine Domäne weiterleiten, an die niemand in Ihrer Organisation Nachrichten weitergeleitet hat (eine neue Domäne).</span><span class="sxs-lookup"><span data-stu-id="0447d-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="0447d-106">Diese Bedingung weist möglicherweise darauf hin, dass die Benutzerkonten gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="0447d-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="0447d-107">Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="0447d-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="0447d-108">Der **Einblick in die E-Mail-Weiterleitung** neuer Domänen im Security & Compliance [Center](https://protection.office.com) benachrichtigt Sie, wenn Benutzer in Ihrer Organisation Nachrichten an neue Domänen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0447d-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="0447d-109">Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0447d-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="0447d-111">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zurück zum [Weiterleitungsbericht.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="0447d-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Details-Flyout, das angezeigt wird, nachdem sie auf die E-Mail-Einblicke für neue Domänen geklickt haben](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="0447d-113">Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top **insights" auf** "Alle einblicke" &**(** Berichtsdashboard oder ) geklickt \>  <https://protection.office.com/insightdashboard> haben.</span><span class="sxs-lookup"><span data-stu-id="0447d-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="0447d-114">Um die automatische Nachrichten weiterleitung an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="0447d-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="0447d-115">Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="0447d-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0447d-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0447d-116">Related topics</span></span>

<span data-ttu-id="0447d-117">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="0447d-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
