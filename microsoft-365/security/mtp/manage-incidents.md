---
title: Verwalten von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie einen Status zuweisen und aktualisieren können,
keywords: Vorfall, Vorfälle, Alert, korrelierte Alerts, zuweisen, aktualisieren, Status, verwalten, Klassifizierung, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930630"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="103bd-104">Verwalten von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="103bd-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="103bd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="103bd-105">**Applies to:**</span></span>
- <span data-ttu-id="103bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="103bd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="103bd-107">Das Verwalten von Vorfällen ist entscheidend, um sicherzustellen, dass Bedrohungen eingedämmt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="103bd-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="103bd-108">In Microsoft 365 Defender haben Sie Zugriff auf die Verwaltung von Vorfällen auf Geräten, Benutzern und Postfächern.</span><span class="sxs-lookup"><span data-stu-id="103bd-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="103bd-109">Sie können Vorfälle verwalten, indem Sie einen Vorfall aus der Warteschlange **Vorfälle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="103bd-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="103bd-110">Sie können den Namen eines Vorfalls bearbeiten, ihn auflösen, seine Klassifizierung und Bestimmung festlegen.</span><span class="sxs-lookup"><span data-stu-id="103bd-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="103bd-111">Sie können den Vorfall auch sich selbst zuweisen, Ereigniskategorien und Kommentare hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="103bd-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="103bd-112">In Fällen, in denen Sie bei der Untersuchung bestimmte Alerts von einem Vorfall auf einen anderen verschieben möchten, können Sie dies auch über die Registerkarte "Alerts" tun und so einen größeren oder kleineren Vorfall erstellen, der alle relevanten Alerts enthält.</span><span class="sxs-lookup"><span data-stu-id="103bd-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="103bd-113">Name des Vorfalls bearbeiten</span><span class="sxs-lookup"><span data-stu-id="103bd-113">Edit incident name</span></span>
<span data-ttu-id="103bd-114">Vorfällen wird automatisch ein Name basierend auf Warnungsattributen zugewiesen, z. B. die Anzahl der betroffenen Endpunkte, der betroffenen Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="103bd-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="103bd-115">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="103bd-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="103bd-116">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="103bd-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="103bd-117">Sie können den Namen des Vorfalls ändern, damit er besser mit Ihrer bevorzugten Benennungskonvention übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="103bd-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="103bd-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span><span class="sxs-lookup"><span data-stu-id="103bd-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="103bd-119">Zuweisen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="103bd-119">Assign incidents</span></span>
<span data-ttu-id="103bd-120">Falls ein Vorfall noch nicht zugewiesen wurde, können Sie **Mir zuweisen** auswählen, um sich den Vorfall selbst zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="103bd-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="103bd-121">Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.</span><span class="sxs-lookup"><span data-stu-id="103bd-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="103bd-122">Festlegen des Status und der Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="103bd-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="103bd-123">Status des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="103bd-123">Incident status</span></span>
<span data-ttu-id="103bd-124">Sie können Ereignisse kategorisieren (z.B. als **aktive** oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet.</span><span class="sxs-lookup"><span data-stu-id="103bd-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="103bd-125">Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.</span><span class="sxs-lookup"><span data-stu-id="103bd-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="103bd-126">So kann Ihr SOC-Analyst beispielsweise die dringlichen **aktiven** Vorfälle für den Tag überprüfen und sich entscheiden, sie sich selbst zur Untersuchung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="103bd-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="103bd-127">Alternativ kann Ihr SOC-Analyst den Vorfall als **aufgelöst** einstufen, wenn der Vorfall behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="103bd-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="103bd-128">Wenn Sie einen Vorfall auflösen, werden automatisch alle Alerts geschlossen, die Teil des Vorfalls sind und bis dahin noch offen sind.</span><span class="sxs-lookup"><span data-stu-id="103bd-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="103bd-129">Klassifizierung und Ermittlung</span><span class="sxs-lookup"><span data-stu-id="103bd-129">Classification and determination</span></span>
<span data-ttu-id="103bd-130">Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist.</span><span class="sxs-lookup"><span data-stu-id="103bd-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="103bd-131">Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.</span><span class="sxs-lookup"><span data-stu-id="103bd-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="103bd-132">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="103bd-132">Add comments</span></span>
<span data-ttu-id="103bd-133">Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="103bd-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="103bd-134">Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="103bd-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="103bd-135">Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="103bd-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="103bd-136">Hinzufügen von Ereigniskategorien</span><span class="sxs-lookup"><span data-stu-id="103bd-136">Add incident tags</span></span>
<span data-ttu-id="103bd-137">Sie können einem Vorfall benutzerdefinierte Kategorien hinzufügen, um beispielsweise eine Gruppe von Vorfällen mit einer gemeinsamen Charakteristik zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="103bd-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="103bd-138">Sie können die Liste der Vorfälle später nach allen Einträgen filtern, die eine bestimmte Kategorie enthalten.</span><span class="sxs-lookup"><span data-stu-id="103bd-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
