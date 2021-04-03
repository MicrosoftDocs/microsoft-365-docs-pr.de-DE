---
title: Akku-Einblicke
description: Ein Bericht, der Daten über die vorhergesagte Akkulaufzeit und die besten Stromverbraucher enthält
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579710"
---
# <a name="battery-insights"></a><span data-ttu-id="34497-104">Akku-Einblicke</span><span class="sxs-lookup"><span data-stu-id="34497-104">Battery insights</span></span>
<span data-ttu-id="34497-105">Diese Ansicht bietet Leistungs-, Akku- und App-Nutzungsmetriken für Ihre Microsoft Managed Desktop-Geräte.</span><span class="sxs-lookup"><span data-stu-id="34497-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="34497-106">Zu diesen Zwecken wird eine App als "in Gebrauch" betrachtet, wenn sie ausgeführt wird und im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="34497-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="34497-107">Wählen Sie zum Anzeigen von Verwendungsdaten die Registerkarte **Akku** aus.</span><span class="sxs-lookup"><span data-stu-id="34497-107">To view usage data, select the **Battery** tab.</span></span>

![Akkubereich: Vorhergesagte Akkulaufzeit pro Gerätemodell oben links, Energieverbraucher (per App) oben rechts, Einblicke tabelle unten.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="34497-110">Vorhergesagte Akkulaufzeit</span><span class="sxs-lookup"><span data-stu-id="34497-110">Predicted battery life</span></span>

<span data-ttu-id="34497-111">Im Bereich **Vorhergesagte** Akkulaufzeit bieten wir Vorhersagen für die erwartete Akkulaufzeit für Ihre Geräte, organisiert nach Gerätemodell.</span><span class="sxs-lookup"><span data-stu-id="34497-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="34497-112">Diese Daten werden aus einer zufälligen Auswahl der Geräte <em></em> in Ihrer Microsoft Managed Desktop-Bereitstellung abgeleitet, die auch Daten melden.</span><span class="sxs-lookup"><span data-stu-id="34497-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="34497-113">Die Tabelle enthält die vorhergesagte Akkulaufzeit (in Stunden), die durchschnittliche Akkulaufzeit für dieselben Modelle in anderen Microsoft Managed Desktop-Bereitstellungen und die Anzahl der Geräte, die diese Daten in Ihrer Umgebung melden.</span><span class="sxs-lookup"><span data-stu-id="34497-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="34497-114">Sortieren Sie die Daten, indem Sie die Spaltenüberschriften auswählen.</span><span class="sxs-lookup"><span data-stu-id="34497-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="34497-115">Energieverbraucher am meisten</span><span class="sxs-lookup"><span data-stu-id="34497-115">Top energy consumers</span></span>

<span data-ttu-id="34497-116">Im Bereich **Top energy consumers** finden Sie die Apps in Ihrer Umgebung, die die meiste Energie in mgWatt-Stunden (mWh) verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="34497-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="34497-117">Die angezeigten Apps werden pro bestimmtem Gerät angezeigt, das Sie im Abschnitt **"Vorhergesagte Akkulaufzeit"** links auswählen.</span><span class="sxs-lookup"><span data-stu-id="34497-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="34497-118">Wenn Sie z. B. den Verbrauch pro App für Microsoft Surface Book 2-Geräte sehen möchten, wählen Sie diese Zeile im Bereich Akkulaufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="34497-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="34497-119">Wenn Sie kein Modell auswählen, werden die angezeigten App-Nutzungsdaten für alle Apps verwendet, für die wir Daten gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="34497-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="34497-120">Für jede App zeigen farbige Segmente die Verteilung des Energieverbrauchs der App unter den folgenden Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="34497-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="34497-121">CPU</span><span class="sxs-lookup"><span data-stu-id="34497-121">CPU</span></span>
- <span data-ttu-id="34497-122">Anzeigen</span><span class="sxs-lookup"><span data-stu-id="34497-122">Display</span></span>
- <span data-ttu-id="34497-123">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="34497-123">Network</span></span>
- <span data-ttu-id="34497-124">Andere</span><span class="sxs-lookup"><span data-stu-id="34497-124">Other</span></span>

<span data-ttu-id="34497-125">"Other" könnte den Energieverbrauch aus einer Vielzahl von Quellen umfassen, z. B. Datenträgeraktivität, mobile Breitbandnutzung und Energie, die durch internen Widerstand verloren geht.</span><span class="sxs-lookup"><span data-stu-id="34497-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="34497-126">Sie können diese Ansicht filtern, um nur Vordergrund-Apps, Hintergrund-Apps oder beides anzuzeigen, indem Sie das Menü oben rechts verwenden.</span><span class="sxs-lookup"><span data-stu-id="34497-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="34497-127">Vordergrund-Apps sind Apps, die in den letzten 28 Tagen eine Benutzerinteraktion hatten, z. B. das Auswählen einer Maus.</span><span class="sxs-lookup"><span data-stu-id="34497-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="34497-128">Einblicke</span><span class="sxs-lookup"><span data-stu-id="34497-128">Insights</span></span>

<span data-ttu-id="34497-129">Der **Bereich Insights** zeigt die drei Energieverbraucher in den Kategorien CPU und Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="34497-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="34497-130">Diese Elemente verbrauchen im Vergleich zu allen Microsoft Managed Desktop-Bereitstellungen überdurchschnittlich viel Energie.</span><span class="sxs-lookup"><span data-stu-id="34497-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="34497-131">Die Anzeigeressource wird nicht angezeigt, da sie stark von der Gerätenutzungszeit und den Einstellungen für die Bildschirmhelligkeit abhängt.</span><span class="sxs-lookup"><span data-stu-id="34497-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="34497-132">Wählen Sie die Einträge in der **Spalte Details** aus, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34497-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="34497-133">Akkuoptimierung</span><span class="sxs-lookup"><span data-stu-id="34497-133">Battery optimization</span></span>

<span data-ttu-id="34497-134">Windows 10 bietet zahlreiche [Geräteeinstellungen,](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) um den Energieverbrauch zu verbessern und die Akkulaufzeit Ihrer Microsoft Managed Desktop-Geräte zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="34497-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="34497-135">Einige dieser Einstellungen können andere Windows-Funktionen verringern, sodass Sie auch andere Faktoren berücksichtigen müssen, z. B. die Rolle des Geräts in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="34497-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="34497-136">Die Windows-Unterstützung verwaltet eine Liste dieser [Tipps zum Speichern von Akkus.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="34497-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="34497-137">Benutzer können einige Einstellungen selbst anpassen, ohne dass administratorerweiterungen oder -support benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="34497-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="34497-138">Andere Einstellungen erfordern Unterstützung durch den IT-Administrator Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="34497-138">Other settings require support from your organization's IT administrator.</span></span>
