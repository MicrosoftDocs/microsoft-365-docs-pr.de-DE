---
title: Verwalten von Depotbanken in einem erweiterten eDiscovery-Fall
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
description: ''
ms.openlocfilehash: 0b6776571f4abafaf8e050fa6c31311df452d90e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582914"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="45e4e-102">Verwalten von Depotbanken in einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="45e4e-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="45e4e-103">Die Registerkarte depotverwalter in Advanced eDiscovery enthält eine Liste aller depotverwalter, die dem Fall hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="45e4e-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="45e4e-104">Nachdem Sie einem Fall Verwalter hinzugefügt haben, werden Details zu jeder Depotbank automatisch aus Azure Active Directory gesammelt und in Advanced eDiscovery angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45e4e-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Verwalten von Depotbanken](media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="45e4e-106">Anzeigen von Depot Details</span><span class="sxs-lookup"><span data-stu-id="45e4e-106">View custodian details</span></span>

<span data-ttu-id="45e4e-107">Um die Details zu einer Depotbank anzuzeigen, klicken Sie in der Liste auf der Registerkarte **depotverwalter** auf die Depotbank. Eine Flyout-Seite wird angezeigt und enthält die folgenden Informationen zur Depotbank:</span><span class="sxs-lookup"><span data-stu-id="45e4e-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="45e4e-108">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="45e4e-108">Contact information</span></span>

  - <span data-ttu-id="45e4e-109">**Anzeigename** : der Name, der im Adressbuch für die Depotbank angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="45e4e-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="45e4e-110">Dies ist in der Regel die Kombination aus Vorname, Vornamen und Nachname des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="45e4e-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="45e4e-111">**Mail/SMTP** – die primäre SMTP-Adresse für die Depotstelle, beispielsweise brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="45e4e-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="45e4e-112">Beachten Sie, dass der Benutzerprinzipalname (UPN) des Verwalters ebenfalls aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45e4e-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="45e4e-113">**Title** – die Position des Verwalters.</span><span class="sxs-lookup"><span data-stu-id="45e4e-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="45e4e-114">**Department** -der Name für die Abteilung, in der die Depotbank arbeitet.</span><span class="sxs-lookup"><span data-stu-id="45e4e-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="45e4e-115">**Manager** -Verwalter des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="45e4e-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="45e4e-116">Der designierte Manager erhält eine Eskalations Kommunikation für diese Depotbank.</span><span class="sxs-lookup"><span data-stu-id="45e4e-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="45e4e-117">Standortinformationen</span><span class="sxs-lookup"><span data-stu-id="45e4e-117">Location information</span></span>

  - <span data-ttu-id="45e4e-118">**City** – die Stadt, in der sich die Depotbank befindet.</span><span class="sxs-lookup"><span data-stu-id="45e4e-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="45e4e-119">**State** -der Staat oder die Provinz in der Depotbank-Adresse.</span><span class="sxs-lookup"><span data-stu-id="45e4e-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="45e4e-120">**Land/Region** – das Land/die Region, in dem sich die Depotbank befindet.</span><span class="sxs-lookup"><span data-stu-id="45e4e-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="45e4e-121">**Office** – der Office-Standort im Geschäftssitz der Depotbank.</span><span class="sxs-lookup"><span data-stu-id="45e4e-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="45e4e-122">Fall Informationen</span><span class="sxs-lookup"><span data-stu-id="45e4e-122">Case information</span></span>

  - <span data-ttu-id="45e4e-123">**Haltestatus** -gibt an, ob die Depotstelle in die Warteschleife gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="45e4e-124">**Kommunikationsstatus**: gibt an, ob der Depotbank ein Aufbewahrungs Vermerk ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="45e4e-125">Wenn der Depotbank eine Benachrichtigung ausgestellt wurde, wird dieser Wert dieser Eigenschaft **veröffentlicht**.</span><span class="sxs-lookup"><span data-stu-id="45e4e-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="45e4e-126">Wenn der Depotbank kein Hinweis erteilt wurde, wird der Status nicht **veröffentlicht**.</span><span class="sxs-lookup"><span data-stu-id="45e4e-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="45e4e-127">**Status** -der Status der Depotbank in der Anfrage.</span><span class="sxs-lookup"><span data-stu-id="45e4e-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="45e4e-128">Der Status **aktiv** gibt an, dass die Depotbank Teil des Falles ist.</span><span class="sxs-lookup"><span data-stu-id="45e4e-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="45e4e-129">Wenn ein depotverwalter von einem Fall freigegeben wird, wird der Status in " **freigegeben**" geändert.</span><span class="sxs-lookup"><span data-stu-id="45e4e-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="45e4e-130">Datenquellen und Indizierungsinformationen</span><span class="sxs-lookup"><span data-stu-id="45e4e-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="45e4e-131">**Datenquellen** : zeigt die Anzahl und den Typ der Datenquellen (Postfächer, Websites und Teams) an, die der Depotbank zugeordnet sind und Teil des Falles sind.</span><span class="sxs-lookup"><span data-stu-id="45e4e-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="45e4e-132">**Index updated Time** -gibt die Uhrzeit und das Datum für den Zeitpunkt an, zu dem der erweiterte Indizierungs Auftrag zuletzt ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="45e4e-133">Diese Eigenschaft gibt auch an, wann der erweiterte Indizierungsprozess derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45e4e-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="45e4e-134">Bearbeiten einer Depotstelle</span><span class="sxs-lookup"><span data-stu-id="45e4e-134">Edit a custodian</span></span>

