---
title: Schließen, erneutes Öffnen und Löschen von zentralen eDiscovery-Fällen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie zentrale eDiscovery-Fälle verwalten. Dazu gehört das Schließen einer Anfrage, das erneute Öffnen eines geschlossenen Falls und das Löschen einer Anfrage.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412794"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="b791f-104">Schließen, erneutes Öffnen und Löschen eines zentralen eDiscovery-Falls</span><span class="sxs-lookup"><span data-stu-id="b791f-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="b791f-105">In diesem Artikel wird beschrieben, wie Sie zentrale eDiscovery-Fälle in Microsoft 365 schließen, erneut öffnen und löschen.</span><span class="sxs-lookup"><span data-stu-id="b791f-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="b791f-106">Schließen einer Anfrage</span><span class="sxs-lookup"><span data-stu-id="b791f-106">Close a case</span></span>

<span data-ttu-id="b791f-107">Wenn die von einem zentralen eDiscovery-Fall unterstützte Rechtssache oder Untersuchung abgeschlossen ist, können Sie den Fall schließen.</span><span class="sxs-lookup"><span data-stu-id="b791f-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="b791f-108">Hier erfahren Sie, was passiert, wenn Sie einen Fall schließen:</span><span class="sxs-lookup"><span data-stu-id="b791f-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="b791f-109">Wenn der Fall inhaltsspeicherorte in der eDiscovery-Aufbewahrungsstelle enthält, werden diese Haltestatus deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b791f-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="b791f-110">Nachdem der Haltestatus deaktiviert wurde, wird eine 30-tägige Kulanzfrist (so genannte *Verzögerungs*Speicher) auf Aufbewahrungsorte für Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="b791f-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="b791f-111">Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren können den Inhalt suchen und wiederherstellen, bevor er nach Ablauf des Verzögerungszeitraums endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b791f-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="b791f-112">Weitere Informationen finden Sie unter [Entfernen von Inhaltsspeicherorten aus einer eDiscovery-Aufbewahrung](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="b791f-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="b791f-113">Durch das Schließen eines Case werden nur die haltebereiche deaktiviert, die diesem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b791f-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="b791f-114">Wenn andere haltebereiche an einem Inhaltsspeicherort (beispielsweise ein Beweissicherungsverfahren, eine Aufbewahrungsrichtlinie oder ein Haltestatus von einem anderen zentralen eDiscovery-Fall) gespeichert werden, werden diese Aufbewahrungsorte weiterhin beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b791f-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="b791f-115">Der Fall wird weiterhin auf der zentralen eDiscovery-Seite im Microsoft 365 Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b791f-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b791f-116">Die Details, Aufbewahrungen, Suchvorgänge und Elemente eines geschlossenen Falls werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b791f-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="b791f-117">Sie können einen Fall bearbeiten, nachdem er geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b791f-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="b791f-118">Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, suchen erstellen und Suchergebnisse exportieren.</span><span class="sxs-lookup"><span data-stu-id="b791f-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="b791f-119">Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht darin, dass eDiscovery-Haltestatus deaktiviert sind, wenn ein Fall geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b791f-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="b791f-120">So schließen Sie einen Fall:</span><span class="sxs-lookup"><span data-stu-id="b791f-120">To close a case:</span></span>
  
1. <span data-ttu-id="b791f-121">Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery**  >  **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b791f-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b791f-122">Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="b791f-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="b791f-123">Die Dropdown Seite **diesen Fall verwalten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b791f-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="b791f-124">Klicken Sie unter **Fall Status verwalten**auf **Schließ Fall**.</span><span class="sxs-lookup"><span data-stu-id="b791f-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="b791f-125">Es wird eine Warnung angezeigt, die besagt, dass die dem Fall zugeordneten Haltestatus deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b791f-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="b791f-126">Klicken Sie auf **Ja** , um den Fall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b791f-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="b791f-127">Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **aktiv** " in " **Schließen**" geändert.</span><span class="sxs-lookup"><span data-stu-id="b791f-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="b791f-128">Schließen Sie die Seite **diesen Fall verwalten** .</span><span class="sxs-lookup"><span data-stu-id="b791f-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="b791f-129">Klicken Sie auf der **zentralen eDiscovery** -Seite auf **Aktualisieren** , um den Status des geschlossenen Falls zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b791f-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="b791f-130">Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b791f-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="b791f-131">Wenn der Prozess abgeschlossen ist, wird der Status der Anfrage in **geschlossen** auf der **zentralen eDiscovery** -Seite geändert.</span><span class="sxs-lookup"><span data-stu-id="b791f-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="b791f-132">Klicken Sie erneut auf den Namen der Anfrage, um die Flyout-Seite " **diesen Fall verwalten** " anzuzeigen, die Informationen dazu enthält, wann der Fall geschlossen wurde und wer ihn geschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="b791f-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="b791f-133">Erneutes Öffnen eines geschlossenen Falls</span><span class="sxs-lookup"><span data-stu-id="b791f-133">Reopen a closed case</span></span>

