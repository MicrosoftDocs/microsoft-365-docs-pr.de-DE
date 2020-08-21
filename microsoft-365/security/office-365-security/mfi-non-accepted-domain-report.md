---
title: Bericht "nicht akzeptierte Domäne" im Nachrichtenfluss-Dashboard
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
description: Administratoren können erfahren, wie Sie den Bericht nicht akzeptierte Domäne im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um Nachrichten von Ihrer lokalen Organisation zu überwachen, in denen die Domäne des Absenders in Microsoft 365 nicht konfiguriert ist.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826941"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="f1c70-103">Bericht über nicht akzeptierte Domänen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f1c70-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="f1c70-104">Der Bericht **nicht akzeptierte Domäne** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center zeigt Informationen zu Nachrichten von Ihrer lokalen e-Mail-Organisation an, in der die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f1c70-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="f1c70-105">Microsoft 365 kann diese Nachrichten Drosseln, wenn wir Daten haben, um zu beweisen, dass die Absicht dieser Nachrichten bösartig ist.</span><span class="sxs-lookup"><span data-stu-id="f1c70-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="f1c70-106">Daher ist es wichtig, dass Sie verstehen, was passiert, und das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f1c70-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget "nicht akzeptierte Domäne" im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="f1c70-108">Berichtsansicht für den Bericht "nicht akzeptierte Domäne"</span><span class="sxs-lookup"><span data-stu-id="f1c70-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="f1c70-109">Durch Klicken auf das Diagramm im Widget " **nicht akzeptierte Domäne** " gelangen Sie zum Bericht " **nicht akzeptierte Domäne** ".</span><span class="sxs-lookup"><span data-stu-id="f1c70-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="f1c70-110">Standardmäßig wird die Aktivität für alle betroffenen Konnektoren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c70-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="f1c70-111">Wenn Sie auf **Daten anzeigen für**klicken, können Sie einen bestimmten Konnektor aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="f1c70-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="f1c70-112">Wenn Sie mit dem Mauszeiger auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtzahl der Nachrichten für den Connector angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c70-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Berichtsansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="f1c70-114">Detailtabellen Ansicht für den Bericht "nicht akzeptierte Domäne"</span><span class="sxs-lookup"><span data-stu-id="f1c70-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="f1c70-115">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f1c70-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f1c70-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="f1c70-116">**Date**</span></span>
- <span data-ttu-id="f1c70-117">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="f1c70-117">**Inbound connector name**</span></span>
- <span data-ttu-id="f1c70-118">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="f1c70-118">**Sender domain**</span></span>
- <span data-ttu-id="f1c70-119">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="f1c70-119">**Message count**</span></span>
- <span data-ttu-id="f1c70-120">**Beispiel Meldungen**: die Nachrichten-IDs einer Stichprobe betroffener Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f1c70-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="f1c70-121">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="f1c70-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f1c70-122">Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="f1c70-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="f1c70-123">Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f1c70-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="f1c70-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="f1c70-124">**Date**</span></span>
- <span data-ttu-id="f1c70-125">**Name des eingehenden Connectors**</span><span class="sxs-lookup"><span data-stu-id="f1c70-125">**Inbound connector name**</span></span>
- <span data-ttu-id="f1c70-126">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="f1c70-126">**Sender domain**</span></span>
- <span data-ttu-id="f1c70-127">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="f1c70-127">**Message count**</span></span>
- <span data-ttu-id="f1c70-128">**Beispiel Meldungen**: Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der betroffenen Nachrichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1c70-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Detail Flyout nach dem Auswählen einer Zeile in der Detailtabellen Ansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="f1c70-130">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f1c70-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1c70-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f1c70-131">Related topics</span></span>

<span data-ttu-id="f1c70-132">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="f1c70-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
