---
title: Verwenden von Vertraulichkeitsbeschriftungen zum Priorisieren von Vorfallantworten
description: Informationen zum Verwenden von Vertraulichkeitsbezeichnungen zum Priorisieren und Untersuchen von Vorfällen
keywords: information, protection, data, loss, prevention,labels, dlp, incident, investigate, investigation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186125"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="31ff9-104">Verwenden von Vertraulichkeitsbeschriftungen zum Priorisieren von Vorfallantworten</span><span class="sxs-lookup"><span data-stu-id="31ff9-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31ff9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="31ff9-105">**Applies to:**</span></span>
- [<span data-ttu-id="31ff9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="31ff9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="31ff9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31ff9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="31ff9-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="31ff9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="31ff9-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="31ff9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="31ff9-110">Ein typischer erweiterter Lebenszyklus für dauerhafte Bedrohungen umfasst die Daten-Exfiltration.</span><span class="sxs-lookup"><span data-stu-id="31ff9-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="31ff9-111">Bei einem Sicherheitsvorfall ist es wichtig, dass Sie Untersuchungen priorisieren können, bei denen vertrauliche Dateien gefährdet sind, damit Unternehmensdaten und -informationen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="31ff9-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="31ff9-112">Defender for Endpoint erleichtert die Priorisierung von Sicherheitsvorfällen durch die Verwendung von Vertraulichkeitsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="31ff9-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="31ff9-113">Vertraulichkeitsbezeichnungen identifizieren schnell Vorfälle, die Geräte mit vertraulichen Informationen wie z. B. vertraulichen Informationen betreffen können.</span><span class="sxs-lookup"><span data-stu-id="31ff9-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="31ff9-114">Untersuchen von Vorfällen mit vertraulichen Daten</span><span class="sxs-lookup"><span data-stu-id="31ff9-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="31ff9-115">Erfahren Sie, wie Sie Datensensitivitätsbezeichnungen verwenden, um die Untersuchung von Vorfällen zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="31ff9-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="31ff9-116">Bezeichnungen werden für Windows 10, Version 1809 oder höher, erkannt.</span><span class="sxs-lookup"><span data-stu-id="31ff9-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="31ff9-117">Wählen Microsoft Defender Security Center unter **Incidents aus.**</span><span class="sxs-lookup"><span data-stu-id="31ff9-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="31ff9-118">Scrollen Sie nach rechts, um die Spalte **Datensensitivität zu** sehen.</span><span class="sxs-lookup"><span data-stu-id="31ff9-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="31ff9-119">Diese Spalte spiegelt Vertraulichkeitsbezeichnungen wider, die auf Geräten im Zusammenhang mit den Vorfällen beobachtet wurden und einen Hinweis darauf geben, ob vertrauliche Dateien von dem Vorfall betroffen sein können.</span><span class="sxs-lookup"><span data-stu-id="31ff9-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Abbildung der Datensensitivitätsspalte](images/data-sensitivity-column.png)

    <span data-ttu-id="31ff9-121">Sie können auch nach Datensensitivität **filtern**</span><span class="sxs-lookup"><span data-stu-id="31ff9-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Abbildung des Datensensitivitätsfilters](images/data-sensitivity-filter.png)

3. <span data-ttu-id="31ff9-123">Öffnen Sie die Vorfallseite, um weitere Untersuchungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="31ff9-123">Open the incident page to further investigate.</span></span>

    ![Abbildung der Details der Vorfallseite](images/incident-page.png)

4. <span data-ttu-id="31ff9-125">Wählen Sie die **Registerkarte Geräte** aus, um Geräte zu identifizieren, die Dateien mit Vertraulichkeitsbezeichnungen speichern.</span><span class="sxs-lookup"><span data-stu-id="31ff9-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Abbildung der Registerkarte "Gerät"](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="31ff9-127">Wählen Sie die Geräte aus, auf denen vertrauliche Daten gespeichert werden, und durchsuchen Sie die Zeitachse, um zu ermitteln, welche Dateien betroffen sein können, und ergreifen Sie dann geeignete Maßnahmen, um sicherzustellen, dass Daten geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="31ff9-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="31ff9-128">Sie können die auf der Gerätezeitachse angezeigten Ereignisse einen, indem Sie nach Datenempfindlichkeitsbezeichnungen suchen.</span><span class="sxs-lookup"><span data-stu-id="31ff9-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="31ff9-129">Dadurch werden nur Ereignisse angezeigt, die Dateien zugeordnet sind, deren Bezeichnungsname angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="31ff9-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Abbildung der Gerätezeitachse mit einengten Suchergebnissen basierend auf der Bezeichnung](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="31ff9-131">Diese Datenpunkte werden auch über die "DeviceFileEvents" in der erweiterten Suche verfügbar gemacht, sodass erweiterte Abfragen und die Zeitplanungserkennung Vertraulichkeitsbezeichnungen und Dateischutzstatus berücksichtigen können.</span><span class="sxs-lookup"><span data-stu-id="31ff9-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
