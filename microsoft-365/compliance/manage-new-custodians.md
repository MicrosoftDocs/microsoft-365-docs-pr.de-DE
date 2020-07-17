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
description: In diesem Artikel erfahren Sie, wie Sie die Liste der depotverwalter in einem erweiterten eDiscovery-Fall anzeigen, bearbeiten und Massen bearbeiten können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b7a7dbec5656a1ac0692ed465eb5a99d7ca11a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024805"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="bcc19-103">Verwalten von Depotbanken in einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="bcc19-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="bcc19-104">Die Seite depotverwalter auf der Registerkarte **Quellen** in einem erweiterten eDiscovery-Fall enthält eine Liste aller depotverwalter, die dem Fall hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bcc19-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="bcc19-105">Nachdem Sie einem Fall Verwalter hinzugefügt haben, werden Details zu jeder Depotbank automatisch aus Azure Active Directory gesammelt und in Advanced eDiscovery angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcc19-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Verwalten von Depotbanken](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="bcc19-107">Anzeigen von Depot Details</span><span class="sxs-lookup"><span data-stu-id="bcc19-107">View custodian details</span></span>

<span data-ttu-id="bcc19-108">Um die Details zu einer Depotbank anzuzeigen, klicken Sie in der Liste auf der Registerkarte **depotverwalter** auf die Depotbank. Eine Flyout-Seite wird angezeigt und enthält die folgenden Informationen zur Depotbank:</span><span class="sxs-lookup"><span data-stu-id="bcc19-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="bcc19-109">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="bcc19-109">Contact information</span></span>

  - <span data-ttu-id="bcc19-110">**Anzeigename** : der Name, der im Adressbuch für die Depotbank angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bcc19-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="bcc19-111">Dies ist in der Regel die Kombination aus Vorname, Vornamen und Nachname des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="bcc19-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="bcc19-112">**Mail/SMTP** – die primäre SMTP-Adresse für die Depotstelle, beispielsweise brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bcc19-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="bcc19-113">Der Benutzerprinzipalname (UPN) der Depotbank wird ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bcc19-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="bcc19-114">**Title** – die Position des Verwalters.</span><span class="sxs-lookup"><span data-stu-id="bcc19-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="bcc19-115">**Department** -der Name für die Abteilung, in der die Depotbank arbeitet.</span><span class="sxs-lookup"><span data-stu-id="bcc19-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="bcc19-116">**Manager** -Verwalter des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="bcc19-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="bcc19-117">Der designierte Manager erhält eine Eskalations Kommunikation für diese Depotbank.</span><span class="sxs-lookup"><span data-stu-id="bcc19-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="bcc19-118">Standortinformationen</span><span class="sxs-lookup"><span data-stu-id="bcc19-118">Location information</span></span>

  - <span data-ttu-id="bcc19-119">**City** – die Stadt, in der sich die Depotbank befindet.</span><span class="sxs-lookup"><span data-stu-id="bcc19-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="bcc19-120">**State** -der Staat oder die Provinz in der Depotbank-Adresse.</span><span class="sxs-lookup"><span data-stu-id="bcc19-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="bcc19-121">**Land/Region** – das Land/die Region, in dem sich die Depotbank befindet.</span><span class="sxs-lookup"><span data-stu-id="bcc19-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="bcc19-122">**Office** – der Office-Standort im Geschäftssitz der Depotbank.</span><span class="sxs-lookup"><span data-stu-id="bcc19-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="bcc19-123">Fall Informationen</span><span class="sxs-lookup"><span data-stu-id="bcc19-123">Case information</span></span>

  - <span data-ttu-id="bcc19-124">**Haltestatus** -gibt an, ob die Depotstelle in die Warteschleife gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc19-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="bcc19-125">**Kommunikationsstatus**: gibt an, ob der Depotbank ein Aufbewahrungs Vermerk ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc19-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="bcc19-126">Wenn der Depotbank eine Benachrichtigung ausgestellt wurde, wird dieser Wert dieser Eigenschaft **veröffentlicht**.</span><span class="sxs-lookup"><span data-stu-id="bcc19-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="bcc19-127">Wenn der Depotbank kein Hinweis erteilt wurde, wird der Status nicht **veröffentlicht**.</span><span class="sxs-lookup"><span data-stu-id="bcc19-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="bcc19-128">**Status** -der Status der Depotbank in der Anfrage.</span><span class="sxs-lookup"><span data-stu-id="bcc19-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="bcc19-129">Der Status **aktiv** gibt an, dass die Depotbank Teil des Falles ist.</span><span class="sxs-lookup"><span data-stu-id="bcc19-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="bcc19-130">Wenn ein depotverwalter von einem Fall freigegeben wird, wird der Status in " **freigegeben**" geändert.</span><span class="sxs-lookup"><span data-stu-id="bcc19-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="bcc19-131">Datenquellen und Indizierungsinformationen</span><span class="sxs-lookup"><span data-stu-id="bcc19-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="bcc19-132">**Datenquellen** : zeigt die Anzahl und den Typ der Datenquellen (Postfächer, Websites und Teams) an, die der Depotbank zugeordnet sind und Teil des Falles sind.</span><span class="sxs-lookup"><span data-stu-id="bcc19-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="bcc19-133">**Index updated Time** -gibt die Uhrzeit und das Datum für den Zeitpunkt an, zu dem der erweiterte Indizierungs Auftrag zuletzt ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc19-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="bcc19-134">Diese Eigenschaft gibt auch an, wann der erweiterte Indizierungsprozess derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bcc19-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="bcc19-135">Bearbeiten einer Depotstelle</span><span class="sxs-lookup"><span data-stu-id="bcc19-135">Edit a custodian</span></span>

<span data-ttu-id="bcc19-136">Wenn Ihr Fall fortschreitet, stellen Sie möglicherweise fest, dass für eine bestimmte Depotbank & Ihrem Fall möglicherweise zusätzliche Datenquellen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="bcc19-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="bcc19-137">In anderen Szenarien möchten Sie möglicherweise bestimmte Datenquellen entfernen, die überprüft und als nicht relevant erachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="bcc19-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="bcc19-138">So aktualisieren Sie die Datenquellen, die einer Depotbank zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="bcc19-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="bcc19-139">Wechseln Sie zu **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="bcc19-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="bcc19-140">Klicken Sie auf die Registerkarte **Quellen** .</span><span class="sxs-lookup"><span data-stu-id="bcc19-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="bcc19-141">Wählen Sie auf der Seite **depotverwalter** eine Depotbank aus der Liste aus, und klicken Sie auf der Flyout-Seite auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="bcc19-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Bearbeiten von Datenquellen](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="bcc19-143">Klicken Sie auf **Datenquellen** Registerkarte auswählen, um die Einstellungen für das Exchange-Postfach und das OneDrive-Konto der Depotbank zu ändern, indem Sie auf **Datenquellen auswählen**klicken.</span><span class="sxs-lookup"><span data-stu-id="bcc19-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="bcc19-144">Klicken Sie auf die Registerkarte **Weitere Datenquellen auswählen** , um Teams, SharePoint-oder Exchange-Postfächer hinzuzufügen oder zu entfernen, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bcc19-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="bcc19-145">Weitere Informationen zu Datenquellen, die einer Depotbank zugeordnet sind, finden Sie unter "Schritt 3: Zuordnen zusätzlicher Datenquellen zu einer Depotbank" unter [Hinzufügen von Depotstellen zu einem Fall](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span><span class="sxs-lookup"><span data-stu-id="bcc19-145">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="bcc19-146">Klicken Sie auf **Depot Platz** Halter, um den Haltebereich für die Depotbank zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bcc19-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="bcc19-147">Erneutes Indizieren von Depotdaten</span><span class="sxs-lookup"><span data-stu-id="bcc19-147">Re-index custodian data</span></span>

<span data-ttu-id="bcc19-148">In den meisten eDiscovery-Workflows für rechtliche Untersuchungen wird eine Teilmenge der Daten eines Depotinhabers durchsucht, nachdem die Depotbank einem Rechtsfall hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc19-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="bcc19-149">Aufgrund sehr großer Dateigrößen oder möglicher Datenbeschädigungen können einige Elemente in den Datenquellen, die einer Depotbank zugeordnet sind, teilweise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="bcc19-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="bcc19-150">Mithilfe der [erweiterten Indizierungs](indexing-custodian-data.md) Funktion in der erweiterten eDiscovery können die meisten teilweise indizierten Elemente automatisch durch Erneutes Indizieren dieser Elemente bei Bedarf behoben werden.</span><span class="sxs-lookup"><span data-stu-id="bcc19-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="bcc19-151">Wenn eine Depotstelle einem Fall hinzugefügt wird, werden die Daten, die sich in den Datenquellen befinden, die der Depotbank zugeordnet sind, automatisch erneut indiziert (durch den erweiterten Indizierungsprozess).</span><span class="sxs-lookup"><span data-stu-id="bcc19-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="bcc19-152">Dies bedeutet, dass Sie die Daten in einem Ort lassen können, anstatt Sie herunterladen und korrigieren und dann offline durchsuchen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="bcc19-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="bcc19-153">Während des Lebenszyklus eines Rechts Falls können neue Datenquellen jedoch einer Depotbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="bcc19-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="bcc19-154">In diesem Fall können Sie die Daten der Depotbank erneut indizieren, indem Sie den erweiterten Indizierungsprozess erneut durchführen, um teilweise indizierte Elemente zu korrigieren und den Index für die Daten der Depotbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bcc19-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="bcc19-155">So lösen Sie den erneuten Indizierungsprozess zum Adressieren von teilweise indizierten Elementen aus:</span><span class="sxs-lookup"><span data-stu-id="bcc19-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="bcc19-156">Wechseln Sie zu **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="bcc19-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="bcc19-157">Klicken Sie auf die Registerkarte **Quellen** .</span><span class="sxs-lookup"><span data-stu-id="bcc19-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="bcc19-158">Wählen Sie auf der Seite **depotverwalter** eine Depotbank aus, deren Daten neu indiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bcc19-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="bcc19-159">Klicken Sie auf der Seite Flyout auf **Index aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="bcc19-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="bcc19-160">Es wird ein Dialogfeld angezeigt, das besagt, dass der Index Auftrag erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc19-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="bcc19-161">Das erneute Indizieren von Depotdaten ist ein langwieriger Prozess; der entsprechende Auftrag, der erstellt wird, wird als **erneute Indizierung von Depotdaten**bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bcc19-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="bcc19-162">Sie können den Fortschritt auf der Registerkarte **Aufträge** oder auf der Registerkarte **depotverwalter** verfolgen, indem Sie den Status in der Spalte **Indizierungs Auftragsstatus** überwachen.</span><span class="sxs-lookup"><span data-stu-id="bcc19-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="bcc19-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bcc19-163">For more information, see:</span></span>

- [<span data-ttu-id="bcc19-164">Arbeiten mit Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="bcc19-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="bcc19-165">Verwalten von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="bcc19-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="bcc19-166">Freigeben einer Depotbank aus einem Fall</span><span class="sxs-lookup"><span data-stu-id="bcc19-166">Release a custodian from a case</span></span>

<span data-ttu-id="bcc19-167">Eine Depotbank wird in Situationen, in denen ein Fall geschlossen wird, freigegeben, die Depotbank ist nicht mehr verpflichtet, Inhalte für einen Fall aufzubewahren oder wenn die Depotbank für den Fall nicht mehr relevant erachtet wird.</span><span class="sxs-lookup"><span data-stu-id="bcc19-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="bcc19-168">Wenn Sie einen depotverwalter freigeben, nachdem ein Aufbewahrungs Bescheid veröffentlicht wurde, wird eine Veröffentlichungs Benachrichtigung an die Depotbank gesendet.</span><span class="sxs-lookup"><span data-stu-id="bcc19-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="bcc19-169">Darüber hinaus werden alle in Datenquellen, die mit der Depotbank verknüpft sind, aufgenommenen Haltestatus entfernt.</span><span class="sxs-lookup"><span data-stu-id="bcc19-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="bcc19-170">Wenn die Depotbank in einem *stillen*Speicherplatz genommen wurde und keine Benachrichtigungen über den rechtlichen Aufbewahrungsplatz ausgestellt wurden, wird keine Veröffentlichungs Benachrichtigung gesendet, aber alle auf Datenquellen, die dieser Depotbank zugeordnet sind, bereitgestellten Haltestatus werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="bcc19-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="bcc19-171">So veröffentlichen Sie eine Depotstelle:</span><span class="sxs-lookup"><span data-stu-id="bcc19-171">To release a custodian:</span></span> 

1. <span data-ttu-id="bcc19-172">Wechseln Sie zu **eDiscovery > Advanced eDiscovery** , und öffnen Sie die Anfrage.</span><span class="sxs-lookup"><span data-stu-id="bcc19-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="bcc19-173">Klicken Sie auf die Registerkarte **Quellen** .</span><span class="sxs-lookup"><span data-stu-id="bcc19-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="bcc19-174">Wählen Sie auf der Seite **depotverwalter** die Depotbank aus, die für den Fall freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bcc19-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="bcc19-175">Klicken Sie auf der Seite Flyout auf **Versionsverwalter**.</span><span class="sxs-lookup"><span data-stu-id="bcc19-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="bcc19-176">Eine Warn Seite wird angezeigt, in der erläutert wird, dass der Haltebereich entfernt wird, wenn ein Haltebereich in einer Datenquelle gespeichert wird, die mit der Depotbank verknüpft ist, und dass alle anderen Halterungen, die einem anderen erweiterten eDiscovery-Fall zugeordnet sind, weiterhin zutreffen.</span><span class="sxs-lookup"><span data-stu-id="bcc19-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="bcc19-177">Dies umfasst andere Arten von Aufbewahrungs-und Aufbewahrungsfunktionen (beispielsweise eine Microsoft 365-Aufbewahrungsrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="bcc19-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="bcc19-178">Klicken Sie auf **Ja** , um zu bestätigen, dass Sie die Depotbank freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="bcc19-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="bcc19-179">Der Status für diesen Benutzer auf der Registerkarte " **Verwalter** " wird auf " **freigegeben** " festgelegt, und der **Aufbewahrungs Status** auf der Flyout-Seite wird auf " **false**" geändert.</span><span class="sxs-lookup"><span data-stu-id="bcc19-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="bcc19-180">Eine Depotbank kann gleichzeitig in mehreren Rechtsfällen beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="bcc19-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="bcc19-181">Wenn ein depotverwalter von einem Fall freigegeben wird, werden die Aufbewahrungs-und Benachrichtigungen in anderen Bereichen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="bcc19-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="bcc19-182">Massenbearbeitung von Depot Betreuern</span><span class="sxs-lookup"><span data-stu-id="bcc19-182">Bulk-edit custodians</span></span>

<span data-ttu-id="bcc19-183">Sie können den Massen-Editor verwenden, um mehrere Verwalter gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bcc19-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="bcc19-184">Wählen Sie dazu einfach mindestens zwei Verwalter auf der Registerkarte **depotverwalter** aus, um den Massen Editor anzuzeigen, und klicken Sie dann auf eine der Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="bcc19-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Flyout-Seite zum Bearbeiten von Einstellungen mehrerer depotverwalter](../media/AeDBulkEditCustodians.png)
