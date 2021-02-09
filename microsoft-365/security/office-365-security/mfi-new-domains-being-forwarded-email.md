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
description: Administratoren können erfahren, wie Sie die neuen Domänen, die per E-Mail weitergeleitet werden, im E-Mail-Flussdashboard im Security & Compliance Center verwenden, um zu untersuchen, ob ihre Benutzer Nachrichten an externe Domänen weiterleiten, an die noch nie weitergeleitet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150601"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="0532d-103">Neue Domänen, die E-Mail-Einblicke im Security & Compliance Center weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="0532d-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0532d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0532d-104">**Applies to**</span></span>
- [<span data-ttu-id="0532d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0532d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="0532d-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="0532d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="0532d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0532d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="0532d-108">Es gibt gültige geschäftliche Gründe für die Weiterleitung von E-Mail-Nachrichten an externe Empfänger in bestimmten Domänen.</span><span class="sxs-lookup"><span data-stu-id="0532d-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="0532d-109">Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an eine Domäne weiterleiten, an die niemand in Ihrer Organisation Nachrichten weitergeleitet hat (eine neue Domäne).</span><span class="sxs-lookup"><span data-stu-id="0532d-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="0532d-110">Diese Bedingung weist möglicherweise darauf hin, dass die Benutzerkonten gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="0532d-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="0532d-111">Wenn Sie vermuten, dass die Konten gefährdet wurden, lesen Sie ["Reagieren auf ein gefährdetes E-Mail-Konto".](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="0532d-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="0532d-112">The **New domains being forwarded email** insight in the Security & Compliance [Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span><span class="sxs-lookup"><span data-stu-id="0532d-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="0532d-113">Dieser Einblick wird nur angezeigt, wenn das Problem erkannt wird, und er wird auf der Seite ["Weiterleitungsbericht"](view-mail-flow-reports.md#forwarding-report) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0532d-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="0532d-115">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden, einschließlich eines Links zurück zum [Weiterleitungsbericht.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="0532d-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Details-Flyout, das angezeigt wird, nachdem sie auf die E-Mail-Einblicke für neue Domänen geklickt haben](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="0532d-117">Sie können auch zu dieser Detailseite gelangen,  wenn Sie die Einblicke auswählen, nachdem Sie im Bereich "Top insights" **&** **(** Berichtsdashboard oder ) auf "Alle anzeigen" geklickt \>  haben. <https://protection.office.com/insightdashboard></span><span class="sxs-lookup"><span data-stu-id="0532d-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="0532d-118">Um die automatische Nachrichten weiterleitung an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="0532d-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="0532d-119">Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="0532d-119">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0532d-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0532d-120">Related topics</span></span>

<span data-ttu-id="0532d-121">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="0532d-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
