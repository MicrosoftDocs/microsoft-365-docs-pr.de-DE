---
title: Top-Domain-Nachrichtenflussstatus Einblicke im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Nachrichtenflussstatus "Top Domain" im Nachrichtenfluss-Dashboard im Security & Compliance Center Nachrichtenflussprobleme im Zusammenhang mit MX-Einträgen in Ihren e-Mail-Domänen behandeln.
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827015"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="dd9d1-103">Top-Domain-Nachrichtenflussstatus Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dd9d1-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="dd9d1-104">Der **Nachrichtenflussstatus "Top Domain"** im [Nachrichten](mail-flow-insights-v2.md) Fluss-Dashboard im Security & Compliance Center gibt Ihnen den aktuellen Status für die Domänen Ihrer Organisation im Hinblick auf den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="dd9d1-105">Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, die sich auf Probleme mit dem ***e-Mail-Fluss auswirken*** (beispielsweise kann keine externe e-Mail empfangen werden), vor allem Domänen Ablauf oder Domänen mit falschen MX-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Top Domain Flow Status widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="dd9d1-107">Wenn Sie im Widget auf **Details anzeigen** klicken, wird ein Flyout für **Domänenstatus** angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten:</span><span class="sxs-lookup"><span data-stu-id="dd9d1-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="dd9d1-108">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="dd9d1-108">**Domain**</span></span>
- <span data-ttu-id="dd9d1-109">**Vorheriger MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="dd9d1-109">**Previous MX record**</span></span>
- <span data-ttu-id="dd9d1-110">**Aktueller MX-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="dd9d1-110">**Current MX record**</span></span>
- <span data-ttu-id="dd9d1-111">**E-Mail-Empfangsstatus**</span><span class="sxs-lookup"><span data-stu-id="dd9d1-111">**Email receiving status**</span></span>
- <span data-ttu-id="dd9d1-112">**Domänenstatus**: ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Datensatz haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="dd9d1-113">Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und dass die Domäne während der letzten 6 Stunden keine e-Mails erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="dd9d1-114">Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="dd9d1-115">Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="dd9d1-116">Sie können auf **mehr anzeigen** klicken, um dieselben Informationen für weitere Domänen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9d1-116">You can click **View more** to see the same information for more domains.</span></span>

![Detail-Flyout im Nachrichtenflussstatus der oberen Domäne Insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="dd9d1-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dd9d1-118">Related topics</span></span>

<span data-ttu-id="dd9d1-119">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="dd9d1-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
