---
title: Akku-Einblicke
description: Ein Bericht, der Daten über die prognostizierte Akkulaufzeit und die wichtigsten Energieverbraucher zeigt
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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739792"
---
# <a name="battery-insights"></a><span data-ttu-id="b845b-104">Akku-Einblicke</span><span class="sxs-lookup"><span data-stu-id="b845b-104">Battery insights</span></span>
<span data-ttu-id="b845b-105">Diese Ansicht bietet Energie-, Akku- und App-Nutzungsmetriken für Ihre Microsoft Managed Desktop Geräte.</span><span class="sxs-lookup"><span data-stu-id="b845b-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b845b-106">Für diese Zwecke wird eine App als "verwendet" betrachtet, wenn sie ausgeführt wird und im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="b845b-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="b845b-107">Um Nutzungsdaten anzuzeigen, wählen Sie die Registerkarte **"Akku"** aus.</span><span class="sxs-lookup"><span data-stu-id="b845b-107">To view usage data, select the **Battery** tab.</span></span>

![Akkubereich: Pro Gerätemodell in oberer linker Ecke, oberer Energieverbraucher (nach App) oben rechts, Insights-Tabelle unten.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="b845b-110">Prognostizierte Akkulaufzeit</span><span class="sxs-lookup"><span data-stu-id="b845b-110">Predicted battery life</span></span>

<span data-ttu-id="b845b-111">Im Bereich **"Prognostizierte Akkulaufzeit"** stellen wir Nach Gerätemodell geordnete Vorhersagen für die erwartete Akkulaufzeit für Ihre Geräte bereit.</span><span class="sxs-lookup"><span data-stu-id="b845b-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="b845b-112">Diese Daten werden aus dem Sampling von Energieverbrauch, Nutzungszeit und Akkukapazität aus einer zufälligen <em>Auswahl</em> der Geräte in Ihrer Microsoft Managed Desktop-Bereitstellung abgeleitet, die auch Berichtsdaten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b845b-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="b845b-113">Die Tabelle enthält die prognostizierte Akkulaufzeit (in Stunden), die durchschnittliche Akkulaufzeit für dieselben Modelle in anderen Microsoft Managed Desktop Bereitstellungen und die Anzahl der Geräte, die diese Daten in Ihrer Umgebung melden.</span><span class="sxs-lookup"><span data-stu-id="b845b-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="b845b-114">Sortieren Sie die Daten, indem Sie die Spaltenüberschriften auswählen.</span><span class="sxs-lookup"><span data-stu-id="b845b-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="b845b-115">Die wichtigsten Energieverbraucher</span><span class="sxs-lookup"><span data-stu-id="b845b-115">Top energy consumers</span></span>

<span data-ttu-id="b845b-116">Im Bereich der **wichtigsten Energieverbraucher** finden Sie die Apps in Ihrer Umgebung, die den größten Energieverbrauch in Millattstunden (mWh) verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="b845b-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="b845b-117">Die angezeigten Apps beziehen sich auf ein bestimmtes Gerät, das Sie im Abschnitt **"Prognostizierte Akkulaufzeit"** auf der linken Seite auswählen.</span><span class="sxs-lookup"><span data-stu-id="b845b-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="b845b-118">Um beispielsweise den Pro-App-Verbrauch für Ihre Microsoft Surface Book 2-Geräte anzuzeigen, wählen Sie diese Zeile im Akkulaufzeitbereich aus.</span><span class="sxs-lookup"><span data-stu-id="b845b-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="b845b-119">Wenn Sie kein Modell auswählen, gelten die angezeigten App-Nutzungsdaten für alle Apps, für die wir Daten gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="b845b-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="b845b-120">Für jede App zeigen farbige Segmente die Verteilung des Energieverbrauchs der App in diesen Kategorien an:</span><span class="sxs-lookup"><span data-stu-id="b845b-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="b845b-121">CPU</span><span class="sxs-lookup"><span data-stu-id="b845b-121">CPU</span></span>
- <span data-ttu-id="b845b-122">Anzeigen</span><span class="sxs-lookup"><span data-stu-id="b845b-122">Display</span></span>
- <span data-ttu-id="b845b-123">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b845b-123">Network</span></span>
- <span data-ttu-id="b845b-124">Andere</span><span class="sxs-lookup"><span data-stu-id="b845b-124">Other</span></span>

<span data-ttu-id="b845b-125">"Andere" könnten den Energieverbrauch einer Vielzahl von Quellen umfassen, z. B. Datenträgeraktivität, mobile Breitbandnutzung und Energie, die durch internen Widerstand verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="b845b-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="b845b-126">Sie können diese Ansicht so filtern, dass nur Vordergrund-Apps, Hintergrund-Apps oder beides angezeigt werden, indem Sie das Menü oben rechts verwenden.</span><span class="sxs-lookup"><span data-stu-id="b845b-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="b845b-127">Vordergrund-Apps sind Apps, die in den letzten 28 Tagen eine Benutzerinteraktion durchgeführt haben, z. B. die Auswahl einer Aktion mit der Maus.</span><span class="sxs-lookup"><span data-stu-id="b845b-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="b845b-128">Einblicke</span><span class="sxs-lookup"><span data-stu-id="b845b-128">Insights</span></span>

<span data-ttu-id="b845b-129">Der Bereich **"Insights"** zeigt die drei wichtigsten Energieverbraucher in den Kategorien CPU und Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="b845b-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="b845b-130">Diese Elemente verbrauchen im Vergleich zu allen Microsoft Managed Desktop Bereitstellungen eine überdurchschnittliche Energie.</span><span class="sxs-lookup"><span data-stu-id="b845b-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="b845b-131">Die Anzeigeressource wird nicht angezeigt, da sie stark von der Gerätenutzungszeit und den Einstellungen für die Bildschirmhelligkeit abhängt.</span><span class="sxs-lookup"><span data-stu-id="b845b-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="b845b-132">Wählen Sie die Einträge in der Spalte **"Details"** aus, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b845b-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="b845b-133">Optimierung des Akkus</span><span class="sxs-lookup"><span data-stu-id="b845b-133">Battery optimization</span></span>

<span data-ttu-id="b845b-134">Windows 10 bietet zahlreiche [Geräteeinstellungen,](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) um den Stromverbrauch zu verbessern und die Akkulaufzeit Ihrer Microsoft Managed Desktop Geräte zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b845b-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b845b-135">Einige dieser Einstellungen können andere Windows Funktionen verringern. Daher müssen Sie auch andere Faktoren wie die Rolle des Geräts in Ihrer Organisation berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b845b-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="b845b-136">Windows Unterstützung verwaltet eine Liste dieser [Tipps zum Stromsparen.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="b845b-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="b845b-137">Benutzer können einige Einstellungen selbst anpassen, ohne dass administratoreigene Rechte oder Unterstützung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b845b-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="b845b-138">Andere Einstellungen erfordern Unterstützung durch den IT-Administrator Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b845b-138">Other settings require support from your organization's IT administrator.</span></span>
