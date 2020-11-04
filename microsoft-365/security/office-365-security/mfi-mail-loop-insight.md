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
ms.openlocfilehash: 15ad5c467d18ce3038bcb05db798a9b5a7c3e391
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877505"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="47a64-103">Beheben möglicher Einblicke in die e-Mail-Schleife im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="47a64-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="47a64-104">Eine e-Mail-Schleife ist schlecht, da Sie Systemressourcen verschwendet, das Kontingent für das e-Mail-Volumen Ihres Unternehmens verwendet und verwirrende Unzustellbarkeitsberichte (auch bekannt als NDR oder Unzustellbarkeitsnachrichten) an die ursprünglichen Absender sendet.</span><span class="sxs-lookup"><span data-stu-id="47a64-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="47a64-105">Mit dem **Fix possible Mail Loop** Insight im Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) werden Sie benachrichtigt, wenn eine e-Mail-Schleife in Ihrer Organisation erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="47a64-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="47a64-106">Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="47a64-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="47a64-108">Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="47a64-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="47a64-109">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="47a64-109">**Domain**</span></span>
- <span data-ttu-id="47a64-110">**Anzahl von Nachrichten** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Schleife betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="47a64-110">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="47a64-111">**Domain-Typ** "beispielsweise autorisierend oder nicht autorisierend.</span><span class="sxs-lookup"><span data-stu-id="47a64-111">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="47a64-112">**MX-Eintrag** : der Host ( **e-Mail-Server** ) und die **Prioritäts** Werte des MX-Eintrags für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="47a64-112">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="47a64-113">**Schleifen Grund** und **How to Fix** : Wir werden versuchen, die gängigsten e-Mail-Schleifen Szenarien zu identifizieren und die empfohlenen Aktionen bereitzustellen (falls verfügbar), um die Schleife zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="47a64-113">**Loop reason** and **How to fix** : We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details anzeigen in der Fix possible Mail Loop Insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="47a64-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="47a64-115">Related topics</span></span>

<span data-ttu-id="47a64-116">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="47a64-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
