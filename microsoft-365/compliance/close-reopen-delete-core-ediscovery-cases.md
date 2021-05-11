---
title: Schließen, Erneut öffnen und Löschen von Core eDiscovery-Fällen
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
description: In diesem Artikel wird die Verwaltung von Core eDiscovery-Fällen beschrieben. Dies umfasst das Schließen eines Falls, das erneute Öffnen eines geschlossenen Falls und das Löschen eines Falls.
ms.openlocfilehash: 251ca932954071cf949c45343130f122464dcf01
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310880"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="3aa12-104">Schließen, Erneut öffnen und Löschen eines Core eDiscovery-Falls</span><span class="sxs-lookup"><span data-stu-id="3aa12-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="3aa12-105">In diesem Artikel wird beschrieben, wie Sie Core eDiscovery-Fälle in einem Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3aa12-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="3aa12-106">Schließen eines Falls</span><span class="sxs-lookup"><span data-stu-id="3aa12-106">Close a case</span></span>

<span data-ttu-id="3aa12-107">Wenn der von einem Core eDiscovery-Fall unterstützte Rechtsstreit oder die Untersuchung abgeschlossen ist, können Sie den Fall schließen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="3aa12-108">Dies geschieht, wenn Sie einen Fall schließen:</span><span class="sxs-lookup"><span data-stu-id="3aa12-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="3aa12-109">Wenn der Fall eDiscovery-Halte halte enthält, werden sie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3aa12-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="3aa12-110">Nachdem der Haltezeitraum deaktiviert wurde, wird eine 30-tägige Nachfrist (als Verzögerungsverzögerung *bezeichnet)* auf Inhaltsstandorte angewendet, die sich im Haltezeitraum befinden.</span><span class="sxs-lookup"><span data-stu-id="3aa12-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="3aa12-111">Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren können Inhalte suchen und wiederherstellen, bevor sie nach Ablauf des Verzögerungszeitraums endgültig gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="3aa12-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="3aa12-112">Weitere Informationen finden Sie unter [Entfernen von Inhaltsstandorten aus einem eDiscovery-Halteraum.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="3aa12-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="3aa12-113">Durch das Abschließen eines Falls werden nur die Haltebereiche deaktiviert, die diesem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3aa12-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="3aa12-114">Wenn andere Aufbewahrungsspeicherorts an einem Inhaltsspeicherort platziert werden (z. B. ein Prozessaufbewahrungsverfahren, eine Aufbewahrungsrichtlinie oder ein Haltebereich aus einem anderen Core eDiscovery-Fall), werden diese Aufbewahrungsspeicher weiterhin beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="3aa12-115">Der Fall wird weiterhin auf der Seite Core eDiscovery im Microsoft 365 Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3aa12-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3aa12-116">Die Details, Haltebereiche, Suchvorgänge und Mitglieder eines abgeschlossenen Falls bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="3aa12-117">Sie können einen Fall bearbeiten, nachdem er geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3aa12-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="3aa12-118">Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, Suchen erstellen und Suchergebnisse exportieren.</span><span class="sxs-lookup"><span data-stu-id="3aa12-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="3aa12-119">Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht in der Deaktiviertheit von eDiscovery-Haltefällen, wenn ein Fall geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3aa12-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="3aa12-120">So schließen Sie einen Fall ab</span><span class="sxs-lookup"><span data-stu-id="3aa12-120">To close a case:</span></span>
  
