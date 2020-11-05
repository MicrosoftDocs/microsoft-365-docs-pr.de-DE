---
title: Beheben eines möglichen Einblicks in den E-Mail-Loop
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Fix possible Mail Loop Insight im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um e-Mail-Schleifen in Ihrer Organisation zu identifizieren und zu beheben.
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920565"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="17328-103">Beheben möglicher Einblicke in die e-Mail-Schleife im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="17328-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="17328-104">E-Mail-Schleifen sind schlecht, da:</span><span class="sxs-lookup"><span data-stu-id="17328-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="17328-105">Sie verschwenden Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="17328-105">They waste system resources.</span></span>
- <span data-ttu-id="17328-106">Sie nutzen das Kontingent für das e-Mail-Volumen Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="17328-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="17328-107">Sie senden verwirrende Unzustellbarkeitsberichte (auch bekannt als NDR oder Unzustellbarkeitsnachrichten) an die ursprünglichen Nachrichtenabsender.</span><span class="sxs-lookup"><span data-stu-id="17328-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="17328-108">Mit dem **Fix possible Mail Loop** Insight im Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) werden Sie benachrichtigt, wenn eine e-Mail-Schleife in Ihrer Organisation erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="17328-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="17328-109">Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="17328-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="17328-111">Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="17328-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="17328-112">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="17328-112">**Domain**</span></span>
- <span data-ttu-id="17328-113">**Anzahl von Nachrichten** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Schleife betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="17328-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="17328-114">**Domain-Typ** "beispielsweise autorisierend oder nicht autorisierend.</span><span class="sxs-lookup"><span data-stu-id="17328-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="17328-115">**MX-Eintrag** : der Host ( **e-Mail-Server** ) und die **Prioritäts** Werte des MX-Eintrags für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="17328-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="17328-116">**Grund für Loop** und **How to Fix** : Wir werden die gängigsten e-Mail-Schleifen Szenarien identifizieren und empfohlene Aktionen zum Beheben der Schleife bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="17328-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details anzeigen in der Fix possible Mail Loop Insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="17328-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17328-118">See also</span></span>

<span data-ttu-id="17328-119">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="17328-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
