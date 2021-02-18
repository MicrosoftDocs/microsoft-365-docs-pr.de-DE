---
title: Nicht akzeptierter Domänenbericht im Nachrichtenflussdashboard
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
description: Administratoren können erfahren, wie Sie den Bericht über nicht akzeptierte Domänen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Nachrichten aus Ihrer lokalen Organisation zu überwachen, in denen die Domäne des Absenders nicht in Microsoft 365 konfiguriert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d7355af49c5810a593c5776b70cf7497b43af6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287865"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="ac946-103">Nicht akzeptierter Domänenbericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ac946-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac946-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ac946-104">**Applies to**</span></span>
- [<span data-ttu-id="ac946-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ac946-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ac946-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ac946-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ac946-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac946-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ac946-108">Der Bericht "Nicht akzeptierte Domäne" im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten von Ihrer lokalen E-Mail-Organisation an, in denen die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ac946-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="ac946-109">Microsoft 365 drosselt diese Nachrichten möglicherweise, wenn wir Daten haben, um nachzuweisen, dass die Absicht dieser Nachrichten böswillig ist.</span><span class="sxs-lookup"><span data-stu-id="ac946-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="ac946-110">Daher ist es wichtig, dass Sie verstehen, was geschieht, und das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ac946-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Nicht akzeptiertes Domänen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="ac946-112">Berichtsansicht für den Bericht über nicht akzeptierte Domänen</span><span class="sxs-lookup"><span data-stu-id="ac946-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="ac946-113">Wenn Sie auf das Diagramm im **Widget "Nicht akzeptierte** Domänen" klicken, werden Sie zum Bericht **"Nicht akzeptierte Domäne" geklickt.**</span><span class="sxs-lookup"><span data-stu-id="ac946-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="ac946-114">Standardmäßig wird die Aktivität für alle betroffenen Connectors angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac946-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="ac946-115">Wenn Sie auf **"Daten anzeigen" klicken,** können Sie in der Dropdownliste einen bestimmten Connector auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac946-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="ac946-116">Wenn Sie mit der Maus auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtanzahl der Nachrichten für den Connector angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac946-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Berichtsansicht im Bericht über nicht akzeptierte Domänen](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="ac946-118">Detailtabelle für den Bericht über nicht akzeptierte Domänen</span><span class="sxs-lookup"><span data-stu-id="ac946-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="ac946-119">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ac946-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ac946-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="ac946-120">**Date**</span></span>
- <span data-ttu-id="ac946-121">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="ac946-121">**Inbound connector name**</span></span>
- <span data-ttu-id="ac946-122">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="ac946-122">**Sender domain**</span></span>
- <span data-ttu-id="ac946-123">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="ac946-123">**Message count**</span></span>
- <span data-ttu-id="ac946-124">**Beispielmeldungen:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="ac946-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="ac946-125">Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="ac946-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ac946-126">Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**</span><span class="sxs-lookup"><span data-stu-id="ac946-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ac946-127">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ac946-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="ac946-128">**Date**</span><span class="sxs-lookup"><span data-stu-id="ac946-128">**Date**</span></span>
- <span data-ttu-id="ac946-129">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="ac946-129">**Inbound connector name**</span></span>
- <span data-ttu-id="ac946-130">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="ac946-130">**Sender domain**</span></span>
- <span data-ttu-id="ac946-131">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="ac946-131">**Message count**</span></span>
- <span data-ttu-id="ac946-132">**Beispielmeldungen:** Sie können auf "Beispielmeldungen **anzeigen"** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="ac946-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Details flyout after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="ac946-134">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="ac946-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac946-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ac946-135">Related topics</span></span>

<span data-ttu-id="ac946-136">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ac946-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
