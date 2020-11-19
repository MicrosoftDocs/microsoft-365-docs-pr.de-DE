---
title: Einblick in E-Mails von neue Domänen, die weitergeleitet werden
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie die neuen Domänen, die als e-Mail-Insight weitergeleitet werden, im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um zu untersuchen, wann Ihre Benutzer Nachrichten an externe domänenweiter leiten, an die noch nie weitergeleitet wurden.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356943"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="8ddda-103">Neue Domänen werden weitergeleitet e-Mail-Insight im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8ddda-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8ddda-104">Es gibt gültige geschäftliche Gründe für die Weiterleitung von e-Mail-Nachrichten an externe Empfänger in bestimmten Domänen.</span><span class="sxs-lookup"><span data-stu-id="8ddda-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="8ddda-105">Es ist jedoch verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an eine Domäne weiterleiten, in der niemand in Ihrer Organisation Nachrichten an (eine neue Domäne) weitergeleitet hat.</span><span class="sxs-lookup"><span data-stu-id="8ddda-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="8ddda-106">Diese Bedingung deutet möglicherweise darauf hin, dass die Benutzerkonten gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="8ddda-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="8ddda-107">Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="8ddda-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="8ddda-108">Die **neuen Domänen, die als e-Mail-Insight weitergeleitet** werden, werden vom [Security & Compliance Center](https://protection.office.com) benachrichtigt, wenn Benutzer in Ihrer Organisation Nachrichten an neue domänenweiter leiten.</span><span class="sxs-lookup"><span data-stu-id="8ddda-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="8ddda-109">Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ddda-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Einblick in E-Mails von neue Domänen, die weitergeleitet werden](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="8ddda-111">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, darunter einen Link zurück zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="8ddda-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Details-Flyout, das nach dem Klicken auf die weiterzuleitenden neuen Domänen angezeigt wird e-Mail Insight](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="8ddda-113">Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.</span><span class="sxs-lookup"><span data-stu-id="8ddda-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="8ddda-114">Um die automatische Weiterleitung von Nachrichten an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="8ddda-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="8ddda-115">Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="8ddda-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8ddda-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8ddda-116">Related topics</span></span>

<span data-ttu-id="8ddda-117">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8ddda-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