<span data-ttu-id="45e4e-135">Wenn Ihr Fall fortschreitet, stellen Sie möglicherweise fest, dass für eine bestimmte Depotbank #a0 Ihrem Fall möglicherweise zusätzliche Datenquellen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="45e4e-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="45e4e-136">In anderen Szenarien möchten Sie möglicherweise bestimmte Datenquellen entfernen, die überprüft und als nicht relevant erachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="45e4e-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="45e4e-137">So aktualisieren Sie die Datenquellen, die einer Depotbank zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="45e4e-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="45e4e-138">Wechseln Sie zu **eDiscovery #a0 Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="45e4e-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="45e4e-139">Klicken Sie auf die Registerkarte **depotverwalter** .</span><span class="sxs-lookup"><span data-stu-id="45e4e-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="45e4e-140">Wählen Sie in der Liste eine Depotbank aus, und klicken Sie auf der Flyout-Seite auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="45e4e-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Bearbeiten von Datenquellen](media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="45e4e-142">Klicken Sie auf **Datenquellen** Registerkarte auswählen, um die Einstellungen für das Exchange-Postfach und das OneDrive-Konto der Depotbank zu ändern, indem Sie auf **Datenquellen auswählen**klicken.</span><span class="sxs-lookup"><span data-stu-id="45e4e-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="45e4e-143">Klicken Sie auf die Registerkarte **Weitere Datenquellen auswählen** , um Teams, SharePoint-oder Exchange-Postfächer hinzuzufügen oder zu entfernen, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="45e4e-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="45e4e-144">Weitere Informationen zu Datenquellen, die einer Depotbank zugeordnet sind, finden Sie unter "Schritt 3: Zuordnen zusätzlicher Datenquellen zu einer Depotbank" unter [Hinzufügen von Depotstellen zu einem Fall](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span><span class="sxs-lookup"><span data-stu-id="45e4e-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="45e4e-145">Klicken Sie auf **Depot Platz** Halter, um den Haltebereich für die Depotbank zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="45e4e-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="45e4e-146">Beheben von Depot Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="45e4e-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="45e4e-147">In den meisten eDiscovery-Workflows für rechtliche Untersuchungen wird eine Teilmenge der Daten eines Depotinhabers durchsucht, nachdem die Depotbank einem Rechtsfall hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="45e4e-148">Aufgrund sehr großer Dateigrößen oder möglicher Datenbeschädigungen können einige Elemente in den Datenquellen, die einer Depotbank zugeordnet sind, teilweise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="45e4e-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="45e4e-149">Mithilfe der [erweiterten Indizierungs](indexing-custodian-data.md) Funktion in der erweiterten eDiscovery können die meisten teilweise indizierten Elemente automatisch durch Erneutes Indizieren dieser Elemente bei Bedarf behoben werden.</span><span class="sxs-lookup"><span data-stu-id="45e4e-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="45e4e-150">Wenn eine Depotstelle einem Fall hinzugefügt wird, werden die Daten, die sich in den Datenquellen befinden, die der Depotbank zugeordnet sind, automatisch erneut indiziert (durch den erweiterten Indizierungsprozess).</span><span class="sxs-lookup"><span data-stu-id="45e4e-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="45e4e-151">Dies bedeutet, dass Sie die Daten in einem Ort lassen können, anstatt Sie herunterladen und korrigieren und dann offline durchsuchen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="45e4e-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="45e4e-152">Während des Lebenszyklus eines Rechts Falls können jedoch neue Datenquellen einer Depotbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="45e4e-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="45e4e-153">In diesem Fall indizieren Sie die Daten der Depotbank neu, indem Sie den erweiterten Indizierungsprozess erneut durchführen, um teilweise indizierte Elemente zu korrigieren und den Index für die Daten der Depotbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="45e4e-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="45e4e-154">So lösen Sie den erneuten Indizierungsprozess zum Adressieren von teilweise indizierten Elementen aus:</span><span class="sxs-lookup"><span data-stu-id="45e4e-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="45e4e-155">Wechseln Sie zu **eDiscovery #a0 Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="45e4e-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="45e4e-156">Klicken Sie auf die **Registerkarte depotverwalter**, und wählen Sie dann eine Depotbank aus, deren Daten neu indiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="45e4e-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="45e4e-157">Klicken Sie auf der Seite Flyout auf **Index aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="45e4e-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="45e4e-158">Es wird ein Dialogfeld angezeigt, das besagt, dass der Index Auftrag erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="45e4e-159">Das erneute Indizieren von Depotdaten ist ein langwieriger Prozess; der entsprechende Auftrag, der erstellt wird, wird als **erneute Indizierung von Depotdaten**bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="45e4e-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="45e4e-160">Sie können den Fortschritt auf der Registerkarte **Aufträge** oder auf der Registerkarte **depotverwalter** verfolgen, indem Sie den Status in der Spalte **Indizierungs Auftragsstatus** überwachen.</span><span class="sxs-lookup"><span data-stu-id="45e4e-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="45e4e-161">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="45e4e-161">For more information, see:</span></span>

