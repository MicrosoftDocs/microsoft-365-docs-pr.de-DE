---
title: Zuverlässigkeitseinblicke
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950342"
---
# <a name="reliability-insights"></a><span data-ttu-id="66497-103">Zuverlässigkeitseinblicke</span><span class="sxs-lookup"><span data-stu-id="66497-103">Reliability insights</span></span>

<span data-ttu-id="66497-104">Diese Ansicht enthält eine Integritätszusammenfassung Ihrer verwalteten Geräte.</span><span class="sxs-lookup"><span data-stu-id="66497-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="66497-105">Wählen Sie zum Anzeigen von Zuverlässigkeitsdaten die Registerkarte **Zuverlässigkeit** aus.</span><span class="sxs-lookup"><span data-stu-id="66497-105">To view reliability data, select the **Reliability** tab.</span></span>


![Zuverlässigkeitsbereich: Zuverlässigkeit auf allen Geräten in der oberen linken Ecke, Diagramm "Zuverlässigkeit über Zeit" in der oberen rechten Ecke, Tabelle mit den obersten Problemen unten.](../../media/insights_reliability.png)

<span data-ttu-id="66497-108">Der  Abschnitt Zuverlässigkeit auf allen Geräten bietet eine kurze Integritätszusammenfassung Ihrer Bereitstellung in den letzten 14 Tagen, indem der Prozentsatz der Geräte gemeldet wird, die als "fehlerfrei" betrachtet werden, und den Mittelwert seit dem letzten gemeldeten Fehler.</span><span class="sxs-lookup"><span data-stu-id="66497-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="66497-109">Das **Diagramm Zuverlässigkeit über die** Zeit auf der rechten Seite gibt die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der im Laufe der Zeit beobachteten kritischen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="66497-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="66497-110">Im **Abschnitt Top issues** werden bestimmte erkannte Probleme beschrieben, die mindestens 5 % ihrer verwalteten Geräte betreffen.</span><span class="sxs-lookup"><span data-stu-id="66497-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="66497-111">Zu den gemeldeten Details gehören:</span><span class="sxs-lookup"><span data-stu-id="66497-111">Reported details include:</span></span>

- <span data-ttu-id="66497-112">Der Typ des Problems</span><span class="sxs-lookup"><span data-stu-id="66497-112">The type of issue</span></span>
    - <span data-ttu-id="66497-113">Anwendungsabstürze, bei denen eine App nicht mehr funktioniert oder unerwartet beendet wird</span><span class="sxs-lookup"><span data-stu-id="66497-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="66497-114">Anwendung hängt ab, wobei eine Anwendung nicht mehr auf Eingaben reagiert</span><span class="sxs-lookup"><span data-stu-id="66497-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="66497-115">Kritische Fehler, die auftreten, wenn windows ein Problem festgestellt hat, von dem es nicht wiederherstellen kann</span><span class="sxs-lookup"><span data-stu-id="66497-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="66497-116">Die Anzahl der geräte, die vom gleichen Problem betroffen sind</span><span class="sxs-lookup"><span data-stu-id="66497-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="66497-117">Der Prozentsatz der verwalteten Geräte, die zahl stellt</span><span class="sxs-lookup"><span data-stu-id="66497-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="66497-118">Die Gesamtanzahl der Vorkommen des spezifischen Problems</span><span class="sxs-lookup"><span data-stu-id="66497-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="66497-119">Die Softwarekomponente, die die Ursache des Problems zu sein scheint</span><span class="sxs-lookup"><span data-stu-id="66497-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="66497-120">Die Kategorie des erkannten Problems:</span><span class="sxs-lookup"><span data-stu-id="66497-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="66497-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="66497-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="66497-122">Unbekannt (Nicht-Microsoft-Komponenten)</span><span class="sxs-lookup"><span data-stu-id="66497-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="66497-123">Treiber (Audio, Grafik oder andere Treiber)</span><span class="sxs-lookup"><span data-stu-id="66497-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="66497-124">Produktivität (Slack, G-Suites, Microsoft Office und seine Add-Ons oder Erweiterungen, Teams)</span><span class="sxs-lookup"><span data-stu-id="66497-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="66497-125">Medien (Bild-, Musik- oder Video-Apps)</span><span class="sxs-lookup"><span data-stu-id="66497-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="66497-126">Sicherheit (Windows-Sicherheitskomponenten)</span><span class="sxs-lookup"><span data-stu-id="66497-126">Security (Windows security components)</span></span>
- <span data-ttu-id="66497-127">Der aktuelle Status als Microsoft Managed Desktop Operations untersucht und be beheben das Problem</span><span class="sxs-lookup"><span data-stu-id="66497-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

