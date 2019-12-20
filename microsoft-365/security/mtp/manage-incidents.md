---
title: Verwalten von Vorfällen in Microsoft-Bedrohungsschutz
description: Erfahren Sie, wie Sie einen Status zuweisen und aktualisieren können,
keywords: Vorfall, Vorfälle, Alert, korrelierte Alerts, zuweisen, aktualisieren, Status, verwalten, Klassifizierung, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d6b7c754db3b43e909871a5a60fa1ab155f2d01d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806954"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="6c150-104">Verwalten von Vorfällen in Microsoft-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="6c150-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="6c150-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6c150-105">**Applies to:**</span></span>
- <span data-ttu-id="6c150-106">Microsoft-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="6c150-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6c150-107">Das Verwalten von Vorfällen ist entscheidend, um sicherzustellen, dass Bedrohungen eingedämmt und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6c150-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="6c150-108">Im Microsoft-Bedrohungsschutz haben Sie Zugriff auf die Verwaltung von Vorfällen auf Geräten, Benutzern und in Postfächern.</span><span class="sxs-lookup"><span data-stu-id="6c150-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="6c150-109">Sie können Vorfälle verwalten, indem Sie einen Vorfall aus der Warteschlange **Vorfälle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6c150-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="6c150-110">Sie können den Namen eines Vorfalls bearbeiten, ihn auflösen, seine Klassifizierung und Bestimmung festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c150-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="6c150-111">Sie können den Vorfall auch sich selbst zuweisen, Ereigniskategorien und Kommentare hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c150-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="6c150-112">In Fällen, in denen Sie bei der Untersuchung bestimmte Alerts von einem Vorfall auf einen anderen verschieben möchten, können Sie dies auch über die Registerkarte "Alerts" tun und so einen größeren oder kleineren Vorfall erstellen, der alle relevanten Alerts enthält.</span><span class="sxs-lookup"><span data-stu-id="6c150-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="6c150-113">Name des Vorfalls bearbeiten</span><span class="sxs-lookup"><span data-stu-id="6c150-113">Edit incident name</span></span>
<span data-ttu-id="6c150-114">Standardmäßig wird einem Vorfall eine Zahl zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6c150-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="6c150-115">Sie können den Namen des Vorfalls ändern, damit er besser mit Ihrer bevorzugten Benennungskonvention übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="6c150-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="6c150-116">Zuweisen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6c150-116">Assign incidents</span></span>
<span data-ttu-id="6c150-117">Falls ein Vorfall noch nicht zugewiesen wurde, können Sie **Mir zuweisen** auswählen, um sich den Vorfall selbst zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6c150-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="6c150-118">Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.</span><span class="sxs-lookup"><span data-stu-id="6c150-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="6c150-119">Festlegen des Status und der Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="6c150-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="6c150-120">Status des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="6c150-120">Incident status</span></span>
<span data-ttu-id="6c150-121">Sie können Ereignisse kategorisieren (z.B. als **aktive**oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet.</span><span class="sxs-lookup"><span data-stu-id="6c150-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="6c150-122">Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.</span><span class="sxs-lookup"><span data-stu-id="6c150-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="6c150-123">So kann Ihr SOC-Analyst beispielsweise die dringlichen **aktiven** Vorfälle für den Tag überprüfen und sich entscheiden, sie sich selbst zur Untersuchung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6c150-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="6c150-124">Alternativ kann Ihr SOC-Analyst den Vorfall als **aufgelöst** einstufen, wenn der Vorfall behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="6c150-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="6c150-125">Wenn Sie einen Vorfall auflösen, werden automatisch alle Alerts geschlossen, die Teil des Vorfalls sind und bis dahin noch offen sind.</span><span class="sxs-lookup"><span data-stu-id="6c150-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="6c150-126">Klassifizierung und Ermittlung</span><span class="sxs-lookup"><span data-stu-id="6c150-126">Classification and determination</span></span>
<span data-ttu-id="6c150-127">Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist.</span><span class="sxs-lookup"><span data-stu-id="6c150-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="6c150-128">Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.</span><span class="sxs-lookup"><span data-stu-id="6c150-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="6c150-129">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="6c150-129">Add comments</span></span>
<span data-ttu-id="6c150-130">Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c150-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="6c150-131">Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6c150-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="6c150-132">Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c150-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="6c150-133">Hinzufügen von Ereigniskategorien</span><span class="sxs-lookup"><span data-stu-id="6c150-133">Add incident tags</span></span>
<span data-ttu-id="6c150-134">Sie können einem Vorfall benutzerdefinierte Kategorien hinzufügen, um beispielsweise eine Gruppe von Vorfällen mit einer gemeinsamen Charakteristik zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="6c150-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="6c150-135">Sie können die Liste der Vorfälle später nach allen Einträgen filtern, die eine bestimmte Kategorie enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c150-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

