---
title: Verwalten von Microsoft Defender für Endpunkt-Vorfällen
description: Verwalten Sie Vorfälle, indem Sie sie zuweisen, ihren Status aktualisieren oder die Klassifizierung festlegen.
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
ms.openlocfilehash: c86b53abf54788740c8c78cb0ecf9251b10ea8f7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842338"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="f7cc6-104">Verwalten von Microsoft Defender für Endpunkt-Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f7cc6-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7cc6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7cc6-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7cc6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7cc6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7cc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7cc6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7cc6-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f7cc6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7cc6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f7cc6-110">Die Verwaltung von Vorfällen ist ein wichtiger Bestandteil jedes Cybersicherheitsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="f7cc6-111">Sie können Vorfälle verwalten, indem Sie einen Vorfall in der **Vorfallwarteschlange** oder im **Bereich "Vorfallverwaltung"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="f7cc6-112">Wenn Sie einen Vorfall aus der **Vorfallwarteschlange** auswählen, wird der **Bereich "Vorfallverwaltung"** angezeigt, auf dem Sie die Vorfallseite für Details öffnen können.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Abbildung des Bereichs "Vorfallverwaltung"](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="f7cc6-114">Sie können Sich selbst Vorfälle zuweisen, den Status und die Klassifizierung ändern, umbenennen oder kommentieren, um ihren Fortschritt nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="f7cc6-115">Für eine zusätzliche Sichtbarkeit auf einen Blick werden Vorfallnamen automatisch basierend auf Warnungsattributen generiert, z. B. der Anzahl der betroffenen Endpunkte, betroffenen Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="f7cc6-116">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="f7cc6-117">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="f7cc6-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="f7cc6-118">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihre Namen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Abbildung der Vorfalldetailseite](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="f7cc6-120">Zuweisen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f7cc6-120">Assign incidents</span></span>
<span data-ttu-id="f7cc6-121">Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **"Mir zuweisen"** auswählen, um den Vorfall sich selbst zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="f7cc6-122">Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="f7cc6-123">Festlegen des Status und der Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f7cc6-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="f7cc6-124">Status des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="f7cc6-124">Incident status</span></span>
<span data-ttu-id="f7cc6-125">Sie können Ereignisse kategorisieren (z.B. als **aktive** oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="f7cc6-126">Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="f7cc6-127">Beispielsweise kann Ihr SoC-Analyst die dringenden **aktiven** Vorfälle für den Tag überprüfen und sie sich selbst zur Untersuchung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="f7cc6-128">Alternativ kann Ihr SoC-Analyst den Vorfall als **behoben** festlegen, wenn der Vorfall behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="f7cc6-129">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f7cc6-129">Classification</span></span>
<span data-ttu-id="f7cc6-130">Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="f7cc6-131">Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="f7cc6-132">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f7cc6-132">Add comments</span></span>
<span data-ttu-id="f7cc6-133">Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="f7cc6-134">Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="f7cc6-135">Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7cc6-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="f7cc6-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f7cc6-136">Related topics</span></span>
- [<span data-ttu-id="f7cc6-137">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="f7cc6-137">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="f7cc6-138">Anzeigen und Organisieren der Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="f7cc6-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="f7cc6-139">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f7cc6-139">Investigate incidents</span></span>](investigate-incidents.md)
