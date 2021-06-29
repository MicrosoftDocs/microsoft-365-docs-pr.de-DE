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
description: Erfahren Sie, was geschieht, wenn eine Untersuchung oder ein Rechtsfall, der von einem Advanced eDiscovery Fall unterstützt wird, geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194628"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="0bca2-103">Schließen oder Löschen eines Advanced eDiscovery Falls</span><span class="sxs-lookup"><span data-stu-id="0bca2-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="0bca2-104">Wenn der von einem Advanced eDiscovery Fall unterstützte Rechtsfall oder die Untersuchung abgeschlossen ist, können Sie einen Fall schließen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="0bca2-105">Sie können auch einen geschlossenen Fall erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="0bca2-106">Schließen eines Falls</span><span class="sxs-lookup"><span data-stu-id="0bca2-106">Close a case</span></span>

<span data-ttu-id="0bca2-107">Dies geschieht, wenn Sie einen Advanced eDiscovery Fall schließen:</span><span class="sxs-lookup"><span data-stu-id="0bca2-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="0bca2-108">Wenn der Fall in den Haltebereich versetzte Inhaltsspeicherorte enthält, werden diese Haltebereiche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bca2-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="0bca2-109">Nachdem die Aufbewahrung deaktiviert wurde, wird eine 30-tägige Nachfrist (als *Verzögerungssperre* bezeichnet) auf Inhaltsspeicherorte angewendet, die in der Warteschleife waren.</span><span class="sxs-lookup"><span data-stu-id="0bca2-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="0bca2-110">Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren erhalten die Möglichkeit, nach Inhalten zu suchen oder sie wiederherzustellen, die nach Ablauf der Verzögerungssperre endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0bca2-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="0bca2-111">Weitere Informationen finden Sie unter [Entfernen von Inhaltsspeicherorten aus einem eDiscovery-Haltebereich.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="0bca2-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="0bca2-112">Durch das Abschließen eines Falls werden nur die Haltebereiche deaktiviert, die diesem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0bca2-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="0bca2-113">Wenn andere Haltebereiche an einem Inhaltsspeicherort (z. B. einem Beweissicherungsverfahren, einem Core eDiscovery-Haltebereich oder einem Haltebereich eines anderen Advanced eDiscovery Falls) platziert werden, werden diese Haltebereiche weiterhin beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="0bca2-114">The case is still listed on the eDiscovery page in the Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="0bca2-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0bca2-115">Die Details, Haltebereiche, Suchvorgänge und Mitglieder eines abgeschlossenen Falls bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="0bca2-116">Sie können einen Fall bearbeiten, nachdem er geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0bca2-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="0bca2-117">Sie können beispielsweise Mitglieder hinzufügen oder entfernen, Suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="0bca2-118">Der Hauptunterschied zwischen aktiven und abgeschlossenen Fällen ist, dass die Haltebereiche beim Abschließen eines Falls deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0bca2-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="0bca2-119">So schließen Sie einen Fall ab</span><span class="sxs-lookup"><span data-stu-id="0bca2-119">To close a case:</span></span>

1. <span data-ttu-id="0bca2-120">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="0bca2-121">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="0bca2-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

   ![Zugreifen auf die Flyoutseite für Fallinformationen in einem Advanced eDiscovery Fall](..\media\AeDSelectCaseInformation.png) 

3. <span data-ttu-id="0bca2-123">Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen",** und klicken Sie dann auf **"Groß-/Kleinschreibung schließen".**</span><span class="sxs-lookup"><span data-stu-id="0bca2-123">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Close case**.</span></span>

   <span data-ttu-id="0bca2-124">Es kann bis zu 60 Minuten dauern, bis der Abschlussvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0bca2-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="0bca2-125">Erneutes Öffnen eines geschlossenen Falls</span><span class="sxs-lookup"><span data-stu-id="0bca2-125">Reopen a closed case</span></span>

<span data-ttu-id="0bca2-126">Wenn Sie einen Advanced eDiscovery Fall erneut öffnen, werden alle Haltebereiche, die beim Schließen des Falls vorhanden waren, nicht automatisch wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0bca2-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="0bca2-127">Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Registerkarte **"Haltebereiche"** wechseln und die vorherigen Haltebereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0bca2-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="0bca2-128">Wenn Sie einen Haltebereich aktivieren möchten, wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann den **Status** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="0bca2-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="0bca2-129">So öffnen Sie einen geschlossenen Fall erneut:</span><span class="sxs-lookup"><span data-stu-id="0bca2-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="0bca2-130">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie erneut öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="0bca2-131">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="0bca2-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0bca2-132">Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen"** und dann auf **"Groß-/Kleinschreibung erneut öffnen".**</span><span class="sxs-lookup"><span data-stu-id="0bca2-132">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Reopen case**.</span></span>

   <span data-ttu-id="0bca2-133">Es kann bis zu 60 Minuten dauern, bis der erneute Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0bca2-133">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="0bca2-134">Löschen eines Falls</span><span class="sxs-lookup"><span data-stu-id="0bca2-134">Delete a case</span></span>

<span data-ttu-id="0bca2-135">Sie können aktive und geschlossene Advanced eDiscovery Fälle löschen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-135">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="0bca2-136">Wenn Sie einen Fall löschen, werden alle dem Fall zugeordneten Komponenten, z. B. die Liste von Verwaltern, die Kommunikation, Suchvorgänge, Überprüfungssätze und der Exportvorgang, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0bca2-136">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="0bca2-137">Der Fall wird aus der Liste der Fälle auf der **Advanced eDiscovery** Seite im Microsoft 365 Compliance Center entfernt.</span><span class="sxs-lookup"><span data-stu-id="0bca2-137">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0bca2-138">Sie können einen gelöschten Fall nicht wiederherstellen oder erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-138">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="0bca2-139">In Szenarien mit Datenlecks besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Prüfdateisatz darin, den Advanced eDiscovery Fall zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-139">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="0bca2-140">Andere "Such- und Bereinigungsmethoden" entfernen keine Elemente aus einem Prüfdateisatz.</span><span class="sxs-lookup"><span data-stu-id="0bca2-140">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="0bca2-141">Bevor Sie einen Fall löschen können (unabhängig davon, ob er aktiv oder geschlossen ist), müssen Sie zunächst *alle* haltebereiche löschen, die dem Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0bca2-141">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="0bca2-142">Dazu gehört das Löschen von Haltebereichen mit dem Status **"Aus".**</span><span class="sxs-lookup"><span data-stu-id="0bca2-142">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="0bca2-143">So löschen Sie haltebereiche, die einem Fall zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="0bca2-143">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="0bca2-144">Wechseln Sie zur Registerkarte **"Haltebereiche"** im Advanced eDiscovery Fall, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-144">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="0bca2-145">Klicken Sie auf den Haltebereich, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-145">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="0bca2-146">Klicken Sie auf der Flyoutseite auf **"Haltebereich löschen".**</span><span class="sxs-lookup"><span data-stu-id="0bca2-146">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="0bca2-147">So löschen Sie einen Fall</span><span class="sxs-lookup"><span data-stu-id="0bca2-147">To delete a case:</span></span>

1. <span data-ttu-id="0bca2-148">Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bca2-148">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="0bca2-149">Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="0bca2-149">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0bca2-150">Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen",** und klicken Sie dann auf **"Groß-/Kleinschreibung löschen".**</span><span class="sxs-lookup"><span data-stu-id="0bca2-150">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Delete case**.</span></span>

