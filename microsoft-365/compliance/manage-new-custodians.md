---
title: Verwalten von Verwahrern in einem Advanced eDiscovery Fall
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
description: Erfahren Sie, wie Sie Details anzeigen, bearbeiten und die Liste der Verwahrer in einem Advanced eDiscovery bearbeiten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739868"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="eaf82-103">Verwalten von Verwahrern in einem Advanced eDiscovery Fall</span><span class="sxs-lookup"><span data-stu-id="eaf82-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="eaf82-104">Die Seite Custodians auf der Registerkarte **Quellen** in einem Advanced eDiscovery enthält eine Liste aller Verwahrer, die dem Fall hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="eaf82-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="eaf82-105">Nachdem Sie einem Fall Custodians hinzugefügt haben, werden Details zu jedem Custodian automatisch von Azure Active Directory erfasst und in der Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="eaf82-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Verwalten von Verwahrern](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="eaf82-107">Anzeigen von Verwahrerdetails</span><span class="sxs-lookup"><span data-stu-id="eaf82-107">View custodian details</span></span>

<span data-ttu-id="eaf82-108">Klicken Sie auf der Registerkarte Verwahrer auf der Liste auf den Custodian, um die Details zu einem **Custodian anzuzeigen.** Eine Flyoutseite wird angezeigt und enthält die folgenden Informationen zum Verwahrer:</span><span class="sxs-lookup"><span data-stu-id="eaf82-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="eaf82-109">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="eaf82-109">Contact information</span></span>

  - <span data-ttu-id="eaf82-110">**Anzeigename** – Der Name, der im Adressbuch für den Verwahrer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eaf82-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="eaf82-111">Dies ist in der Regel die Kombination aus Vorname, Vorname und Nachname des Verwahrers.</span><span class="sxs-lookup"><span data-stu-id="eaf82-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="eaf82-112">**Mail/SMTP** – Die primäre SMTP-Adresse für den Verwahrer, z. B. brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="eaf82-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="eaf82-113">Der Benutzerprinzipalname (User Principal Name, UPN) des Custodians wird ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eaf82-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="eaf82-114">**Titel** – Der Auftragstitel des Verwahrers.</span><span class="sxs-lookup"><span data-stu-id="eaf82-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="eaf82-115">**Abteilung** – Der Name der Abteilung, in der der Verwahrer arbeitet.</span><span class="sxs-lookup"><span data-stu-id="eaf82-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="eaf82-116">**Manager** – Der Vorgesetzte des Verwalters.</span><span class="sxs-lookup"><span data-stu-id="eaf82-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="eaf82-117">Der designierte Manager erhält jegliche Eskalationskommunikation für diesen Verwalter.</span><span class="sxs-lookup"><span data-stu-id="eaf82-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="eaf82-118">Standortinformationen</span><span class="sxs-lookup"><span data-stu-id="eaf82-118">Location information</span></span>

  - <span data-ttu-id="eaf82-119">**City** – Die Stadt, in der sich der Custodian befindet.</span><span class="sxs-lookup"><span data-stu-id="eaf82-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="eaf82-120">**Bundesland** – Das Bundesland oder die Provinz in der Adresse des Verwahrers.</span><span class="sxs-lookup"><span data-stu-id="eaf82-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="eaf82-121">**Land/Region** – Das Land/die Region, in dem sich der Custodian befindet.</span><span class="sxs-lookup"><span data-stu-id="eaf82-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="eaf82-122">**Office** – Der Bürostandort am Geschäftssitz des Verwahrers.</span><span class="sxs-lookup"><span data-stu-id="eaf82-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="eaf82-123">Fallinformationen</span><span class="sxs-lookup"><span data-stu-id="eaf82-123">Case information</span></span>

  - <span data-ttu-id="eaf82-124">**Haltestatus** – Gibt an, ob der Custodian in der Warteschleife platziert wurde.</span><span class="sxs-lookup"><span data-stu-id="eaf82-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="eaf82-125">**Kommunikationsstatus**: Gibt an, ob der Custodian eine Haltebenachrichtigung erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="eaf82-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="eaf82-126">Wenn der Verwahrer eine Benachrichtigung erhalten hat, wird dieser Wert dieser Eigenschaft **veröffentlicht**.</span><span class="sxs-lookup"><span data-stu-id="eaf82-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="eaf82-127">Wenn der Verwahrer keine Benachrichtigung erhalten hat, ist der Status **Un-published**.</span><span class="sxs-lookup"><span data-stu-id="eaf82-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="eaf82-128">**Status** – Der Status des Verwahrers innerhalb des Falls.</span><span class="sxs-lookup"><span data-stu-id="eaf82-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="eaf82-129">Der Status **Active** gibt an, dass der Verwahrer Teil des Falls ist.</span><span class="sxs-lookup"><span data-stu-id="eaf82-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="eaf82-130">Wenn ein Verwahrer aus einem Fall freigelassen wird, wird der Status in **Freigegeben geändert.**</span><span class="sxs-lookup"><span data-stu-id="eaf82-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="eaf82-131">Datenquellen und Indizierungsinformationen</span><span class="sxs-lookup"><span data-stu-id="eaf82-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="eaf82-132">**Datenquellen** – Zeigt die Anzahl und den Typ der Datenquellen (Postfächer, Websites und Teams) an, die dem Custodian zugeordnet sind und Teil des Falls sind.</span><span class="sxs-lookup"><span data-stu-id="eaf82-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="eaf82-133">**Index updated time** – Gibt die Uhrzeit und das Datum an, an dem der erweiterte Indizierungsauftrag zuletzt ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="eaf82-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="eaf82-134">Diese Eigenschaft gibt auch an, wann der erweiterte Indizierungsprozess gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaf82-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="eaf82-135">Bearbeiten eines Verwahrers</span><span class="sxs-lookup"><span data-stu-id="eaf82-135">Edit a custodian</span></span>

<span data-ttu-id="eaf82-136">Wenn Ihr Fall fortschreitet, stellen Sie möglicherweise fest, dass es zusätzliche Datenquellen gibt, die für einen bestimmten Verwahrer & fall relevant sind.</span><span class="sxs-lookup"><span data-stu-id="eaf82-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="eaf82-137">In anderen Szenarien möchten Sie möglicherweise bestimmte Datenquellen entfernen, die überprüft wurden und als nicht relevant eingestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="eaf82-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="eaf82-138">So aktualisieren Sie die Datenquellen, die einem Custodian zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="eaf82-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="eaf82-139">Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.</span><span class="sxs-lookup"><span data-stu-id="eaf82-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="eaf82-140">Klicken Sie auf **die Registerkarte** Quellen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="eaf82-141">Wählen Sie **auf der Seite** Verwahrer in der Liste einen Custodian aus, und klicken Sie auf der Flyoutseite auf Bearbeiten. </span><span class="sxs-lookup"><span data-stu-id="eaf82-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Bearbeiten von Datenquellen](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="eaf82-143">Klicken **Sie auf** Die Registerkarte Datenquellen auswählen, um die Einstellungen für das Exchange und OneDrive zu ändern, klicken Sie auf **Datenquellen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="eaf82-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="eaf82-144">Klicken Sie auf die Registerkarte Zusätzliche **Datenquellen** auswählen, um dem Custodian zugeordnete Teams, SharePoint oder Exchange hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="eaf82-145">Weitere Informationen zu Datenquellen, die einem Verwahrer zugeordnet sind, finden Sie unter [Hinzufügen von Verwahrern zu einem Fall](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="eaf82-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="eaf82-146">Klicken **Sie auf Verwahrer platzieren,** um den Halteraum für den Verwahrer zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eaf82-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="eaf82-147">Erneutes Indizieren von Daten des Verwahrers</span><span class="sxs-lookup"><span data-stu-id="eaf82-147">Re-index custodian data</span></span>

<span data-ttu-id="eaf82-148">In den meisten eDiscovery-Workflows für juristische Untersuchungen wird eine Teilmenge der Daten eines Verwahrers durchsucht, nachdem der Custodian einem Rechtsstreit hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="eaf82-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="eaf82-149">Aufgrund sehr großer Dateigrößen oder möglicher Datenbeschädigungen können einige Elemente in den einem Custodian zugeordneten Datenquellen teilweise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="eaf82-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="eaf82-150">Mithilfe der [erweiterten](indexing-custodian-data.md) Indizierungsfunktion im Advanced eDiscovery können die meisten teilweise indizierten Elemente automatisch behoben werden, indem diese Elemente bei Bedarf erneut indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="eaf82-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="eaf82-151">Wenn einem Fall ein Verwahrer hinzugefügt wird, werden die Daten in den datenquellen, die dem Custodian zugeordnet sind, automatisch neu indiziert (durch den erweiterten Indizierungsprozess).</span><span class="sxs-lookup"><span data-stu-id="eaf82-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="eaf82-152">Dies bedeutet, dass Sie die Daten direkt lassen können, anstatt sie herunterzuladen und zu repakieren und dann offline zu durchsuchen).</span><span class="sxs-lookup"><span data-stu-id="eaf82-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="eaf82-153">Während des Lebenszyklus eines Rechtsstreits können jedoch neue Datenquellen einem Verwahrer zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eaf82-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="eaf82-154">In diesem Fall können Sie die Daten des Verwahrers neu indizieren, indem Sie den erweiterten Indizierungsprozess erneut ausführen, um teilweise indizierte Elemente zu re-indizieren und den Index für die Daten des Custodians zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eaf82-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="eaf82-155">So lösen Sie den Erneutindizierungsprozess aus, um teilweise indizierte Elemente zu adressieren:</span><span class="sxs-lookup"><span data-stu-id="eaf82-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="eaf82-156">Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.</span><span class="sxs-lookup"><span data-stu-id="eaf82-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="eaf82-157">Klicken Sie auf **die Registerkarte** Quellen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="eaf82-158">Wählen Sie **auf der Seite** Verwahrer einen Custodian aus, dessen Daten neu indiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="eaf82-159">Klicken Sie auf der Flyoutseite auf **Index aktualisieren.**</span><span class="sxs-lookup"><span data-stu-id="eaf82-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="eaf82-160">Es wird ein Dialogfeld mit der Meldung angezeigt, dass der Indexauftrag erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="eaf82-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="eaf82-161">Die erneute Indizierung von Daten von Verwahrer ist ein langer Prozess. Der entsprechende auftrag, der erstellt wird, heißt **Re-indexing custodian data**.</span><span class="sxs-lookup"><span data-stu-id="eaf82-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="eaf82-162">Sie können den Fortschritt auf der  Registerkarte **Aufträge** oder auf der Registerkarte Verwahrer nachverfolgen, indem Sie den Status in der Spalte **Auftragsstatus indizieren** überwachen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="eaf82-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="eaf82-163">For more information, see:</span></span>

- [<span data-ttu-id="eaf82-164">Arbeiten mit Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="eaf82-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="eaf82-165">Verwalten von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="eaf82-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="eaf82-166">Freigabe eines Verwahrers aus einem Fall</span><span class="sxs-lookup"><span data-stu-id="eaf82-166">Release a custodian from a case</span></span>

<span data-ttu-id="eaf82-167">Ein Verwahrer wird in Situationen freigelassen, in denen ein Fall geschlossen wird, der Custodian nicht mehr verpflichtet ist, Inhalte für einen Fall zu bewahren, oder wenn der Custodian als nicht mehr relevant für den Fall angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="eaf82-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="eaf82-168">Wenn Sie einen Verwahrer nach der Veröffentlichung einer Haltebenachrichtigung frei lassen, wird eine Veröffentlichungsbenachrichtigung an den Verwahrer gesendet.</span><span class="sxs-lookup"><span data-stu-id="eaf82-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="eaf82-169">Darüber hinaus werden alle halte für Datenquellen, die dem Custodian zugeordnet waren, entfernt.</span><span class="sxs-lookup"><span data-stu-id="eaf82-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="eaf82-170">Wenn der Verwahrer in einem stillen Halterecht platziert wurde *und* keine Benachrichtigungen über das gesetzliche Halterecht ausgestellt wurden, wird keine Veröffentlichungsbenachrichtigung gesendet, aber alle halte, die für Datenquellen, die diesem Custodian zugeordnet waren, platziert wurden, werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="eaf82-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="eaf82-171">So lassen Sie einen Verwahrer frei:</span><span class="sxs-lookup"><span data-stu-id="eaf82-171">To release a custodian:</span></span> 

1. <span data-ttu-id="eaf82-172">Wechseln Sie **zu eDiscovery > Advanced eDiscovery,** und öffnen Sie den Fall.</span><span class="sxs-lookup"><span data-stu-id="eaf82-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="eaf82-173">Klicken Sie auf **die Registerkarte** Quellen.</span><span class="sxs-lookup"><span data-stu-id="eaf82-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="eaf82-174">Wählen Sie **auf der Seite** Verwahrer den Custodian aus, der aus dem Fall freigelassen wird.</span><span class="sxs-lookup"><span data-stu-id="eaf82-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="eaf82-175">Klicken Sie auf der Flyoutseite auf **Custodian los.**</span><span class="sxs-lookup"><span data-stu-id="eaf82-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="eaf82-176">Es wird eine Warnseite angezeigt, auf der erklärt wird, dass bei einem Halterecht für eine Datenquelle, die dem Custodian zugeordnet ist, der Halteraum entfernt wird und dass ein anderer Halteraum, der einem anderen Advanced eDiscovery-Fall zugeordnet ist, weiterhin gilt.</span><span class="sxs-lookup"><span data-stu-id="eaf82-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="eaf82-177">Dies umfasst andere Arten von Erhaltungs- und Aufbewahrungsfeatures (z. B. Microsoft 365 Aufbewahrungsrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="eaf82-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="eaf82-178">Klicken **Sie auf Ja,** um zu bestätigen, dass Sie den Custodian los lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="eaf82-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="eaf82-179">Der Status für diesen  Benutzer auf der Registerkarte  Verwahrer ist auf **Freigegeben** festgelegt, und der Haltestatus auf der Flyoutseite wird in **False geändert.**</span><span class="sxs-lookup"><span data-stu-id="eaf82-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="eaf82-180">Ein Verwahrer kann gleichzeitig an mehreren Rechtsfällen beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="eaf82-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="eaf82-181">Wenn ein Verwahrer aus einem Fall freigelassen wird, werden die Halte- und Benachrichtigungen in anderen Fällen nicht betroffen sein.</span><span class="sxs-lookup"><span data-stu-id="eaf82-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="eaf82-182">Massenbearbeitung von Verwahrern</span><span class="sxs-lookup"><span data-stu-id="eaf82-182">Bulk-edit custodians</span></span>

<span data-ttu-id="eaf82-183">Sie können den Masseneditor verwenden, um mehrere Custodians gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eaf82-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="eaf82-184">Wählen Sie dazu auf der Registerkarte Custodians nur zwei oder mehr **Custodians** aus, um den Masseneditor anzeigen zu können, und klicken Sie dann auf eine der Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="eaf82-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Flyoutseite zum Bearbeiten von Einstellungen mehrerer Custodians](../media/AeDBulkEditCustodians.png)
