---
title: Übersicht über den Top-Domain-e-Mail-Datenstrom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 'Administratoren können sich im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center über den Nachrichtenflussstatus "Top Domain" informieren.'
ms.openlocfilehash: 1fb22ac1543c490dcbd316464803f5393003d503
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598882"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="9ee31-103">Übersicht über den Top-Domain-e-Mail-Datenstrom</span><span class="sxs-lookup"><span data-stu-id="9ee31-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="9ee31-104">In der **oberen Domäne der Nachrichtenflussstatus** Insight erhalten Sie den aktuellen Status für die Domänen Ihrer Organisation im Hinblick auf den Nachrichtenfluss.</span><span class="sxs-lookup"><span data-stu-id="9ee31-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="9ee31-105">Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, die sich auf Probleme mit dem ***e-Mail-Fluss auswirken*** (beispielsweise kann keine externe e-Mail empfangen werden), vor allem Domänen Ablauf oder Domänen mit falschen MX-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="9ee31-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Der obere Domänen Fluss Status – Einblicke im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center](../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="9ee31-107">Wenn Sie in der Insight auf **Details anzeigen** klicken, wird ein Flyout angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ee31-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="9ee31-108">Ein grünes Häkchen für eine Domäne gibt an, dass der aktuelle MX-Eintrag (beim Browsen in das Nachrichtenfluss-Einblicke-Dashboard) dem Wert entspricht, den wir im Datensatz haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="9ee31-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="9ee31-109">Ein rotes x für eine Domäne gibt an, dass der MX-Eintrag geändert wurde und dass in den letzten 6 Stunden keine e-Mails für die Domäne empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="9ee31-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="9ee31-110">Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9ee31-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="9ee31-111">Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.</span><span class="sxs-lookup"><span data-stu-id="9ee31-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![Das Detail-Flyout im oberen Bereich der Domänen-Flow-Status Einblicke](../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="9ee31-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ee31-113">See also</span></span>

<span data-ttu-id="9ee31-114">Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security #a0 Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9ee31-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