- [<span data-ttu-id="45e4e-162">Arbeiten mit Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="45e4e-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="45e4e-163">Verwalten von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="45e4e-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="45e4e-164">Freigeben einer Depotbank aus einem Fall</span><span class="sxs-lookup"><span data-stu-id="45e4e-164">Release a custodian from a case</span></span>

<span data-ttu-id="45e4e-165">Eine Depotbank wird in Situationen, in denen ein Fall geschlossen wird, freigegeben, die Depotbank ist nicht mehr verpflichtet, Inhalte für einen Fall aufzubewahren oder wenn die Depotbank für den Fall nicht mehr relevant erachtet wird.</span><span class="sxs-lookup"><span data-stu-id="45e4e-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="45e4e-166">Wenn Sie einen depotverwalter freigeben, nachdem ein Aufbewahrungs Bescheid veröffentlicht wurde, wird eine Veröffentlichungs Benachrichtigung an die Depotbank gesendet.</span><span class="sxs-lookup"><span data-stu-id="45e4e-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="45e4e-167">Darüber hinaus werden alle in Datenquellen, die mit der Depotbank verknüpft sind, aufgenommenen Haltestatus entfernt.</span><span class="sxs-lookup"><span data-stu-id="45e4e-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="45e4e-168">Wenn die Depotbank in einem *stillen*Speicherplatz genommen wurde und keine Benachrichtigungen über den rechtlichen Aufbewahrungsplatz ausgestellt wurden, wird keine Veröffentlichungs Benachrichtigung gesendet, aber alle auf Datenquellen, die dieser Depotbank zugeordnet sind, bereitgestellten Haltestatus werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="45e4e-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="45e4e-169">So veröffentlichen Sie eine Depotstelle:</span><span class="sxs-lookup"><span data-stu-id="45e4e-169">To release a custodian:</span></span> 

1. <span data-ttu-id="45e4e-170">Wechseln Sie zu **eDiscovery #a0 Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="45e4e-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="45e4e-171">Wechseln Sie zur Registerkarte **depotverwalter** .</span><span class="sxs-lookup"><span data-stu-id="45e4e-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="45e4e-172">Klicken Sie auf die **Registerkarte depotverwalter**, und wählen Sie dann die Depotbank aus, die für den Fall freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="45e4e-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="45e4e-173">Klicken Sie auf der Seite Flyout auf **Versionsverwalter**.</span><span class="sxs-lookup"><span data-stu-id="45e4e-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="45e4e-174">Eine Warn Seite wird angezeigt, in der erläutert wird, dass der Haltebereich entfernt wird, wenn ein Haltebereich in einer Datenquelle gespeichert wird, die mit der Depotbank verknüpft ist, und dass alle anderen Halterungen, die einem anderen erweiterten eDiscovery-Fall zugeordnet sind, weiterhin zutreffen.</span><span class="sxs-lookup"><span data-stu-id="45e4e-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="45e4e-175">Dies umfasst andere Arten von Konservierungs-und Aufbewahrungs Features in Office 365 (beispielsweise eine Office 365-Aufbewahrungsrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="45e4e-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="45e4e-176">Klicken Sie auf **Ja** , um zu bestätigen, dass Sie die Depotbank freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="45e4e-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="45e4e-177">Beachten Sie, dass der Status für diesen Benutzer auf der Registerkarte " **Verwalter** " auf " **freigegeben** " und der **Aufbewahrungs Status** auf der Flyout-Seite in " **false**" geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="45e4e-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="45e4e-178">Eine Depotbank kann gleichzeitig in mehreren Rechtsfällen beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="45e4e-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="45e4e-179">Wenn ein depotverwalter von einem Fall freigegeben wird, werden die Aufbewahrungs-und Benachrichtigungen in anderen Bereichen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="45e4e-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="45e4e-180">Massenbearbeitung von Depot Betreuern</span><span class="sxs-lookup"><span data-stu-id="45e4e-180">Bulk-edit custodians</span></span>

<span data-ttu-id="45e4e-181">Sie können den Massen-Editor verwenden, um mehrere Verwalter gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="45e4e-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="45e4e-182">Wählen Sie dazu einfach mindestens zwei Verwalter auf der Registerkarte **depotverwalter** aus, um den Massen Editor anzuzeigen, und klicken Sie dann auf eine der Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="45e4e-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Flyout-Seite zum Bearbeiten von Einstellungen mehrerer depotverwalter](media/AeDBulkEditCustodians.png)