---
title: Hinzufügen nicht verwahrter Datenquellen zu einem Advanced eDiscovery Fall
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
description: Sie können einem fall nicht verwahrten Datenquellen Advanced eDiscovery hinzufügen und die Datenquelle speichern. Nicht verwahrbare Datenquellen werden neu indiziert, sodass alle Inhalte, die als teilweise indiziert markiert wurden, erneut verarbeitet werden, um sie vollständig und schnell durchsuchbar zu machen.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740352"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="ad34e-104">Hinzufügen nicht verwahrter Datenquellen zu einem Advanced eDiscovery Fall</span><span class="sxs-lookup"><span data-stu-id="ad34e-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="ad34e-105">In Advanced eDiscovery erfüllt es nicht immer Ihre Anforderungen, eine Microsoft 365 datenquelle einem Custodian in dem Fall zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="ad34e-106">Möglicherweise müssen Sie diese Daten jedoch einem Fall zuordnen, damit Sie sie durchsuchen, einem Überprüfungssatz hinzufügen und analysieren und überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="ad34e-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="ad34e-107">Das Feature in Advanced eDiscovery wird  als nicht verwahrte Datenquellen bezeichnet und ermöglicht es Ihnen, einem Fall Daten hinzuzufügen, ohne sie einem Verwahrer zuordnen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="ad34e-108">Es wendet auch die Advanced eDiscovery auf nicht verwahrte Daten an, die für Daten verfügbar sind, die mit dem Custodian verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ad34e-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="ad34e-109">Zwei der nützlichsten Dinge, die Sie auf nicht verwahrbare Daten anwenden können, besteht in der Inhaftierung und Verarbeitung dieser Daten mithilfe der [erweiterten Indizierung.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="ad34e-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="ad34e-110">Hinzufügen einer nicht verwahrten Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ad34e-110">Add a non-custodial data source</span></span>

<span data-ttu-id="ad34e-111">Führen Sie die folgenden Schritte aus, um nicht verwahrte Datenquellen in einem Fall hinzuzufügen und Advanced eDiscovery verwalten.</span><span class="sxs-lookup"><span data-stu-id="ad34e-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="ad34e-112">Klicken Sie **Advanced eDiscovery** Startseite auf den Fall, dem Sie die Daten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad34e-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="ad34e-113">Klicken Sie **auf die** Registerkarte Datenquellen, und klicken Sie dann auf Datenquelle **hinzufügen**  >  **Speicherorte hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="ad34e-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="ad34e-114">Wählen Sie **auf** der Flyoutseite Neue nicht verwahrte Datenspeicherorte die Datenquellen aus, die Sie dem Fall hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad34e-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="ad34e-115">Sie können mehrere Postfächer und Websites hinzufügen, indem Sie die SharePoint **oder** **Exchange** erweitern und dann auf **Bearbeiten klicken.**</span><span class="sxs-lookup"><span data-stu-id="ad34e-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Hinzufügen SharePoint Websites und Exchange Postfächern als nicht verwahrte Datenquellen](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="ad34e-117">**SharePoint** – Klicken **Sie auf Bearbeiten,** um Websites hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="ad34e-118">Wählen Sie eine Website in der Liste aus, oder Sie können nach einer Website suchen, indem Sie die URL der Website in die Suchleiste eingeben.</span><span class="sxs-lookup"><span data-stu-id="ad34e-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="ad34e-119">Wählen Sie die Websites aus, die Sie als datenquellenfrei hinzufügen möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ad34e-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="ad34e-120">**Exchange** - Klicken Sie **auf Bearbeiten,** um Postfächer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="ad34e-121">Geben Sie einen Namen oder Alias (mindestens drei Zeichen) in das Suchfeld für Postfächer oder Verteilergruppen ein.</span><span class="sxs-lookup"><span data-stu-id="ad34e-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="ad34e-122">Wählen Sie die Postfächer aus, die Sie als nicht verwahrerische Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ad34e-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ad34e-123">Sie können die Abschnitte **SharePoint** und **Exchange** verwenden, um Websites und Postfächer hinzuzufügen, die einem Team oder einer Yammer-Gruppe als nicht verwahrte Datenquellen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ad34e-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="ad34e-124">Sie müssen das Postfach und die Website, die einem Team oder einer Gruppe zugeordnet sind, Yammer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="ad34e-125">Nachdem Sie nicht verwahrte Datenquellen hinzugefügt haben, haben Sie die Möglichkeit, diese Speicherorte in der Warteschleife zu platzieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ad34e-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="ad34e-126">Aktivieren oder deaktivieren Sie das **Kontrollkästchen Halten** neben der Datenquelle, um es in der Warteschleife zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="ad34e-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="ad34e-127">Klicken **Sie** unten auf der Flyoutseite Neue nicht **verwahrte** Datenspeicherorte auf Hinzufügen, um dem Fall die Datenquellen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="ad34e-128">Jede nicht verwahrte Datenquelle, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad34e-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="ad34e-129">Nicht verwahrte Datenquellen  werden durch den Datenspeicherortwert in der **Spalte Quelltyp** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ad34e-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Nicht verwahrte Datenquellen auf der Registerkarte Datenquellen](../media/NonCustodialDataSources2.png)

