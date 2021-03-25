---
title: Verwalten von Microsoft Defender ATP-Vorfällen
description: Verwalten von Vorfällen durch Zuweisen, Aktualisieren des Status oder Festlegen der Klassifizierung.
keywords: Vorfälle, verwalten, zuweisen, Status, Klassifizierung, echte Warnung, falsche Warnung
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
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185810"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="d78d2-104">Verwalten von Microsoft Defender for Endpoint-Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d78d2-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d78d2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d78d2-105">**Applies to:**</span></span>
- [<span data-ttu-id="d78d2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d78d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d78d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d78d2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d78d2-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d78d2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d78d2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d78d2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d78d2-110">Die Verwaltung von Vorfällen ist ein wichtiger Bestandteil jedes Cybersicherheitsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="d78d2-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="d78d2-111">Sie können Vorfälle verwalten, indem Sie einen Vorfall in der **Incidents-Warteschlange** oder im **Bereich Incidents Management auswählen.**</span><span class="sxs-lookup"><span data-stu-id="d78d2-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="d78d2-112">Wenn Sie einen Vorfall aus  der **Incidents-Warteschlange auswählen,** wird der Bereich "Vorfallverwaltung" geöffnet, auf dem Sie die Vorfallseite für Details öffnen können.</span><span class="sxs-lookup"><span data-stu-id="d78d2-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Abbildung des Bereichs "Verwaltung von Vorfällen"](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="d78d2-114">Sie können Vorfälle sich selbst zuweisen, den Status und die Klassifizierung ändern, sie umbenennen oder kommentieren, um den Fortschritt nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="d78d2-115">Für eine zusätzliche Sichtbarkeit auf einen Blick werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien generiert.</span><span class="sxs-lookup"><span data-stu-id="d78d2-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="d78d2-116">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="d78d2-117">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="d78d2-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="d78d2-118">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihre Namen bei.</span><span class="sxs-lookup"><span data-stu-id="d78d2-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Abbildung der Detailseite für Vorfälle](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="d78d2-120">Zuweisen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d78d2-120">Assign incidents</span></span>
<span data-ttu-id="d78d2-121">Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **zuweisen** auswählen, um den Vorfall sich selbst zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="d78d2-122">Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.</span><span class="sxs-lookup"><span data-stu-id="d78d2-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="d78d2-123">Festlegen des Status und der Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d78d2-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="d78d2-124">Status des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="d78d2-124">Incident status</span></span>
<span data-ttu-id="d78d2-125">Sie können Ereignisse kategorisieren (z.B. als **aktive** oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet.</span><span class="sxs-lookup"><span data-stu-id="d78d2-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="d78d2-126">Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.</span><span class="sxs-lookup"><span data-stu-id="d78d2-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="d78d2-127">Beispielsweise kann Ihr SoC-Analyst die dringenden **Aktiven** Vorfälle für den Tag überprüfen und sie sich selbst zur Untersuchung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="d78d2-128">Alternativ kann Ihr SoC-Analyst den Vorfall als **Aufgelöst** festlegen, wenn der Vorfall behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="d78d2-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="d78d2-129">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d78d2-129">Classification</span></span>
<span data-ttu-id="d78d2-130">Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist.</span><span class="sxs-lookup"><span data-stu-id="d78d2-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="d78d2-131">Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="d78d2-132">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d78d2-132">Add comments</span></span>
<span data-ttu-id="d78d2-133">Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d78d2-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="d78d2-134">Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d78d2-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="d78d2-135">Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d78d2-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="d78d2-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d78d2-136">Related topics</span></span>
- [<span data-ttu-id="d78d2-137">Warteschlange für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="d78d2-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="d78d2-138">Anzeigen und Organisieren der Incidents-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="d78d2-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="d78d2-139">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d78d2-139">Investigate incidents</span></span>](investigate-incidents.md)
