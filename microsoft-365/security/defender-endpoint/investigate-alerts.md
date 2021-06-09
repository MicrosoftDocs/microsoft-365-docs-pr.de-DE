---
title: Untersuchen von Microsoft Defender für Endpunkt-Warnungen
description: Verwenden Sie die Untersuchungsoptionen, um Details zu Warnungen zu erhalten, die Sich auf Ihr Netzwerk auswirken, was sie bedeuten und wie Sie diese beheben können.
keywords: untersuchen, Untersuchung, Geräte, Gerät, Warnungswarteschlange, Dashboard, IP-Adresse, Datei, übermitteln, Übermittlungen, umfassende Analyse, Zeitachse, Suche, Domäne, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841090"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="eaa01-104">Untersuchen von Warnungen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eaa01-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eaa01-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eaa01-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaa01-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eaa01-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaa01-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaa01-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="eaa01-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="eaa01-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eaa01-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eaa01-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="eaa01-110">Untersuchen Sie Warnungen, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten und wie Sie diese beheben können.</span><span class="sxs-lookup"><span data-stu-id="eaa01-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="eaa01-111">Wählen Sie eine Warnung aus der Warnungswarteschlange aus, um zur Warnungsseite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="eaa01-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="eaa01-112">Diese Ansicht enthält den Warnungstitel, die betroffenen Ressourcen, den Detailseitenbereich und den Warnungsartikel.</span><span class="sxs-lookup"><span data-stu-id="eaa01-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="eaa01-113">Beginnen Sie ihre Untersuchung auf der Warnungsseite, indem Sie die betroffenen Ressourcen oder entitäten unter der Warnungs-Story-Strukturansicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="eaa01-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="eaa01-114">Der Detailbereich wird automatisch mit weiteren Informationen zu den ausgewählten Elementen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="eaa01-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="eaa01-115">Um zu sehen, welche Art von Informationen Sie hier anzeigen können, lesen Sie ["Warnungen überprüfen" in Microsoft Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="eaa01-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="eaa01-116">Untersuchen der Verwendung des Warnungsartikels</span><span class="sxs-lookup"><span data-stu-id="eaa01-116">Investigate using the alert story</span></span>

<span data-ttu-id="eaa01-117">Der Warnungsartikel beschreibt, warum die Warnung ausgelöst wurde, verwandte Ereignisse, die vor und nach der Warnung aufgetreten sind, sowie andere verwandte Entitäten.</span><span class="sxs-lookup"><span data-stu-id="eaa01-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="eaa01-118">Entitäten sind klickbar, und jede Entität, die keine Warnung ist, kann mithilfe des Erweiterungssymbols auf der rechten Seite der Karte dieser Entität erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="eaa01-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="eaa01-119">Die entität im Fokus wird durch einen blauen Streifen auf der linken Seite der Karte der Entität angezeigt, wobei die Warnung im Titel zuerst im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="eaa01-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="eaa01-120">Erweitern Sie Entitäten, um Details auf einen Blick anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eaa01-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="eaa01-121">Wenn Sie eine Entität auswählen, wird der Kontext des Detailbereichs auf diese Entität umgestellt, und Sie können weitere Informationen überprüfen und diese Entität verwalten.</span><span class="sxs-lookup"><span data-stu-id="eaa01-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="eaa01-122">Wenn Sie *...* rechts neben der Entitätskarte auswählen, werden alle für diese Entität verfügbaren Aktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eaa01-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="eaa01-123">Diese Aktionen werden im Detailbereich angezeigt, wenn diese Entität im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="eaa01-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="eaa01-124">Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, wobei zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur vor oder nach der ausgewählten Warnung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eaa01-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Ein Beispiel für eine Warnung mit einer Warnung im Fokus und einigen erweiterten Karten](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="eaa01-126">Ergreifen von Maßnahmen aus dem Detailbereich</span><span class="sxs-lookup"><span data-stu-id="eaa01-126">Take action from the details pane</span></span>

<span data-ttu-id="eaa01-127">Nachdem Sie eine interessante Entität ausgewählt haben, wird der Detailbereich so geändert, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn diese verfügbar sind, und Steuerelemente zum Ergreifen von **Maßnahmen** für diese Entität direkt über die Warnungsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eaa01-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="eaa01-128">Sobald Sie die Untersuchung abgeschlossen haben, kehren Sie zu der Warnung zurück, mit der Sie begonnen haben, markieren Sie den Status der Warnung als **aufgelöst,** und klassifizieren Sie sie als **"False"** oder **"True".**</span><span class="sxs-lookup"><span data-stu-id="eaa01-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="eaa01-129">Das Klassifizieren von Warnungen hilft bei der Optimierung dieser Funktion, um mehr echte und weniger falsche Warnungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eaa01-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="eaa01-130">Wenn Sie sie als echte Warnung klassifizieren, können Sie auch eine Bestimmung auswählen, wie in der abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eaa01-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Ein Codeausschnitt des Detailbereichs mit einer aufgelösten Warnung und erweiterter Dropdownliste zur Ermittlung](images/alert-details-resolved-true.png)

<span data-ttu-id="eaa01-132">Wenn bei einer Branchenanwendung eine falsche Warnung auftritt, erstellen Sie eine Unterdrückungsregel, um diese Art von Warnung in Zukunft zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="eaa01-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![Aktionen und Klassifizierung im Detailbereich mit hervorgehobener Unterdrückungsregel](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="eaa01-134">Wenn Sie Probleme haben, die oben nicht beschrieben sind, verwenden Sie die 🙂 Schaltfläche, um Feedback zu geben oder ein Supportticket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eaa01-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="eaa01-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="eaa01-135">Related topics</span></span>
- [<span data-ttu-id="eaa01-136">Anzeigen und Organisieren der Microsoft Defender für Endpunkt-Warnungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="eaa01-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="eaa01-137">Verwalten von Microsoft Defender für Endpunkt-Warnungen</span><span class="sxs-lookup"><span data-stu-id="eaa01-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="eaa01-138">Untersuchen einer Datei, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="eaa01-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="eaa01-139">Untersuchen von Geräten in der Liste "Defender für Endpunktgeräte"</span><span class="sxs-lookup"><span data-stu-id="eaa01-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="eaa01-140">Untersuchen einer IP-Adresse, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="eaa01-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="eaa01-141">Untersuchen einer Domäne, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="eaa01-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="eaa01-142">Untersuchen eines Benutzerkontos in Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eaa01-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