<span data-ttu-id="b791f-134">Wenn Sie einen Fall erneut öffnen, werden alle eDiscovery-Aufbewahrungsorte, die bei der Schließung des Falles abgeschlossen wurden, nicht automatisch wieder eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="b791f-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="b791f-135">Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Seite "halte **Status** " wechseln und die vorherigen Haltestatus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b791f-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="b791f-136">Zum Aktivieren eines haltebereichs wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann die **Status** Umschalttaste **auf**ein fest.</span><span class="sxs-lookup"><span data-stu-id="b791f-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="b791f-137">Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery**  >  **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b791f-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b791f-138">Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie erneut öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="b791f-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="b791f-139">Die Dropdown Seite **diesen Fall verwalten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b791f-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="b791f-140">Klicken Sie unter **Fall Status verwalten**auf **erneuter Fall öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b791f-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="b791f-141">Es wird eine Warnung angezeigt, die besagt, dass die haltebereiche, die dem Fall beim Schließen zugeordnet waren, nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b791f-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="b791f-142">Klicken Sie auf **Ja** , um die Anfrage erneut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b791f-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="b791f-143">Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **geschlossen** " in " **aktiv**" geändert.</span><span class="sxs-lookup"><span data-stu-id="b791f-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="b791f-144">Schließen Sie die Seite **diesen Fall verwalten** .</span><span class="sxs-lookup"><span data-stu-id="b791f-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="b791f-145">Klicken Sie auf der **zentralen eDiscovery** -Seite auf **Aktualisieren** , um den Status des erneut geöffneten Falls zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b791f-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="b791f-146">Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b791f-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="b791f-147">Wenn der Prozess abgeschlossen ist, wird der Status der Groß-/Kleinschreibung auf der **zentralen eDiscovery** -Seite in " **aktiv** " geändert.</span><span class="sxs-lookup"><span data-stu-id="b791f-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="b791f-148">Löschen einer Anfrage</span><span class="sxs-lookup"><span data-stu-id="b791f-148">Delete a case</span></span>

<span data-ttu-id="b791f-149">Sie können auch aktive und geschlossene Haupt-eDiscovery-Fälle löschen.</span><span class="sxs-lookup"><span data-stu-id="b791f-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="b791f-150">Wenn Sie einen Fall löschen, werden alle Suchvorgänge und Exporte gelöscht, und der Fall wird aus der Liste der Fälle auf der **zentralen eDiscovery** -Seite im Microsoft 365 Compliance Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="b791f-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b791f-151">Sie können einen gelöschten Fall nicht erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="b791f-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="b791f-152">Bevor Sie einen Fall löschen können (ob er aktiv oder geschlossen ist), müssen Sie zuerst *alle* eDiscovery-Haltestatus löschen, die mit der Anfrage verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="b791f-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="b791f-153">Dies umfasst das Löschen von Haltebereichen mit dem Status **Off**.</span><span class="sxs-lookup"><span data-stu-id="b791f-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="b791f-154">So löschen Sie eine eDiscovery-Sperre:</span><span class="sxs-lookup"><span data-stu-id="b791f-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="b791f-155">Wechseln Sie zur Registerkarte halte **Status** in dem Fall, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b791f-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="b791f-156">Klicken Sie auf den Haltestatus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b791f-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="b791f-157">Klicken Sie auf der Flyout-Seite auf **Haltestatus löschen**.</span><span class="sxs-lookup"><span data-stu-id="b791f-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="b791f-158">So löschen Sie einen Fall:</span><span class="sxs-lookup"><span data-stu-id="b791f-158">To delete a case:</span></span>

1. <span data-ttu-id="b791f-159">Klicken Sie im Microsoft 365 Compliance Center auf **eDiscovery**  >  **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b791f-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b791f-160">Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b791f-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="b791f-161">Klicken Sie unter **Fall Status verwalten** auf der Flyout-Seite auf **Fall löschen**.</span><span class="sxs-lookup"><span data-stu-id="b791f-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="b791f-162">Wenn der Fall, den Sie löschen möchten, weiterhin eDiscovery-Haltestatus enthält, erhalten Sie eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="b791f-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="b791f-163">Sie müssen alle dem Fall zugeordneten haltebereiche löschen und dann erneut versuchen, die Groß-/Kleinschreibung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b791f-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
