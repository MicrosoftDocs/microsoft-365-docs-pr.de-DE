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
description: Erfahren Sie, was geschieht, wenn eine Untersuchung oder ein von einem Fall Advanced eDiscovery Fall geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657639"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="4867e-103">Schließen oder Löschen eines Advanced eDiscovery Fall</span><span class="sxs-lookup"><span data-stu-id="4867e-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="4867e-104">Wenn die von einem Fall unterstützte Rechts- oder Advanced eDiscovery abgeschlossen ist, können Sie einen Fall schließen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="4867e-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="4867e-105">Sie können auch einen geschlossenen Fall erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="4867e-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="4867e-106">Schließen eines Falls</span><span class="sxs-lookup"><span data-stu-id="4867e-106">Close a case</span></span>

<span data-ttu-id="4867e-107">Dies geschieht, wenn Sie einen Fall Advanced eDiscovery schließen:</span><span class="sxs-lookup"><span data-stu-id="4867e-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="4867e-108">Wenn der Fall in den Haltebereich versetzte Inhaltsspeicherorte enthält, werden diese Haltebereiche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4867e-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="4867e-109">Nachdem der Haltezeitraum deaktiviert wurde, wird eine 30-tägige Nachfrist (als Verzögerungsverzögerung *bezeichnet)* auf Inhaltsstandorte angewendet, die sich im Haltezeitraum befinden.</span><span class="sxs-lookup"><span data-stu-id="4867e-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="4867e-110">Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren können Inhalte suchen oder wiederherstellen, die nach Ablauf des Verzögerungszeitraums endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4867e-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="4867e-111">Weitere Informationen finden Sie unter [Entfernen von Inhaltsstandorten aus einem eDiscovery-Halteraum.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="4867e-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="4867e-112">Durch das Abschließen eines Falls werden nur die Haltebereiche deaktiviert, die diesem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4867e-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="4867e-113">Wenn an einem Inhaltsspeicherort andere Haltewerte (z. B. ein Rechtsstreitigkeiten, ein Core eDiscovery-Haltebereich oder ein Haltebereich von einem anderen Advanced eDiscovery-Fall) stattfinden, werden diese Haltewerte weiterhin beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4867e-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="4867e-114">Der Fall wird weiterhin auf der eDiscovery-Seite im compliance center Microsoft 365 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4867e-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4867e-115">Die Details, Haltebereiche, Suchvorgänge und Mitglieder eines abgeschlossenen Falls bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="4867e-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="4867e-116">Sie können einen Fall bearbeiten, nachdem er geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4867e-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="4867e-117">Sie können z. B. Mitglieder hinzufügen oder entfernen, Suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4867e-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="4867e-118">Der Hauptunterschied zwischen aktiven und abgeschlossenen Fällen ist, dass die Haltebereiche beim Abschließen eines Falls deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4867e-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="4867e-119">So schließen Sie einen Fall ab</span><span class="sxs-lookup"><span data-stu-id="4867e-119">To close a case:</span></span>

1. <span data-ttu-id="4867e-120">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="4867e-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="4867e-121">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="4867e-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="4867e-122">Klicken Sie unten auf **der** Flyoutseite Fallinformationen auf (**...**) **Weitere Optionen**, und klicken Sie dann auf **Schließen Fall**.</span><span class="sxs-lookup"><span data-stu-id="4867e-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Option im Menü Weitere Optionen zum Schließen eines Advanced eDiscovery Fall](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="4867e-124">Es kann bis zu 60 Minuten dauern, bis der Abschlussvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4867e-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="4867e-125">Erneuter Öffnen eines geschlossenen Falls</span><span class="sxs-lookup"><span data-stu-id="4867e-125">Reopen a closed case</span></span>

<span data-ttu-id="4867e-126">Wenn Sie einen Advanced eDiscovery erneut öffnen, werden alle Haltewerte, die beim Schließen des Falls aktiviert wurden, nicht automatisch wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4867e-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="4867e-127">Nachdem der Fall erneut geöffnet wurde, müssen  Sie zur Registerkarte Halte halten wechseln und die vorherigen Halte halte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4867e-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="4867e-128">Wenn Sie einen Haltebereich aktivieren möchten, wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann den **Status** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="4867e-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="4867e-129">So öffnen Sie einen geschlossenen Fall erneut:</span><span class="sxs-lookup"><span data-stu-id="4867e-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="4867e-130">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie erneut öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="4867e-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="4867e-131">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="4867e-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="4867e-132">Klicken Sie unten auf **der** Flyoutseite Fallinformationen auf (**...**) **Weitere Optionen**, und klicken Sie dann auf **Erneuter Fall .**</span><span class="sxs-lookup"><span data-stu-id="4867e-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Option im Menü Weitere Optionen zum erneuten Öffnen eines Advanced eDiscovery Fall](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="4867e-134">Es kann bis zu 60 Minuten dauern, bis der Erneutes Öffnen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4867e-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="4867e-135">Löschen eines Falls</span><span class="sxs-lookup"><span data-stu-id="4867e-135">Delete a case</span></span>

<span data-ttu-id="4867e-136">Sie können sowohl aktive als auch geschlossene Advanced eDiscovery löschen.</span><span class="sxs-lookup"><span data-stu-id="4867e-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="4867e-137">Wenn Sie einen Fall löschen, werden alle dem Fall zugeordneten Komponenten, z. B. die Liste von Verwaltern, die Kommunikation, Suchvorgänge, Überprüfungssätze und der Exportvorgang, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4867e-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="4867e-138">Der Fall wird aus der Liste  der Fälle auf der Advanced eDiscovery im Microsoft 365 Compliance Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="4867e-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4867e-139">Sie können einen gelöschten Fall nicht wiederherstellen oder erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="4867e-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="4867e-140">In Szenarien mit Datenlecks besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Überprüfungssatz in der Löschung Advanced eDiscovery Fall.</span><span class="sxs-lookup"><span data-stu-id="4867e-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="4867e-141">Andere Such- und Bereinigungsmethoden entfernen keine Elemente aus einem Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="4867e-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="4867e-142">Bevor Sie einen Fall löschen können (unabhängig davon, ob  er aktiv oder geschlossen ist), müssen Sie zunächst alle dem Fall zugeordneten Halte halte löschen.</span><span class="sxs-lookup"><span data-stu-id="4867e-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="4867e-143">Dazu gehört das Löschen von Haltestatus mit dem Status **Aus**.</span><span class="sxs-lookup"><span data-stu-id="4867e-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="4867e-144">So löschen Sie halte, die einem Fall zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="4867e-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="4867e-145">Wechseln Sie **in** der Advanced eDiscovery, die Sie löschen möchten, auf die Registerkarte Halte haltet.</span><span class="sxs-lookup"><span data-stu-id="4867e-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="4867e-146">Klicken Sie auf den Halteraum, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="4867e-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="4867e-147">Klicken Sie auf der Flyoutseite auf **Halten löschen**.</span><span class="sxs-lookup"><span data-stu-id="4867e-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="4867e-148">So löschen Sie einen Fall</span><span class="sxs-lookup"><span data-stu-id="4867e-148">To delete a case:</span></span>

1. <span data-ttu-id="4867e-149">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="4867e-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="4867e-150">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="4867e-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="4867e-151">Klicken Sie unten auf **der** Flyoutseite Fallinformationen auf (**...**) **Weitere Optionen**, und klicken Sie dann auf **Fall löschen**.</span><span class="sxs-lookup"><span data-stu-id="4867e-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Option im Menü Weitere Optionen zum Löschen eines Advanced eDiscovery Fall](..\Media\DeleteAdvancedeDiscoveryCase.png)
