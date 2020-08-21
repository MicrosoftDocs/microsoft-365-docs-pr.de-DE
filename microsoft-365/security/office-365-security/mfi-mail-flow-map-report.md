---
title: Zuordnung der Nachrichtenübermittlung
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
description: Administratoren können erfahren, wie Sie die e-Mail-Fluss Zuordnung im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie e-Mail-Nachrichten zu und von Ihrer Organisation über Connectors und ohne Connectors verwendet werden.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827001"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="4d091-103">Nachrichtenfluss Zuordnung im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4d091-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="4d091-104">Die **e-Mail-Fluss Übersicht** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center gibt Einblicke in die Art und Weise, wie e-Mail-Nachrichten durch Ihre Organisation fließt.</span><span class="sxs-lookup"><span data-stu-id="4d091-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="4d091-105">Sie können diese Informationen verwenden, um Muster zu erfahren, Anomalien zu identifizieren und Probleme zu beheben, wenn Sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="4d091-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Nachrichtenfluss-Zuordnungs Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="4d091-107">Standardmäßig zeigt das Widget das Nachrichtenfluss Muster aus dem vorherigen Tag in einem Diagramm an, das als *Sankey* -Diagramm bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="4d091-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="4d091-108">Sie können den nach-links-Pfeil nach links ![ ](../../media/scc-left-arrow.png) und nach-rechts-Pfeil verwenden ![ ](../../media/scc-right-arrow.png) , um Informationen aus unterschiedlichen Tagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4d091-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="4d091-109">Jede andere Farbe stellt die Nachrichtenübermittlung über einen anderen eingehenden oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar.</span><span class="sxs-lookup"><span data-stu-id="4d091-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="4d091-110">Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diese Art von Connector angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d091-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="4d091-111">Berichtsansicht für die Nachrichtenfluss Zuordnung</span><span class="sxs-lookup"><span data-stu-id="4d091-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="4d091-112">Durch Klicken auf das Widget **"Nachrichtenfluss-Zuordnung** " gelangen Sie zum Bericht **"Nachrichtenfluss Karte** ".</span><span class="sxs-lookup"><span data-stu-id="4d091-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="4d091-113">Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4d091-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4d091-114">**Daten anzeigen für: Overview**: Dies ist im Wesentlichen eine größere Ansicht des Widgets.</span><span class="sxs-lookup"><span data-stu-id="4d091-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="4d091-115">Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diese Art von Connector angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d091-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Übersichtsansicht im Bericht "Nachrichtenfluss Übersicht"](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="4d091-117">**Daten anzeigen für: Detail: in**dieser Ansicht werden Details zu den Connectors und Zieldomänen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d091-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="4d091-118">Die obersten Absender-und Empfängerdomänen werden aufgelistet, und die restlichen werden in **andere**eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4d091-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="4d091-119">Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d091-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detail Ansicht im Nachrichtenfluss-Zuordnungsbericht](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="4d091-121">Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="4d091-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4d091-122">Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="4d091-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="4d091-123">Zugehörige Einblicke werden unterhalb der Nachrichtenfluss Zuordnung angezeigt, wenn Sie verfügbar sind (beispielsweise die [Fix possible Mail Loop Insight](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="4d091-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="4d091-124">Tabellenansicht "Details" für die Nachrichtenfluss Zuordnung</span><span class="sxs-lookup"><span data-stu-id="4d091-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="4d091-125">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d091-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4d091-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d091-126">**Date**</span></span>
- <span data-ttu-id="4d091-127">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="4d091-127">**Category**</span></span>
- <span data-ttu-id="4d091-128">**Connector/Drittanbieter-Dienstanbieter**</span><span class="sxs-lookup"><span data-stu-id="4d091-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="4d091-129">**Absender/Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="4d091-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="4d091-130">**Nachrichtenanzahl**</span><span class="sxs-lookup"><span data-stu-id="4d091-130">**Message count**</span></span>

<span data-ttu-id="4d091-131">Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.</span><span class="sxs-lookup"><span data-stu-id="4d091-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4d091-132">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d091-132">If you select a row, similar details are shown in a flyout:</span></span>

![Details-Flyout aus der Detailtabelle der Nachrichtenfluss Zuordnung](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="4d091-134">Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="4d091-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="4d091-135">Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="4d091-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d091-136">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="4d091-136">See also</span></span>

<span data-ttu-id="4d091-137">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4d091-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