<span data-ttu-id="ad34e-131">Nachdem Sie dem Fall nicht verwahrte Datenquellen hinzugefügt haben, wird ein Auftrag mit  dem Namen *Reindexing non-custodial data* erstellt und auf der Registerkarte Aufträge des Falls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad34e-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="ad34e-132">Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiiert und die Datenquellen neu indiziert.</span><span class="sxs-lookup"><span data-stu-id="ad34e-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="ad34e-133">Verwalten des Halteraums für nicht verwahrte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="ad34e-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="ad34e-134">Nachdem Sie eine Nicht-Verwahrer-Datenquelle gespeichert haben, wird automatisch eine Halterichtlinie erstellt, die die nicht verwahrten Datenquellen für den Fall enthält.</span><span class="sxs-lookup"><span data-stu-id="ad34e-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="ad34e-135">Wenn Sie andere nicht verwahrte Datenquellen in der Warteschleife platzieren, werden sie dieser Halterichtlinie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ad34e-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="ad34e-136">Öffnen Sie Advanced eDiscovery Fall, und wählen Sie die Registerkarte **Halten** aus.</span><span class="sxs-lookup"><span data-stu-id="ad34e-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="ad34e-137">Klicken **Sie auf \<GUID\> NCDSHold-**, wobei der GUID-Wert für den Fall eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="ad34e-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="ad34e-138">Auf der Flyoutseite werden Informationen und Statistiken zu nicht verwahrten Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad34e-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![Die Flyoutseite für nicht verwahrte Datenquellen zeigt Statistiken an.](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="ad34e-140">Klicken **Sie auf Halteraum** bearbeiten, um die nicht verwahrbaren Datenquellen zu sehen, die in der Warteschleife gespeichert sind, und führen Sie die folgenden Verwaltungsaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="ad34e-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="ad34e-141">Auf der **Seite Speicherorte** können Sie eine nicht verwahrte Datenquelle los, indem Sie sie aus dem Halteraum entfernen.</span><span class="sxs-lookup"><span data-stu-id="ad34e-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="ad34e-142">Durch das Freigeben einer Datenquelle wird die nicht verwahrte Datenquelle nicht aus dem Fall entfernt.</span><span class="sxs-lookup"><span data-stu-id="ad34e-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="ad34e-143">Es wird nur der Halteraum entfernt, der für die Datenquelle platziert wurde.</span><span class="sxs-lookup"><span data-stu-id="ad34e-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="ad34e-144">Auf der **Seite Abfrage** können Sie den Haltemodus bearbeiten, um einen abfragebasierten Haltemodus zu erstellen, der in diesem Fall auf alle nicht verwahrbaren Datenquellen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad34e-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
