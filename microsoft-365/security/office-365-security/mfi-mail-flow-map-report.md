---
title: Zuordnung der Nachrichtenübermittlung
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
description: Administratoren können erfahren, wie Sie die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie E-Mails über Connectors und ohne Connectors zu und von ihrer Organisation fließen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c07730f3abcec8905285cdfdf1579ffb71573ec1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029918"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="f2bce-103">Nachrichtenflusszuordnung im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f2bce-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f2bce-104">Die **Nachrichtenflusszuordnung** im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) bietet Einblicke in den E-Mail-Fluss in Ihrer Organisation. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="f2bce-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="f2bce-105">Sie können diese Informationen verwenden, um Muster zu erlernen, Anomalien zu identifizieren und Probleme zu beheben, während sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="f2bce-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget für die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="f2bce-107">Standardmäßig zeigt das Widget das Nachrichtenflussmuster vom vorigen Tag in einem Diagramm an, das als *"Sankey"-Diagramm bezeichnet* wird.</span><span class="sxs-lookup"><span data-stu-id="f2bce-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="f2bce-108">Sie können den Nach-links-Pfeil und den Pfeil nach rechts verwenden, um Informationen aus ![ ](../../media/scc-left-arrow.png) verschiedenen Tagen ![ ](../../media/scc-right-arrow.png) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2bce-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="f2bce-109">Jede unterschiedliche Farbe stellt den Nachrichtenfluss über einen anderen eingehenden oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar.</span><span class="sxs-lookup"><span data-stu-id="f2bce-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="f2bce-110">Wenn Sie mit der Maus auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2bce-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="f2bce-111">Berichtsansicht für die Nachrichtenflusszuordnung</span><span class="sxs-lookup"><span data-stu-id="f2bce-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="f2bce-112">Wenn Sie auf das **Widget für die Nachrichtenflusszuordnung** klicken, werden Sie zum **Bericht "Nachrichtenflusszuordnung" geklickt.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="f2bce-113">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f2bce-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f2bce-114">**Anzeigen von Daten für: Übersicht:** Dies ist im Wesentlichen eine größere Ansicht des Widgets.</span><span class="sxs-lookup"><span data-stu-id="f2bce-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="f2bce-115">Wenn Sie mit der Maus auf eine bestimmte Farbe zeigen, wird die Anzahl der Meldungen für diesen Connectortyp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2bce-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Übersichtsansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="f2bce-117">**Daten anzeigen für: Detail:** Diese Ansicht zeigt Details zu den Connectors und Zieldomänen.</span><span class="sxs-lookup"><span data-stu-id="f2bce-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="f2bce-118">Die am besten verwendeten Absender- und Empfängerdomänen werden aufgelistet, und der Rest wird in **"Andere" angegeben.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="f2bce-119">Wenn Sie mit der Maus auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2bce-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detailansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="f2bce-121">Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f2bce-122">Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="f2bce-123">Verwandte Einblicke werden unter der Nachrichtenflusszuordnung angezeigt, wenn sie verfügbar sind (z. B. der Einblick in die mögliche E-Mail-Schleife [korrigieren).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="f2bce-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="f2bce-124">Detailtabelle für die Nachrichtenflusszuordnung</span><span class="sxs-lookup"><span data-stu-id="f2bce-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="f2bce-125">Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2bce-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f2bce-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="f2bce-126">**Date**</span></span>
- <span data-ttu-id="f2bce-127">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="f2bce-127">**Category**</span></span>
- <span data-ttu-id="f2bce-128">**Connector/Drittanbieter**</span><span class="sxs-lookup"><span data-stu-id="f2bce-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="f2bce-129">**Absender-/Empfängerdomäne**</span><span class="sxs-lookup"><span data-stu-id="f2bce-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="f2bce-130">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="f2bce-130">**Message count**</span></span>

<span data-ttu-id="f2bce-131">Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f2bce-132">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2bce-132">If you select a row, similar details are shown in a flyout:</span></span>

![Detailf flyout aus der Detailtabelle in der Nachrichtenflusszuordnung](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="f2bce-134">Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="f2bce-135">Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="f2bce-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2bce-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2bce-136">See also</span></span>

<span data-ttu-id="f2bce-137">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="f2bce-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
