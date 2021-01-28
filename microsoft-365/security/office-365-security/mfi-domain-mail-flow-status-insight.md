---
title: Einblick in den Nachrichtenflussstatus der obersten Domäne im Dashboard für den Nachrichtenfluss
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
description: Administratoren können erfahren, wie Sie den Einblick in den Nachrichtenflussstatus der obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Probleme mit dem Nachrichtenfluss im Zusammenhang mit ihren MX-Einträgen zu behandeln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029906"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="7f2ed-103">Einblick in den Nachrichtenflussstatus der obersten Domäne im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7f2ed-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7f2ed-104">Die **Einblicke in den** Nachrichtenflussstatus der obersten Domäne im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) bieten Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="7f2ed-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="7f2ed-105">Dieser Einblick hilft Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei deren Nachrichtenfluss \**_Probleme_* auftreten.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="7f2ed-106">Beispielsweise kann die Domäne keine externe E-Mail empfangen, weil die Domäne abgelaufen ist oder die Domäne über einen falschen MX-Eintrag verfügt.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget für den Status der obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="7f2ed-108">Wenn Sie im Widget *auf* _Details  anzeigen \* klicken, wird ein #A0 mit weiteren Details zum Status jeder Domäne angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f2ed-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="7f2ed-109">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="7f2ed-109">**Domain**</span></span>
- <span data-ttu-id="7f2ed-110">**Vorheriger MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="7f2ed-110">**Previous MX record**</span></span>
- <span data-ttu-id="7f2ed-111">**Aktueller MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="7f2ed-111">**Current MX record**</span></span>
- <span data-ttu-id="7f2ed-112">**Status des E-Mail-Empfangs**</span><span class="sxs-lookup"><span data-stu-id="7f2ed-112">**Email receiving status**</span></span>
- <span data-ttu-id="7f2ed-113">**Domänenstatus:** Ein grünes Häkchen zeigt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir aufgezeichnet haben, und die Domäne hat in den letzten zwei Stunden E-Mails empfangen.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="7f2ed-114">Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine E-Mails empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="7f2ed-115">Dies weist wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="7f2ed-116">Überprüfen Sie bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="7f2ed-117">Sie können auf **"Weitere Informationen anzeigen"** klicken, um die gleichen Informationen für weitere Domänen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7f2ed-117">You can click **View more** to see the same information for more domains.</span></span>

![Details-Flyout im Einblick in den E-Mail-Flussstatus der obersten Domäne](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="7f2ed-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f2ed-119">See also</span></span>

<span data-ttu-id="7f2ed-120">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="7f2ed-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
