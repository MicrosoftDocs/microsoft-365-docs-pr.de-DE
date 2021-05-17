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
description: Administratoren erfahren, wie Sie die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie E-Mails über Connectors und ohne Connectors zu und von ihrer Organisation fließen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206961"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="57880-103">Nachrichtenflusszuordnung im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="57880-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57880-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="57880-104">**Applies to**</span></span>
- [<span data-ttu-id="57880-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57880-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="57880-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="57880-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="57880-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57880-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="57880-108">Die **Nachrichtenflusskarte** im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) gibt Einblick in den E-Mail-Fluss in Ihrer Organisation. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="57880-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="57880-109">Sie können diese Informationen verwenden, um Muster zu erlernen, Anomalien zu identifizieren und Probleme bei deren Auftreten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="57880-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Nachrichtenflusszuordnungs-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="57880-111">Standardmäßig zeigt das Widget das Nachrichtenflussmuster vom Vortag in einem Diagramm an, das als *Sankey-Diagramm bezeichnet* wird.</span><span class="sxs-lookup"><span data-stu-id="57880-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="57880-112">Sie können den Pfeil nach links und nach rechts zum Anzeigen von Informationen aus ![ ](../../media/scc-left-arrow.png) verschiedenen Tagen ![ ](../../media/scc-right-arrow.png) verwenden.</span><span class="sxs-lookup"><span data-stu-id="57880-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="57880-113">Jede unterschiedliche Farbe stellt den Nachrichtenfluss über einen anderen ein- oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar.</span><span class="sxs-lookup"><span data-stu-id="57880-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="57880-114">Wenn Sie den Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57880-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="57880-115">Berichtsansicht für die Nachrichtenflusskarte</span><span class="sxs-lookup"><span data-stu-id="57880-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="57880-116">Wenn Sie auf das **Widget "Nachrichtenflusszuordnung"** klicken, werden Sie zum **Bericht "Nachrichtenflusszuordnung"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57880-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="57880-117">Die folgenden Diagramme sind in der Berichtsansicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="57880-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="57880-118">**Daten anzeigen für: Übersicht**: Dies ist im Wesentlichen eine größere Ansicht des Widgets.</span><span class="sxs-lookup"><span data-stu-id="57880-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="57880-119">Wenn Sie den Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57880-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Übersichtsansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="57880-121">**Daten anzeigen für: Detail**: Diese Ansicht zeigt Details zu den Connectors und Zieldomänen.</span><span class="sxs-lookup"><span data-stu-id="57880-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="57880-122">Die Top-Absender- und Empfängerdomänen werden aufgelistet, und der Rest wird in **Andere angegeben.**</span><span class="sxs-lookup"><span data-stu-id="57880-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="57880-123">Wenn Sie auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57880-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detailansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="57880-125">Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="57880-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="57880-126">Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**</span><span class="sxs-lookup"><span data-stu-id="57880-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="57880-127">Verwandte Einblicke werden unterhalb der Nachrichtenflusskarte angezeigt, wenn sie verfügbar sind (z. B. die Möglichkeit einer E-Mail-Schleife [beheben).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="57880-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="57880-128">Detailtabelle für die Nachrichtenflusszuordnung</span><span class="sxs-lookup"><span data-stu-id="57880-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="57880-129">Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="57880-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="57880-130">**Date**</span><span class="sxs-lookup"><span data-stu-id="57880-130">**Date**</span></span>
- <span data-ttu-id="57880-131">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="57880-131">**Category**</span></span>
- <span data-ttu-id="57880-132">**Connector/Drittanbieter**</span><span class="sxs-lookup"><span data-stu-id="57880-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="57880-133">**Absender-Empfänger-Domäne**</span><span class="sxs-lookup"><span data-stu-id="57880-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="57880-134">**Anzahl der Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="57880-134">**Message count**</span></span>

<span data-ttu-id="57880-135">Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**</span><span class="sxs-lookup"><span data-stu-id="57880-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="57880-136">Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="57880-136">If you select a row, similar details are shown in a flyout:</span></span>

![Details flyout aus der Detailtabelle in der Nachrichtenflusskarte](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="57880-138">Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**</span><span class="sxs-lookup"><span data-stu-id="57880-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="57880-139">Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="57880-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="57880-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57880-140">See also</span></span>

<span data-ttu-id="57880-141">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="57880-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
