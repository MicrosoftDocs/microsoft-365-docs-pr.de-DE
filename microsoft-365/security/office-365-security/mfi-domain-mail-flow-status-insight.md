---
title: Übersicht über den Status des Nachrichtenflusses der obersten Domäne im Dashboard für den Nachrichtenfluss
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie die Informationen zum Statusstatus der Nachrichtenflussstatus der Obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Probleme mit dem Nachrichtenfluss im Zusammenhang mit ihren MX-Einträgen zu behandeln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206971"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="ba347-103">Informationen zum Status des Nachrichtenflusses der obersten Domäne im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ba347-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ba347-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ba347-104">**Applies to**</span></span>
- [<span data-ttu-id="ba347-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ba347-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ba347-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ba347-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ba347-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba347-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ba347-108">Die **Übersicht über den** Status des Nachrichtenflusses der obersten Domäne im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) gibt Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ba347-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="ba347-109">Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei deren ***Nachrichtenfluss Probleme auftreten.***</span><span class="sxs-lookup"><span data-stu-id="ba347-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="ba347-110">Beispielsweise kann die Domäne keine externen E-Mails empfangen, da die Domäne abgelaufen ist oder die Domäne über einen falschen MX-Eintrag verfügt.</span><span class="sxs-lookup"><span data-stu-id="ba347-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget "Top Domain Flow Status" im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="ba347-112">Wenn Sie im **Widget** auf Details anzeigen klicken, wird ein **Flyout** für den Domänenstatus angezeigt, das Ihnen weitere Details zum Status jeder Domäne zeigt:</span><span class="sxs-lookup"><span data-stu-id="ba347-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="ba347-113">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="ba347-113">**Domain**</span></span>
- <span data-ttu-id="ba347-114">**Vorheriger MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="ba347-114">**Previous MX record**</span></span>
- <span data-ttu-id="ba347-115">**Aktueller MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="ba347-115">**Current MX record**</span></span>
- <span data-ttu-id="ba347-116">**E-Mail-Empfangsstatus**</span><span class="sxs-lookup"><span data-stu-id="ba347-116">**Email receiving status**</span></span>
- <span data-ttu-id="ba347-117">**Domänenstatus:** Ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir auf dem Datensatz haben, und die Domäne hat in den letzten zwei Stunden E-Mails empfangen.</span><span class="sxs-lookup"><span data-stu-id="ba347-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="ba347-118">Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine E-Mails erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="ba347-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ba347-119">Dies bedeutet wahrscheinlich, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ba347-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ba347-120">Überprüfen Sie bei Ihrer Domänenregistrierungsstelle oder ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.</span><span class="sxs-lookup"><span data-stu-id="ba347-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="ba347-121">Sie können auf **Weitere Informationen anzeigen klicken,** um die gleichen Informationen für weitere Domänen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ba347-121">You can click **View more** to see the same information for more domains.</span></span>

![Details flyout in der Statusanzeige für den Nachrichtenfluss der obersten Domäne](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="ba347-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba347-123">See also</span></span>

<span data-ttu-id="ba347-124">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ba347-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
