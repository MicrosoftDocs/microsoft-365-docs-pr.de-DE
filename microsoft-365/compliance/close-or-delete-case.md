---
title: Schließen oder Löschen eines Falls
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, was passiert, wenn eine Untersuchung oder ein Rechtsfall, der von einem erweiterten eDiscovery-Fall unterstützt wird, geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292411"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="da6f0-103">Schließen oder Löschen eines erweiterten eDiscovery-Falls</span><span class="sxs-lookup"><span data-stu-id="da6f0-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="da6f0-104">Wenn die von einem erweiterten eDiscovery-Fall unterstützte Rechtssache oder Untersuchung abgeschlossen ist, können Sie einen Fall schließen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="da6f0-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="da6f0-105">Sie können auch einen geschlossenen Fall erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="da6f0-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="da6f0-106">Schließen einer Anfrage</span><span class="sxs-lookup"><span data-stu-id="da6f0-106">Close a case</span></span>

<span data-ttu-id="da6f0-107">Hier erfahren Sie, was passiert, wenn Sie einen erweiterten eDiscovery-Fall schließen:</span><span class="sxs-lookup"><span data-stu-id="da6f0-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="da6f0-108">Wenn der Fall alle inhaltsspeicherorte enthält, sind diese Haltestatus deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="da6f0-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="da6f0-109">Dies kann dazu führen, dass Inhalte dauerhaft gelöscht oder gelöscht werden, entweder durch den Benutzer oder durch einen automatisierten Prozess, beispielsweise eine Löschrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="da6f0-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="da6f0-110">Durch das Schließen eines Case werden nur die haltebereiche deaktiviert, die diesem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="da6f0-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="da6f0-111">Wenn andere Aufbewahrungsorte auf einem Inhaltsspeicherort platziert werden (beispielsweise ein Beweissicherungsverfahren, ein zentrales eDiscovery-Archiv oder ein Haltestatus aus einem anderen erweiterten eDiscovery-Fall), werden diese Haltestatus weiterhin beibehalten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="da6f0-112">Der Fall wird weiterhin auf der Seite "eDiscovery" im Microsoft 365 Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="da6f0-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="da6f0-113">Die Details, Aufbewahrungen, Suchvorgänge und Elemente eines geschlossenen Falls werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="da6f0-114">Sie können einen Fall bearbeiten, nachdem er geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="da6f0-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="da6f0-115">Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="da6f0-116">Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht darin, dass die haltebereiche deaktiviert sind, wenn ein Fall geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="da6f0-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="da6f0-117">So schließen Sie einen Fall:</span><span class="sxs-lookup"><span data-stu-id="da6f0-117">To close a case:</span></span>

1. <span data-ttu-id="da6f0-118">Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="da6f0-119">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="da6f0-120">Klicken Sie auf **Fall schließen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-120">Click **Close case**.</span></span>

   <span data-ttu-id="da6f0-121">Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="da6f0-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="da6f0-122">Erneutes Öffnen eines geschlossenen Falls</span><span class="sxs-lookup"><span data-stu-id="da6f0-122">Reopen a closed case</span></span>

<span data-ttu-id="da6f0-123">Wenn Sie einen erweiterten eDiscovery-Fall erneut öffnen, werden alle holdes-Objekte, die beim Schließen des Case-Verfahrens vorhanden waren, nicht automatisch wieder eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="da6f0-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="da6f0-124">Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Registerkarte "halte **Status** " wechseln und die vorherigen Haltestatus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="da6f0-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="da6f0-125">Zum Aktivieren eines haltebereichs wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann die **Status** Umschalttaste **auf**ein fest.</span><span class="sxs-lookup"><span data-stu-id="da6f0-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="da6f0-126">So öffnen Sie einen geschlossenen Fall erneut:</span><span class="sxs-lookup"><span data-stu-id="da6f0-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="da6f0-127">Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="da6f0-128">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="da6f0-129">Klicken Sie auf **Fall erneut öffnen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="da6f0-130">Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="da6f0-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="da6f0-131">Löschen einer Anfrage</span><span class="sxs-lookup"><span data-stu-id="da6f0-131">Delete a case</span></span>

<span data-ttu-id="da6f0-132">Sie können sowohl aktive als auch abgeschlossene erweiterte eDiscovery-Fälle löschen.</span><span class="sxs-lookup"><span data-stu-id="da6f0-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="da6f0-133">Wenn Sie einen Fall löschen, werden alle mit dem Fall verknüpften Komponenten gelöscht, beispielsweise die Liste der Verwalter, Kommunikationen, Suchvorgänge, Überprüfungs Sätze und Exportaufträge.</span><span class="sxs-lookup"><span data-stu-id="da6f0-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="da6f0-134">Der Fall wird aus der Liste der Fälle auf der Seite " **Advanced eDiscovery** " im Microsoft 365 Compliance Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="da6f0-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="da6f0-135">Ein gelöschter Fall kann nicht wiederhergestellt oder erneut geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="da6f0-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="da6f0-136">In Szenarien mit Datenüberlauf besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Überprüfungs Satzes darin, den erweiterten eDiscovery-Fall zu löschen.</span><span class="sxs-lookup"><span data-stu-id="da6f0-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="da6f0-137">Andere Methoden zum Suchen und löschen entfernen keine Elemente aus einem Überprüfungs Satzes.</span><span class="sxs-lookup"><span data-stu-id="da6f0-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="da6f0-138">Bevor Sie einen Fall löschen können (ob er aktiv oder geschlossen ist), müssen Sie zunächst *alle* Haltestatus löschen, die mit der Groß-/Kleinschreibung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="da6f0-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="da6f0-139">Dies umfasst das Löschen von Haltebereichen mit dem Status **Off**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="da6f0-140">So löschen Sie haltebereiche, die einem Fall zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="da6f0-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="da6f0-141">Wechseln Sie zur Registerkarte halte **Status** im erweiterten eDiscovery-Fall, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="da6f0-142">Klicken Sie auf den Haltestatus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="da6f0-143">Klicken Sie auf der Flyout-Seite auf **Haltestatus löschen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="da6f0-144">So löschen Sie einen Fall:</span><span class="sxs-lookup"><span data-stu-id="da6f0-144">To delete a case:</span></span>

1. <span data-ttu-id="da6f0-145">Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="da6f0-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="da6f0-146">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="da6f0-147">Klicken Sie auf **Fall löschen**.</span><span class="sxs-lookup"><span data-stu-id="da6f0-147">Click **Delete case**.</span></span>
