---
title: Verwalten von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie einen Status zuweisen und aktualisieren können,
keywords: Incident, Incidents, analyze, response, alerts, correlated alerts, assign, update, status, manage, classification, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 09c391d6b02e1273f55070283a6e11454f677114
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300001"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="19e2d-104">Verwalten von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19e2d-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="19e2d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="19e2d-105">**Applies to:**</span></span>
- <span data-ttu-id="19e2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19e2d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="19e2d-107">Die Vorfallverwaltung ist von entscheidender Bedeutung, um sicherzustellen, dass Bedrohungen eindämmt und behoben werden.</span><span class="sxs-lookup"><span data-stu-id="19e2d-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="19e2d-108">Sie verwalten Vorfälle aus Vorfällen **& Warnungen > Vorfällen** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="19e2d-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="19e2d-109">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="19e2d-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

<span data-ttu-id="19e2d-111">Hier sind die Möglichkeiten, wie Sie Ihre Vorfälle verwalten können:</span><span class="sxs-lookup"><span data-stu-id="19e2d-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="19e2d-112">Ändern des Vorfallnamens</span><span class="sxs-lookup"><span data-stu-id="19e2d-112">Change the incident name</span></span>
- <span data-ttu-id="19e2d-113">Fügen Sie Vorfalltags hinzu.</span><span class="sxs-lookup"><span data-stu-id="19e2d-113">Add incident tags.</span></span>
- <span data-ttu-id="19e2d-114">Zuweisen des Vorfalls zu einem Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="19e2d-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="19e2d-115">Auflösen</span><span class="sxs-lookup"><span data-stu-id="19e2d-115">Resolve them</span></span> 
- <span data-ttu-id="19e2d-116">Festlegen der Klassifizierung und Bestimmung</span><span class="sxs-lookup"><span data-stu-id="19e2d-116">Set its classification and determination</span></span>
- <span data-ttu-id="19e2d-117">Fügen Sie Kommentare hinzu.</span><span class="sxs-lookup"><span data-stu-id="19e2d-117">Add comments.</span></span>

<span data-ttu-id="19e2d-118">Sie können Vorfälle im Bereich Vorfall verwalten **für** einen Vorfall verwalten.</span><span class="sxs-lookup"><span data-stu-id="19e2d-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="19e2d-119">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="19e2d-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Beispiel für den Bereich &quot;Vorfall verwalten&quot; eines Vorfalls":::

<span data-ttu-id="19e2d-121">Sie können diesen Bereich über **den** Link Vorfall verwalten auf der folgenden Seite anzeigen:</span><span class="sxs-lookup"><span data-stu-id="19e2d-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="19e2d-122">Eigenschaftenbereich eines Vorfalls in der Vorfallwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="19e2d-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="19e2d-123">**Zusammenfassungsseite** eines Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="19e2d-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="19e2d-124">In Fällen, in denen Sie während der Analyse Warnungen von einem Vorfall  zu einem anderen verschieben möchten, können Sie dies auch auf der Registerkarte Warnungen tun, wodurch ein größerer oder kleinerer Vorfall erstellt wird, der alle relevanten Warnungen enthält.</span><span class="sxs-lookup"><span data-stu-id="19e2d-124">In cases where, while analyzing you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="19e2d-125">Bearbeiten des Vorfallnamens</span><span class="sxs-lookup"><span data-stu-id="19e2d-125">Edit the incident name</span></span>

<span data-ttu-id="19e2d-126">Microsoft 365 Defender weist automatisch einen Namen basierend auf Warnungsattributen zu, z. B. der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="19e2d-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="19e2d-127">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="19e2d-128">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="19e2d-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="19e2d-129">Sie können den Vorfallnamen im Feld **Vorfallname** im Bereich Vorfall **verwalten** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="19e2d-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="19e2d-130">Vorfälle, die vor dem Rollout der funktion für die automatische Benennung von Vorfällen vorhanden waren, behalten ihren Namen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="19e2d-131">Hinzufügen von Ereigniskategorien</span><span class="sxs-lookup"><span data-stu-id="19e2d-131">Add incident tags</span></span>

