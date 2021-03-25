---
title: Untersuchen von Microsoft Defender for Endpoint-Warnungen
description: Verwenden Sie die Untersuchungsoptionen, um Details zu Warnungen zu erhalten, die ihr Netzwerk betreffen, was sie bedeuten und wie Sie diese beheben können.
keywords: untersuchen, Untersuchen, Geräte, Gerät, Warnungswarteschlange, Dashboard, IP-Adresse, Datei, Übermitteln, Übermittlungen, Tiefe Analyse, Zeitachse, Suche, Domäne, URL, IP
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
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067696"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e2d42-104">Untersuchen von Warnungen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2d42-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2d42-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2d42-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2d42-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e2d42-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e2d42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2d42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e2d42-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e2d42-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2d42-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e2d42-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="e2d42-110">Untersuchen Sie Warnungen, die Sich auf Ihr Netzwerk ausdingen, verstehen Sie, was sie bedeuten, und wie Sie sie beheben können.</span><span class="sxs-lookup"><span data-stu-id="e2d42-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="e2d42-111">Wählen Sie eine Warnung aus der Benachrichtigungswarteschlange aus, um zur Warnungsseite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="e2d42-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="e2d42-112">Diese Ansicht enthält den Warnungstitel, die betroffenen Objekte, den Detailseitenbereich und den Warnungsstory.</span><span class="sxs-lookup"><span data-stu-id="e2d42-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="e2d42-113">Beginnen Sie auf der Warnungsseite mit der Untersuchung, indem Sie die betroffenen Objekte oder entitäten unter der Warnungsstorystrukturansicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="e2d42-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="e2d42-114">Der Detailbereich wird automatisch mit weiteren Informationen zu den ausgewählten Informationen auffüllt.</span><span class="sxs-lookup"><span data-stu-id="e2d42-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="e2d42-115">Informationen dazu, welche Art von Informationen Sie hier anzeigen können, finden Sie unter Überprüfen von Warnungen [in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span><span class="sxs-lookup"><span data-stu-id="e2d42-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="e2d42-116">Untersuchen der Verwendung des Warnungsstorys</span><span class="sxs-lookup"><span data-stu-id="e2d42-116">Investigate using the alert story</span></span>

<span data-ttu-id="e2d42-117">Der Warnungsstory enthält Details dazu, warum die Warnung ausgelöst wurde, verwandte Ereignisse, die vor und nach passiert sind, sowie andere verwandte Entitäten.</span><span class="sxs-lookup"><span data-stu-id="e2d42-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="e2d42-118">Entitäten können angeklickt werden, und jede Entität, die keine Warnung ist, kann mithilfe des Erweiterungssymbols auf der rechten Seite der Karte dieser Entität erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="e2d42-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="e2d42-119">Die entität im Fokus wird durch einen blauen Streifen auf der linken Seite der Karte dieser Entität angezeigt, und die Warnung im Titel ist zunächst im Fokus.</span><span class="sxs-lookup"><span data-stu-id="e2d42-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="e2d42-120">Erweitern Sie Entitäten, um Details auf einen Blick anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2d42-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="e2d42-121">Wenn Sie eine Entität auswählen, wird der Kontext des Detailbereichs zu dieser Entität umschalten, und Sie können weitere Informationen überprüfen und diese Entität verwalten.</span><span class="sxs-lookup"><span data-stu-id="e2d42-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="e2d42-122">Wenn *Sie ...* rechts neben der Entitätskarte auswählen, werden alle aktionen für diese Entität verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e2d42-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="e2d42-123">Dieselben Aktionen werden im Detailbereich angezeigt, wenn sich diese Entität im Fokus befindet.</span><span class="sxs-lookup"><span data-stu-id="e2d42-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="e2d42-124">Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, und zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur werden vor oder nach der ausgewählten Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2d42-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Ein Beispiel für einen Warnungsstory mit einer Warnung im Fokus und einigen erweiterten Karten](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="e2d42-126">Ergreifen von Aktionen aus dem Detailbereich</span><span class="sxs-lookup"><span data-stu-id="e2d42-126">Take action from the details pane</span></span>

<span data-ttu-id="e2d42-127">Nachdem Sie eine entität von Interesse ausgewählt haben, wird der Detailbereich geändert, um Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn diese verfügbar ist, anzuzeigen und Steuerelemente zum Ergreifen von Aktionen für diese Entität direkt auf der Warnungsseite anzuzeigen. </span><span class="sxs-lookup"><span data-stu-id="e2d42-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="e2d42-128">Nachdem Sie die Untersuchung durchgeführt haben, wechseln Sie zurück zu der Warnung, mit der Sie begonnen haben, markieren Sie den Status der Warnung als **Aufgelöst,** und klassifizieren Sie sie entweder als **False-Warnung** oder **als True-Warnung.**</span><span class="sxs-lookup"><span data-stu-id="e2d42-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="e2d42-129">Das Klassifizieren von Warnungen trägt dazu bei, diese Funktion zu optimieren, um mehr echte Warnungen und weniger falsche Warnungen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="e2d42-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="e2d42-130">Wenn Sie ihn als echte Warnung klassifizieren, können Sie auch eine Bestimmung auswählen, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2d42-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Ein Codeausschnitt des Detailbereichs mit einer aufgelösten Warnung und erweiterter Dropdownliste zur Ermittlung](images/alert-details-resolved-true.png)

<span data-ttu-id="e2d42-132">Wenn eine falsche Warnung mit einer Geschäftsanwendung auftritt, erstellen Sie eine Unterdrückungsregel, um diese Art von Warnung in Zukunft zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e2d42-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![Aktionen und Klassifizierung im Detailbereich mit hervorgehobener Unterdrückungsregel](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="e2d42-134">Wenn probleme auftreten, die oben nicht beschrieben sind, verwenden Sie die Schaltfläche, um Feedback zu geben 🙂 oder ein Supportticket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e2d42-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e2d42-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e2d42-135">Related topics</span></span>
- [<span data-ttu-id="e2d42-136">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e2d42-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e2d42-137">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="e2d42-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="e2d42-138">Untersuchen einer Datei, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="e2d42-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="e2d42-139">Untersuchen von Geräten in der Liste "Defender for Endpoint Devices"</span><span class="sxs-lookup"><span data-stu-id="e2d42-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="e2d42-140">Untersuchen einer einer Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e2d42-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="e2d42-141">Untersuchen einer Domäne, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="e2d42-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="e2d42-142">Untersuchen eines Benutzerkontos in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2d42-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


