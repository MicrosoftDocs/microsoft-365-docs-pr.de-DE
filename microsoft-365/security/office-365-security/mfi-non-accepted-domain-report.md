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
description: Administratoren erfahren, wie Sie den Nicht akzeptierten Domänenbericht im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Nachrichten aus Ihrer lokalen Organisation zu überwachen, in der die Domäne des Absenders nicht in Microsoft 365 konfiguriert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206334"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="67ea8-103">Nicht akzeptierter Domänenbericht im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="67ea8-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67ea8-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="67ea8-104">**Applies to**</span></span>
- [<span data-ttu-id="67ea8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="67ea8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="67ea8-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="67ea8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67ea8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67ea8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="67ea8-108">Der Bericht Nicht akzeptierter [](mail-flow-insights-v2.md) Domänen im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten aus Ihrer lokalen **E-Mail-Organisation** an, in denen die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="67ea8-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="67ea8-109">Microsoft 365 kann diese Nachrichten drosseln, wenn wir Daten zum Nachweis haben, dass die Absicht dieser Nachrichten bösartig ist.</span><span class="sxs-lookup"><span data-stu-id="67ea8-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="67ea8-110">Daher ist es wichtig, dass Sie verstehen, was geschieht, und das Problem beheben.</span><span class="sxs-lookup"><span data-stu-id="67ea8-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Nicht akzeptiertes Domänen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="67ea8-112">Berichtsansicht für den Nicht akzeptierten Domänenbericht</span><span class="sxs-lookup"><span data-stu-id="67ea8-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="67ea8-113">Wenn Sie im Widget Nicht **akzeptierte** Domänen auf das Diagramm klicken, werden Sie zum **Bericht Nicht akzeptierter Domänen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67ea8-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="67ea8-114">Standardmäßig wird die Aktivität für alle betroffenen Connectors angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67ea8-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="67ea8-115">Wenn Sie auf **Daten anzeigen für klicken,** können Sie in der Dropdownliste einen bestimmten Connector auswählen.</span><span class="sxs-lookup"><span data-stu-id="67ea8-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="67ea8-116">Wenn Sie auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtanzahl der Nachrichten für den Connector angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67ea8-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Berichtsansicht im Nicht akzeptierten Domänenbericht](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="67ea8-118">Detailtabelle für den Nicht akzeptierten Domänenbericht</span><span class="sxs-lookup"><span data-stu-id="67ea8-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="67ea8-119">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="67ea8-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="67ea8-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="67ea8-120">**Date**</span></span>
- <span data-ttu-id="67ea8-121">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="67ea8-121">**Inbound connector name**</span></span>
- <span data-ttu-id="67ea8-122">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="67ea8-122">**Sender domain**</span></span>
- <span data-ttu-id="67ea8-123">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="67ea8-123">**Message count**</span></span>
- <span data-ttu-id="67ea8-124">**Beispielnachrichten:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="67ea8-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="67ea8-125">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="67ea8-126">Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="67ea8-127">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="67ea8-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="67ea8-128">**Date**</span><span class="sxs-lookup"><span data-stu-id="67ea8-128">**Date**</span></span>
- <span data-ttu-id="67ea8-129">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="67ea8-129">**Inbound connector name**</span></span>
- <span data-ttu-id="67ea8-130">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="67ea8-130">**Sender domain**</span></span>
- <span data-ttu-id="67ea8-131">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="67ea8-131">**Message count**</span></span>
- <span data-ttu-id="67ea8-132">**Beispielnachrichten:** Sie können auf **Beispielnachrichten anzeigen klicken,** um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="67ea8-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Details flyout nach dem Auswählen einer Zeile in der Tabellenansicht Details im Nicht akzeptierten Domänenbericht](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="67ea8-134">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67ea8-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="67ea8-135">Related topics</span></span>

<span data-ttu-id="67ea8-136">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="67ea8-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
