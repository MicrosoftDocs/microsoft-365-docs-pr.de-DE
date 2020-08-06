---
title: Neue Domänen werden weitergeleitet e-Mail Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratoren können erfahren, wie Sie die neuen Domänen, die als e-Mail-Insight weitergeleitet werden, in der modernen Exchange-Verwaltungskonsole verwenden, um zu untersuchen, wann Benutzer in Ihrer Organisation Nachrichten an externe domänenweiter leiten, an die noch nie weitergeleitet wurde.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578394"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="b9e6e-103">Neue Domänen werden weitergeleitet e-Mail-Insight im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b9e6e-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="b9e6e-104">Obwohl Sie möglicherweise über gültige geschäftliche Gründe für die Weiterleitung von e-Mail-Nachrichten an externe Empfänger in bestimmten Domänen verfügen, ist es verdächtig, wenn Benutzer in Ihrer Organisation plötzlich Nachrichten an externe domänenweiter leiten und niemand in der Organisation zuvor Nachrichten an diese domänenweiter geleitet hat (neue Domänen).</span><span class="sxs-lookup"><span data-stu-id="b9e6e-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="b9e6e-105">Diese Bedingung kann darauf hindeuten, dass die Benutzerkonten kompromittiert sind.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="b9e6e-106">Wenn Sie vermuten, dass die Konten kompromittiert wurden, finden Sie weitere Informationen unter [reagieren auf ein kompromittiertes e-Mail-Konto](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="b9e6e-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="b9e6e-107">Die **neuen Domänen, die in e-Mail-Insight weitergeleitet** werden, erhalten eine Benachrichtigung, wenn Benutzer in Ihrer Organisation Nachrichten an neue domänenweiter leiten.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="b9e6e-108">Diese Einblicke wird nur angezeigt, wenn das Problem erkannt wird und auf der Seite [weiterleitender Bericht](view-mail-flow-reports.md#forwarding-report) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Neue Domänen werden weitergeleitet e-Mail Insight](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="b9e6e-110">Wenn Sie auf das Widget klicken, wird ein Flyout angezeigt, in dem Sie weitere Details zu den weitergeleiteten Nachrichten finden können, darunter einen Link zurück zum [Weiterleitungs Bericht](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="b9e6e-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Details-Flyout, das nach dem Klicken auf die weiterzuleitenden neuen Domänen angezeigt wird e-Mail Insight](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="b9e6e-112">Sie können diese Detailseite auch aufrufen, wenn Sie die Einblicke auswählen, nachdem Sie auf **Alle anzeigen** im Bereich **Top Insights & Empfehlungen** auf (**Berichte** \> - **Dashboard** oder <https://protection.office.com/insightdashboard> ) klicken.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="b9e6e-113">Um die automatische Weiterleitung von Nachrichten an externe Domänen zu verhindern, konfigurieren Sie eine Remotedomäne für einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="b9e6e-114">Weitere Informationen finden Sie unter [Verwalten von Remotedomänen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="b9e6e-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9e6e-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b9e6e-115">Related topics</span></span>

<span data-ttu-id="b9e6e-116">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="b9e6e-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