1. <span data-ttu-id="3aa12-121">Klicken Sie Microsoft 365 Compliance Center auf **eDiscovery** Core, um die Liste der  >   Core eDiscovery-Fälle in Ihrer Organisation anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="3aa12-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3aa12-122">Klicken Sie auf den Namen des Falls, den Sie schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-122">Click the name of the case that you want to close.</span></span>

   ![Close case on case home page](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="3aa12-124">Klicken Sie auf der Startseite unter **Status** auf **Fall schließen**.</span><span class="sxs-lookup"><span data-stu-id="3aa12-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="3aa12-125">Es wird eine Warnung angezeigt, dass die dem Fall zugeordneten Haltezeichen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3aa12-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="3aa12-126">Klicken **Sie auf Ja,** um den Fall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="3aa12-127">Der Status auf der Fall-Homepage wird von **Aktiv** in **Schließen geändert.**</span><span class="sxs-lookup"><span data-stu-id="3aa12-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="3aa12-128">Klicken Sie **auf der Seite Core eDiscovery** auf **Aktualisieren,** um den Status des geschlossenen Falls zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3aa12-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="3aa12-129">Es kann bis zu 60 Minuten dauern, bis der Abschlussvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3aa12-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="3aa12-130">Wenn der Prozess abgeschlossen ist, wird der Status des Falls auf der Seite Core **eDiscovery** in **Closed** geändert.</span><span class="sxs-lookup"><span data-stu-id="3aa12-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="3aa12-131">Erneuter Öffnen eines geschlossenen Falls</span><span class="sxs-lookup"><span data-stu-id="3aa12-131">Reopen a closed case</span></span>

<span data-ttu-id="3aa12-132">Wenn Sie einen Fall erneut öffnen, werden alle eDiscovery-Haltewerte, die beim Schließen des Falls aktiviert waren, nicht automatisch wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="3aa12-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="3aa12-133">Nachdem der Fall erneut geöffnet wurde, müssen  Sie zur Seite Halte halte wechseln und die vorherigen Halte halte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3aa12-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="3aa12-134">Wenn Sie einen Haltebereich aktivieren möchten, wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann den **Status** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="3aa12-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="3aa12-135">Klicken Sie Microsoft 365 Compliance Center auf **eDiscovery** Core, um die Liste der  >   Core eDiscovery-Fälle in Ihrer Organisation anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="3aa12-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3aa12-136">Klicken Sie auf den Namen des Falls, den Sie erneut öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-136">Click the name of the case that you want to reopen.</span></span>

   ![Erneuter Öffnen eines geschlossenen Falls](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="3aa12-138">Klicken Sie auf der Startseite unter **Status** auf **Erneuter Fall .**</span><span class="sxs-lookup"><span data-stu-id="3aa12-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="3aa12-139">Es wird eine Warnung angezeigt, dass die halte, die dem Fall zugeordnet waren, als er geschlossen wurde, nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3aa12-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="3aa12-140">Klicken Sie **auf Ja,** um den Fall erneut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="3aa12-141">Der Status auf der Flyoutseite für die Fall-Homepage wird von **Closed in** **Active geändert.**</span><span class="sxs-lookup"><span data-stu-id="3aa12-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="3aa12-142">Klicken Sie **auf der Seite Core eDiscovery** auf **Aktualisieren,** um den Status des erneut geöffneten Falls zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3aa12-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="3aa12-143">Es kann bis zu 60 Minuten dauern, bis der Erneutes Öffnen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3aa12-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="3aa12-144">Wenn der Prozess abgeschlossen ist, wird der Status des Falls auf der Seite Core **eDiscovery** in **Aktiv** geändert.</span><span class="sxs-lookup"><span data-stu-id="3aa12-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

7. <span data-ttu-id="3aa12-145">(Optional) Um alle halte, die dem erneut geöffneten Fall zugeordnet sind, zu aktivieren, wechseln Sie zur Registerkarte Halte, wählen Sie einen Haltestatus aus, und aktivieren Sie dann das Kontrollkästchen unter **Status** auf der Flyoutseite für halte. </span><span class="sxs-lookup"><span data-stu-id="3aa12-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="3aa12-146">Löschen eines Falls</span><span class="sxs-lookup"><span data-stu-id="3aa12-146">Delete a case</span></span>

<span data-ttu-id="3aa12-147">Sie können auch aktive und geschlossene Core eDiscovery-Fälle löschen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="3aa12-148">Wenn Sie einen Fall löschen, werden alle Such- und Exporte in dem Fall gelöscht, und der Fall wird aus der Liste der Fälle auf der Seite Core **eDiscovery** im Microsoft 365 Compliance Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="3aa12-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3aa12-149">Sie können einen gelöschten Fall nicht erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="3aa12-150">Bevor Sie einen Fall löschen können (unabhängig davon, ob  er aktiv oder geschlossen ist), müssen Sie zunächst alle eDiscovery-Löscher löschen, die dem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3aa12-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="3aa12-151">Dazu gehört das Löschen von Haltestatus mit dem Status **Aus**.</span><span class="sxs-lookup"><span data-stu-id="3aa12-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="3aa12-152">So löschen Sie einen eDiscovery-Halteraum:</span><span class="sxs-lookup"><span data-stu-id="3aa12-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="3aa12-153">Wechseln Sie **in** dem Fall, den Sie löschen möchten, auf die Registerkarte Halte haltet.</span><span class="sxs-lookup"><span data-stu-id="3aa12-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="3aa12-154">Wählen Sie den Halteraum aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="3aa12-155">Klicken Sie auf der Flyoutseite auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3aa12-155">On the flyout page, click **Delete**.</span></span>

      ![Löschen eines eDiscovery-Halteraums](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="3aa12-157">So löschen Sie einen Fall</span><span class="sxs-lookup"><span data-stu-id="3aa12-157">To delete a case:</span></span>

1. <span data-ttu-id="3aa12-158">Klicken Sie Microsoft 365 Compliance Center auf **eDiscovery** Core, um die Liste der  >   Core eDiscovery-Fälle in Ihrer Organisation anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="3aa12-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3aa12-159">Klicken Sie auf den Namen des Falls, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3aa12-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="3aa12-160">Klicken Sie auf der Fall-Startseite unter **Status** auf **Fall löschen**.</span><span class="sxs-lookup"><span data-stu-id="3aa12-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Erneuter Öffnen eines geschlossenen Falls](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="3aa12-162">Wenn der Fall, den Sie löschen möchten, weiterhin eDiscovery-Halte halte enthält, erhalten Sie eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="3aa12-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="3aa12-163">Sie müssen alle dem Fall zugeordneten Halte halte löschen und dann erneut versuchen, den Fall zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3aa12-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
