---
title: Akku Einblicke
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 81b7a7c3db69d1c20f9a9cd8c6ea4a37b481ce59
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269386"
---
# <a name="battery-insights"></a><span data-ttu-id="52016-103">Akku Einblicke</span><span class="sxs-lookup"><span data-stu-id="52016-103">Battery insights</span></span>
<span data-ttu-id="52016-104">Diese Ansicht enthält Metriken für Energie, Akku und App-Nutzung für Ihre von Microsoft verwalteten Desktop Geräte.</span><span class="sxs-lookup"><span data-stu-id="52016-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="52016-105">Für diese Zwecke wird eine App als "in Verwendung" betrachtet, wenn Sie aktiv ist und sich im Fokus befindet.</span><span class="sxs-lookup"><span data-stu-id="52016-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="52016-106">Um Verwendungsdaten anzuzeigen, wählen Sie die Registerkarte **Akku** aus.</span><span class="sxs-lookup"><span data-stu-id="52016-106">To view usage data, select the **Battery** tab.</span></span>

![Batteriebereich: prognostizierte Batterielebensdauer pro Gerätemodell oben links, Top Energy Consumers (by APP) in der oberen rechten Ecke, Insights-Tabelle auf der unteren Seite.](images/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="52016-109">Prognostizierte Akkulaufzeit</span><span class="sxs-lookup"><span data-stu-id="52016-109">Predicted battery life</span></span>

<span data-ttu-id="52016-110">Im Bereich der **prognostizierten Akkulaufzeit** stellen wir Vorhersagen für die erwartete Akkulaufzeit Ihrer Geräte bereitgestellt, geordnet nach dem Gerätemodell.</span><span class="sxs-lookup"><span data-stu-id="52016-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="52016-111">Diese Daten stammen aus einer Stichprobenahme von Energieverbrauch, Nutzungszeit und Batteriekapazität aus einer zufälligen <em>Auswahl</em> der Geräte in Ihrer Microsoft Managed Desktop-Bereitstellung, die auch Daten melden.</span><span class="sxs-lookup"><span data-stu-id="52016-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="52016-112">Die Tabelle enthält die prognostizierte Batterielebensdauer (in Stunden), die durchschnittliche Lebensdauer der Batterie für dieselben Modelle in anderen Microsoft Managed Desktop-Bereitstellungen sowie die Anzahl der Geräte, die diese Daten in Ihrer Umgebung melden.</span><span class="sxs-lookup"><span data-stu-id="52016-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="52016-113">Sortieren Sie die Daten, indem Sie die Spaltenüberschriften auswählen.</span><span class="sxs-lookup"><span data-stu-id="52016-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="52016-114">Top Energy Consumer</span><span class="sxs-lookup"><span data-stu-id="52016-114">Top energy consumers</span></span>

<span data-ttu-id="52016-115">Im Bereich der **oberen Energieverbraucher** finden Sie die apps in Ihrer Umgebung, die die meiste Energie in milliWatt-Stunden (MWh) verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="52016-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="52016-116">Die gezeigten apps sind pro spezifischem Gerät, das Sie im Abschnitt " **voraussichtliche Lebensdauer der Batterie** " Links auswählen.</span><span class="sxs-lookup"><span data-stu-id="52016-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="52016-117">Wenn Sie beispielsweise den pro-App-Verbrauch für Ihre Microsft Surface Book 2-Geräte anzeigen möchten, wählen Sie diese Zeile im Batterie Nutzungsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="52016-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="52016-118">Wenn Sie kein Modell auswählen, werden die angezeigten App-Nutzungsdaten für alle apps angezeigt, für die wir Daten gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="52016-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="52016-119">Für jede APP zeigen farbige Segmente die Verteilung der Energieverwendung der app in den folgenden Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="52016-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="52016-120">CPU</span><span class="sxs-lookup"><span data-stu-id="52016-120">CPU</span></span>
- <span data-ttu-id="52016-121">Anzeige</span><span class="sxs-lookup"><span data-stu-id="52016-121">Display</span></span>
- <span data-ttu-id="52016-122">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="52016-122">Network</span></span>
- <span data-ttu-id="52016-123">Andere</span><span class="sxs-lookup"><span data-stu-id="52016-123">Other</span></span>

<span data-ttu-id="52016-124">"Sonstiges" könnte den Energieverbrauch durch eine Vielzahl von Quellen wie Datenträgeraktivität, mobile Breitbandnutzung und Energieverlust im internen Widerstand einschließen.</span><span class="sxs-lookup"><span data-stu-id="52016-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="52016-125">Sie können diese Ansicht filtern, um nur Vordergrund-apps, Hintergrund-Apps oder beides anzuzeigen, indem Sie das Menü in der oberen rechten Ecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="52016-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="52016-126">Apps im Vordergrund sind solche, die in den letzten 28 Tagen Benutzerinteraktion hatten, beispielsweise das Auswählen von etwas mit einer Maus.</span><span class="sxs-lookup"><span data-stu-id="52016-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="52016-127">Insights</span><span class="sxs-lookup"><span data-stu-id="52016-127">Insights</span></span>

<span data-ttu-id="52016-128">Der Bereich " **Insights** " zeigt die drei wichtigsten Energieverbraucher in den Kategorien CPU und Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="52016-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="52016-129">Diese Elemente verbrauchen mehr als die durchschnittliche Energie im Vergleich zu allen Microsoft Managed Desktop-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="52016-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="52016-130">Die Anzeige Ressource wird nicht angezeigt, da Sie stark von der Geräte Nutzungszeit und den Bildschirm Helligkeitseinstellungen abhängt.</span><span class="sxs-lookup"><span data-stu-id="52016-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="52016-131">Wählen Sie die Auflistungen in der Spalte **Details** aus, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="52016-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="52016-132">Batterieoptimierung</span><span class="sxs-lookup"><span data-stu-id="52016-132">Battery optimization</span></span>

<span data-ttu-id="52016-133">Windows 10 bietet zahlreiche [Geräteeinstellungen](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) , um den Energieverbrauch zu verbessern und die Akkulaufzeit Ihrer verwalteten Microsoft-Desktop Geräte zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="52016-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="52016-134">Einige dieser Einstellungen können andere Windows-Funktionen verringern, sodass Sie auch andere Faktoren wie die Rolle des Geräts in Ihrer Organisation berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="52016-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="52016-135">Die Windows-Unterstützung enthält eine Liste dieser [Tipps zum Speichern von Akkus](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="52016-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="52016-136">Benutzer können einige Einstellungen selbst anpassen, ohne dass Sie eine Administrator Erweiterung oder-Unterstützung benötigen.</span><span class="sxs-lookup"><span data-stu-id="52016-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="52016-137">Andere Einstellungen erfordern Unterstützung durch den IT-Administrator Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="52016-137">Other settings require support from your organization's IT administrator.</span></span>