<span data-ttu-id="19e2d-132">Sie können einem Vorfall benutzerdefinierte Tags hinzufügen, um beispielsweise eine Gruppe von Vorfällen mit einem gemeinsamen Merkmal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="19e2d-133">Sie können die Vorfallwarteschlange später nach allen Vorfällen filtern, die ein bestimmtes Tag enthalten.</span><span class="sxs-lookup"><span data-stu-id="19e2d-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="19e2d-134">Wenn Sie mit der Eingabe beginnen, haben Sie die Möglichkeit, aus einer Liste ausgewählter Tags auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="19e2d-135">Zuweisen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="19e2d-135">Assign incidents</span></span>

<span data-ttu-id="19e2d-136">Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **Zuweisen zu** auswählen und das Benutzerkonto angeben.</span><span class="sxs-lookup"><span data-stu-id="19e2d-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="19e2d-137">Dadurch wird der Besitz des Vorfalls und aller damit verbundenen Warnungen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="19e2d-138">Beheben eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="19e2d-138">Resolve incident</span></span>

<span data-ttu-id="19e2d-139">Wenn der Vorfall behoben wurde, wählen Sie **Vorfall** beheben aus, um den Umschalter nach rechts zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="19e2d-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="19e2d-140">Beachten Sie, dass beim Auflösen eines Vorfalls auch alle verknüpften und aktiven Warnungen im Zusammenhang mit dem Vorfall behoben werden.</span><span class="sxs-lookup"><span data-stu-id="19e2d-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="19e2d-141">Ein nicht aufgelöster Vorfall wird als **Aktiv angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="19e2d-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="19e2d-142">Festlegen der Klassifizierung und Ermittlung</span><span class="sxs-lookup"><span data-stu-id="19e2d-142">Set the classification and determination</span></span>

<span data-ttu-id="19e2d-143">Die Vorfallklassifizierung ist, ob es sich um eine echte warnung oder eine falsche Warnung handelt, die Sie im Feld **Klassifizierung konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="19e2d-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="19e2d-144">Wenn es sich um eine echte Warnung handeln sollte, sollten Sie auch angeben, um welche Art von Bedrohung es sich bei dem Feld **Bestimmung handeln** sollte.</span><span class="sxs-lookup"><span data-stu-id="19e2d-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="19e2d-145">Das Angeben des Bedrohungstyps hilft Ihrem Sicherheitsteam, Bedrohungsmuster zu erkennen und zu handeln, um Ihre Organisation vor ihnen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="19e2d-146">Kommentare hinzufügen</span><span class="sxs-lookup"><span data-stu-id="19e2d-146">Add comments</span></span>

<span data-ttu-id="19e2d-147">Sie können einem Vorfall mit dem Feld Kommentar mehrere **Kommentare** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="19e2d-148">Jeder Kommentar wird den historischen Ereignissen des Vorfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="19e2d-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="19e2d-149">Sie können die Kommentare und den Verlauf eines Vorfalls über den Link **Kommentare und** Verlauf auf der **Seite Zusammenfassung** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="19e2d-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19e2d-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="19e2d-150">Next steps</span></span>

<span data-ttu-id="19e2d-151">Beginnen Sie bei neuen Vorfällen mit ihrer [Untersuchung.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="19e2d-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="19e2d-152">Bei In-Process-Vorfällen setzen Sie Ihre Untersuchung [fort.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="19e2d-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="19e2d-153">Führen Sie bei gelösten Vorfällen eine [Überprüfung nach dem Vorfall durch.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="19e2d-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19e2d-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19e2d-154">See also</span></span>

- [<span data-ttu-id="19e2d-155">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="19e2d-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="19e2d-156">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="19e2d-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="19e2d-157">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="19e2d-157">Investigate incidents</span></span>](investigate-incidents.md)
