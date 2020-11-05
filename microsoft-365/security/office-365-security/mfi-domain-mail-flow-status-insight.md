---
title: Top-Domain-Nachrichtenflussstatus Einblicke im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Nachrichtenflussstatus "Top Domain" im Nachrichtenfluss-Dashboard im Security & Compliance Center Probleme bei der Nachrichtenübermittlung im Zusammenhang mit Ihren MX-Einträgen beheben.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920584"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="29259-103">Top-Domain-Nachrichtenflussstatus Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="29259-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="29259-104">Der **Nachrichtenflussstatus "Top Domain"** im [Nachrichten](mail-flow-insights-v2.md) Fluss-Dashboard im [Security & Compliance Center](https://protection.office.com) gibt Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="29259-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="29259-105">Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei denen \* *_e-Mail-Fluss_* _ Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="29259-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="29259-106">Beispielsweise kann die Domäne keine externen e-Mails empfangen, weil die Domäne abgelaufen ist oder die Domäne einen falschen MX-Eintrag aufweist.</span><span class="sxs-lookup"><span data-stu-id="29259-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Top Domain Flow Status widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="29259-108">Wenn Sie auf _ *Details anzeigen* \* im Widget klicken, wird ein Flyout für **Domänenstatus** angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten:</span><span class="sxs-lookup"><span data-stu-id="29259-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="29259-109">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="29259-109">**Domain**</span></span>
- <span data-ttu-id="29259-110">**Vorheriger MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="29259-110">**Previous MX record**</span></span>
- <span data-ttu-id="29259-111">**Aktueller MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="29259-111">**Current MX record**</span></span>
- <span data-ttu-id="29259-112">**E-Mail-Empfangsstatus**</span><span class="sxs-lookup"><span data-stu-id="29259-112">**Email receiving status**</span></span>
- <span data-ttu-id="29259-113">**Domänenstatus** : ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Eintrag haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="29259-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="29259-114">Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine e-Mails erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="29259-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="29259-115">Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="29259-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="29259-116">Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.</span><span class="sxs-lookup"><span data-stu-id="29259-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="29259-117">Sie können auf **mehr anzeigen** klicken, um dieselben Informationen für weitere Domänen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="29259-117">You can click **View more** to see the same information for more domains.</span></span>

![Detail-Flyout im Nachrichtenflussstatus der oberen Domäne Insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="29259-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29259-119">See also</span></span>

<span data-ttu-id="29259-120">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="29259-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
