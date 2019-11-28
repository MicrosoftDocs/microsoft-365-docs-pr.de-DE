---
title: Zuverlässigkeitseinblicke
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634032"
---
# <a name="reliability-insights"></a><span data-ttu-id="ba459-103">Zuverlässigkeitseinblicke</span><span class="sxs-lookup"><span data-stu-id="ba459-103">Reliability insights</span></span>

<span data-ttu-id="ba459-104">In dieser Ansicht erhalten Sie eine Zusammenfassung der Integrität Ihrer verwalteten Geräte.</span><span class="sxs-lookup"><span data-stu-id="ba459-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="ba459-105">Um Zuverlässigkeitsdaten anzuzeigen, wählen Sie die Registerkarte **Zuverlässigkeit** aus.</span><span class="sxs-lookup"><span data-stu-id="ba459-105">To view reliability data, select the **Reliability** tab.</span></span>


![Zuverlässigkeits Bereich](images/insights_reliability.png)

<span data-ttu-id="ba459-107">Der Abschnitt " **Zuverlässigkeit für alle Geräte** " bietet eine Schnellübersicht über die Integrität Ihrer Bereitstellung in den letzten 14 Tagen, indem er den Prozentsatz der als "fehlerfrei" erachteten Geräte und die durchschnittliche Zeit seit dem letzten gemeldeten Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="ba459-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="ba459-108">Der Graph " **Zuverlässigkeit über Zeit** " auf der rechten Seite gibt die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der beobachteten kritischen Fehler im Laufe der Zeit an.</span><span class="sxs-lookup"><span data-stu-id="ba459-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="ba459-109">Im Abschnitt **häufigsten Probleme** werden bestimmte erkannte Probleme erläutert, die sich auf mindestens 5% der verwalteten Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="ba459-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="ba459-110">Zu den gemeldeten Details gehören:</span><span class="sxs-lookup"><span data-stu-id="ba459-110">Reported details include:</span></span>

- <span data-ttu-id="ba459-111">Der Typ des Problems</span><span class="sxs-lookup"><span data-stu-id="ba459-111">The type of issue</span></span>
    - <span data-ttu-id="ba459-112">Anwendungsabstürze, bei denen eine APP nicht mehr funktioniert oder unerwartet angehalten wird</span><span class="sxs-lookup"><span data-stu-id="ba459-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="ba459-113">Anwendung hängt an, wobei eine Anwendung nicht mehr auf Eingabe reagiert</span><span class="sxs-lookup"><span data-stu-id="ba459-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="ba459-114">Kritische Fehler, die auftreten, wenn ein Problem bei Windows aufgetreten ist, von dem keine Wiederherstellung möglich ist</span><span class="sxs-lookup"><span data-stu-id="ba459-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="ba459-115">Die Anzahl der Geräte, die von dem gleichen Problem betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="ba459-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="ba459-116">Der Prozentsatz der verwalteten Geräte, die die Zahl darstellt</span><span class="sxs-lookup"><span data-stu-id="ba459-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="ba459-117">Die Gesamtanzahl der Vorkommen des jeweiligen Problems.</span><span class="sxs-lookup"><span data-stu-id="ba459-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="ba459-118">Die Softwarekomponente, die als Ursache des Problems angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="ba459-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="ba459-119">Die Kategorie des erkannten Problems:</span><span class="sxs-lookup"><span data-stu-id="ba459-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="ba459-120">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="ba459-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="ba459-121">Unbekannt (nicht-Microsoft-Komponenten)</span><span class="sxs-lookup"><span data-stu-id="ba459-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="ba459-122">Treiber (Audio, Grafik oder andere Treiber)</span><span class="sxs-lookup"><span data-stu-id="ba459-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="ba459-123">Produktivität (slack, G-Suites, Microsoft Office und seine Add-ons oder Erweiterungen, Teams)</span><span class="sxs-lookup"><span data-stu-id="ba459-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="ba459-124">Medien (Bild-, Musik-oder Video-apps</span><span class="sxs-lookup"><span data-stu-id="ba459-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="ba459-125">Sicherheit (Windows-Sicherheitskomponenten)</span><span class="sxs-lookup"><span data-stu-id="ba459-125">Security (Windows security components)</span></span>
- <span data-ttu-id="ba459-126">Der aktuelle Status als von Microsoft verwaltete Desktop Vorgänge untersucht und korrigiert das Problem</span><span class="sxs-lookup"><span data-stu-id="ba459-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

