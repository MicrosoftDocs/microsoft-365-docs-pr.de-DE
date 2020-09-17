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
# <a name="reliability-insights"></a><span data-ttu-id="f7308-103">Zuverlässigkeitseinblicke</span><span class="sxs-lookup"><span data-stu-id="f7308-103">Reliability insights</span></span>

<span data-ttu-id="f7308-104">In dieser Ansicht erhalten Sie eine Zusammenfassung der Integrität Ihrer verwalteten Geräte.</span><span class="sxs-lookup"><span data-stu-id="f7308-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="f7308-105">Um Zuverlässigkeitsdaten anzuzeigen, wählen Sie die Registerkarte **Zuverlässigkeit** aus.</span><span class="sxs-lookup"><span data-stu-id="f7308-105">To view reliability data, select the **Reliability** tab.</span></span>


![Zuverlässigkeits Bereich: Zuverlässigkeit über Geräte in der oberen linken Ecke, Zuverlässigkeit im Zeitdiagramm oben rechts, Tabelle oben auf der unteren Seite.](../../media/insights_reliability.png)

<span data-ttu-id="f7308-108">Der Abschnitt " **Zuverlässigkeit für alle Geräte** " bietet eine Schnellübersicht über die Integrität Ihrer Bereitstellung in den letzten 14 Tagen, indem er den Prozentsatz der als "fehlerfrei" erachteten Geräte und die durchschnittliche Zeit seit dem letzten gemeldeten Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="f7308-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="f7308-109">Der Graph " **Zuverlässigkeit über Zeit** " auf der rechten Seite gibt die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der beobachteten kritischen Fehler im Laufe der Zeit an.</span><span class="sxs-lookup"><span data-stu-id="f7308-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="f7308-110">Im Abschnitt **häufigsten Probleme** werden bestimmte erkannte Probleme erläutert, die sich auf mindestens 5% der verwalteten Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="f7308-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="f7308-111">Zu den gemeldeten Details gehören:</span><span class="sxs-lookup"><span data-stu-id="f7308-111">Reported details include:</span></span>

- <span data-ttu-id="f7308-112">Der Typ des Problems</span><span class="sxs-lookup"><span data-stu-id="f7308-112">The type of issue</span></span>
    - <span data-ttu-id="f7308-113">Anwendungsabstürze, bei denen eine APP nicht mehr funktioniert oder unerwartet angehalten wird</span><span class="sxs-lookup"><span data-stu-id="f7308-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="f7308-114">Anwendung hängt an, wobei eine Anwendung nicht mehr auf Eingabe reagiert</span><span class="sxs-lookup"><span data-stu-id="f7308-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="f7308-115">Kritische Fehler, die auftreten, wenn ein Problem bei Windows aufgetreten ist, von dem keine Wiederherstellung möglich ist</span><span class="sxs-lookup"><span data-stu-id="f7308-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="f7308-116">Die Anzahl der Geräte, die von dem gleichen Problem betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="f7308-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="f7308-117">Der Prozentsatz der verwalteten Geräte, die die Zahl darstellt</span><span class="sxs-lookup"><span data-stu-id="f7308-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="f7308-118">Die Gesamtanzahl der Vorkommen des jeweiligen Problems.</span><span class="sxs-lookup"><span data-stu-id="f7308-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="f7308-119">Die Softwarekomponente, die als Ursache des Problems angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="f7308-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="f7308-120">Die Kategorie des erkannten Problems:</span><span class="sxs-lookup"><span data-stu-id="f7308-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="f7308-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="f7308-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="f7308-122">Unbekannt (nicht-Microsoft-Komponenten)</span><span class="sxs-lookup"><span data-stu-id="f7308-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="f7308-123">Treiber (Audio, Grafik oder andere Treiber)</span><span class="sxs-lookup"><span data-stu-id="f7308-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="f7308-124">Produktivität (slack, G-Suites, Microsoft Office und seine Add-ons oder Erweiterungen, Teams)</span><span class="sxs-lookup"><span data-stu-id="f7308-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="f7308-125">Medien (Bild-, Musik-oder Video-apps</span><span class="sxs-lookup"><span data-stu-id="f7308-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="f7308-126">Sicherheit (Windows-Sicherheitskomponenten)</span><span class="sxs-lookup"><span data-stu-id="f7308-126">Security (Windows security components)</span></span>
- <span data-ttu-id="f7308-127">Der aktuelle Status als von Microsoft verwaltete Desktop Vorgänge untersucht und korrigiert das Problem</span><span class="sxs-lookup"><span data-stu-id="f7308-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

