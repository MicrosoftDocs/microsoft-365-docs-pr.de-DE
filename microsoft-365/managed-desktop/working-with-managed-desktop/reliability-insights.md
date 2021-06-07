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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739783"
---
# <a name="reliability-insights"></a><span data-ttu-id="5c76c-103">Zuverlässigkeitseinblicke</span><span class="sxs-lookup"><span data-stu-id="5c76c-103">Reliability insights</span></span>

<span data-ttu-id="5c76c-104">In dieser Ansicht erhalten Sie eine Integritätszusammenfassung ihrer verwalteten Geräte.</span><span class="sxs-lookup"><span data-stu-id="5c76c-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="5c76c-105">Wählen Sie zum Anzeigen von Zuverlässigkeitsdaten die Registerkarte **"Zuverlässigkeit"** aus.</span><span class="sxs-lookup"><span data-stu-id="5c76c-105">To view reliability data, select the **Reliability** tab.</span></span>


![Zuverlässigkeitsbereich: Zuverlässigkeit auf allen Geräten oben links, Zuverlässigkeitsdiagramm im Zeitverlauf oben rechts, Tabelle mit den oberen Problemen unten.](../../media/insights_reliability.png)

<span data-ttu-id="5c76c-108">Der Abschnitt **"Zuverlässigkeit geräteübergreifend"** bietet eine schnelle Integritätszusammenfassung ihrer Bereitstellung in den letzten 14 Tagen, indem der Prozentsatz der als "fehlerfrei" eingestuften Geräte und die seit dem letzten gemeldeten Fehler beobachtete Mittlere Zeit gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="5c76c-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="5c76c-109">Das Diagramm **"Zuverlässigkeit im Zeitverlauf"** auf der rechten Seite meldet die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der beobachteten kritischen Fehler im Laufe der Zeit.</span><span class="sxs-lookup"><span data-stu-id="5c76c-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="5c76c-110">Im Abschnitt **"Häufigste Probleme"** werden bestimmte erkannte Probleme beschrieben, die sich auf mindestens 5 % Ihrer verwalteten Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="5c76c-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="5c76c-111">Zu den gemeldeten Details gehören:</span><span class="sxs-lookup"><span data-stu-id="5c76c-111">Reported details include:</span></span>

- <span data-ttu-id="5c76c-112">Der Typ des Problems</span><span class="sxs-lookup"><span data-stu-id="5c76c-112">The type of issue</span></span>
    - <span data-ttu-id="5c76c-113">Anwendungsabstürze, bei denen eine App nicht mehr funktioniert oder unerwartet beendet wird</span><span class="sxs-lookup"><span data-stu-id="5c76c-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="5c76c-114">Anwendung hängt an, wo eine Anwendung nicht mehr auf Eingaben reagiert</span><span class="sxs-lookup"><span data-stu-id="5c76c-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="5c76c-115">Kritische Fehler, die auftreten, wenn Windows ein Problem aufgetreten ist, von dem es nicht wiederhergestellt werden kann</span><span class="sxs-lookup"><span data-stu-id="5c76c-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="5c76c-116">Die Anzahl der Geräte, die von demselben Problem betroffen sind</span><span class="sxs-lookup"><span data-stu-id="5c76c-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="5c76c-117">Der Prozentsatz der verwalteten Geräte, die diese Anzahl darstellt</span><span class="sxs-lookup"><span data-stu-id="5c76c-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="5c76c-118">Die Gesamtanzahl der Vorkommen des spezifischen Problems</span><span class="sxs-lookup"><span data-stu-id="5c76c-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="5c76c-119">Die Softwarekomponente, die die Ursache des Problems zu sein scheint</span><span class="sxs-lookup"><span data-stu-id="5c76c-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="5c76c-120">Die Kategorie des erkannten Problems:</span><span class="sxs-lookup"><span data-stu-id="5c76c-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="5c76c-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="5c76c-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="5c76c-122">Unbekannt (Nicht-Microsoft-Komponenten)</span><span class="sxs-lookup"><span data-stu-id="5c76c-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="5c76c-123">Treiber (Audio, Grafiken oder andere Treiber)</span><span class="sxs-lookup"><span data-stu-id="5c76c-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="5c76c-124">Produktivität (Slack, G-Suites, Microsoft Office und seine Add-Ons oder Erweiterungen Teams)</span><span class="sxs-lookup"><span data-stu-id="5c76c-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="5c76c-125">Medien (Bild-, Musik- oder Video-Apps</span><span class="sxs-lookup"><span data-stu-id="5c76c-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="5c76c-126">Sicherheitskomponenten (Windows)</span><span class="sxs-lookup"><span data-stu-id="5c76c-126">Security (Windows security components)</span></span>
- <span data-ttu-id="5c76c-127">Der aktuelle Status als Microsoft Managed Desktop Vorgänge untersucht und behebt das Problem.</span><span class="sxs-lookup"><span data-stu-id="5c76c-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

