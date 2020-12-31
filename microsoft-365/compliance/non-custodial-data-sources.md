---
title: Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall
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
description: Sie können einem erweiterten eDiscovery-Fall Datenquellen ohne Freiheitsentzug hinzufügen und die Datenquelle aufbewahren. Datenquellen ohne Freiheitsentzug werden neu indiziert, sodass alle Inhalte, die als teilweise indiziert markiert wurden, neu verarbeitet werden, damit Sie vollständig und schnell durchsuchbar sind.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740352"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="df4e8-104">Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="df4e8-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="df4e8-105">In erweiterten eDiscovery-Fällen erfüllt es nicht immer Ihre Anforderungen, um eine Microsoft 365-Datenquelle mit einer Depotbank in dem Fall zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="df4e8-106">Möglicherweise müssen Sie diese Daten aber dennoch einem Fall zuordnen, damit Sie Sie durchsuchen, zu einem Überprüfungs Satzes hinzufügen und analysieren und überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="df4e8-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="df4e8-107">Das Feature in Advanced eDiscovery wird als *nicht-Freiheits Zeichen-Datenquellen* bezeichnet und ermöglicht es Ihnen, einem Fall Daten hinzuzufügen, ohne ihn einer Depotbank zuordnen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="df4e8-108">Sie wendet auch die gleiche erweiterte eDiscovery-Funktionalität auf nicht-Freiheitsentzug-Daten an, die für mit der Depotbank verbundene Daten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="df4e8-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="df4e8-109">Zwei der nützlichsten Dinge, die Sie auf Daten ohne Freiheitsentzug anwenden können, sind das aufbewahren und das verarbeiten mit der [erweiterten Indizierung](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="df4e8-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="df4e8-110">Hinzufügen einer Datenquelle ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="df4e8-110">Add a non-custodial data source</span></span>

<span data-ttu-id="df4e8-111">Führen Sie die folgenden Schritte aus, um Datenquellen ohne Freiheitsentzug in einem erweiterten eDiscovery-Fall hinzuzufügen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="df4e8-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="df4e8-112">Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf den Fall, dem Sie die Daten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="df4e8-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="df4e8-113">Klicken Sie auf die Registerkarte **Datenquellen** , und klicken Sie dann auf Daten **Quelle** Hinzufügen von  >  **Datenspeicherorten**.</span><span class="sxs-lookup"><span data-stu-id="df4e8-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="df4e8-114">Wählen Sie auf der Seite Neues Flyout für **Datenspeicherorte ohne Freiheits** Zeichen die Datenquellen aus, die Sie der Anfrage hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="df4e8-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="df4e8-115">Sie können mehrere Postfächer und Websites hinzufügen, indem Sie die **SharePoint** -oder **Exchange** -Abschnitte erweitern und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="df4e8-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Hinzufügen von SharePoint-Websites und Exchange-Postfächern zu Datenquellen ohne Freiheitsentzug](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="df4e8-117">**SharePoint** – klicken Sie auf **Bearbeiten** , um Websites hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="df4e8-118">Wählen Sie eine Website in der Liste aus, oder suchen Sie nach einer Website, indem Sie die URL der Website in die Suchleiste eingeben.</span><span class="sxs-lookup"><span data-stu-id="df4e8-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="df4e8-119">Wählen Sie die Websites aus, die Sie als nicht-Depotbank-Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="df4e8-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="df4e8-120">**Exchange** – klicken Sie auf **Bearbeiten** , um Postfächer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="df4e8-121">Geben Sie einen Namen oder einen Alias (mindestens drei Zeichen) für Postfächer oder Verteilergruppen in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="df4e8-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="df4e8-122">Wählen Sie die Postfächer aus, die Sie als nicht-Depotbank-Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="df4e8-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="df4e8-123">Sie können die **SharePoint** -und **Exchange** -Abschnitte zum Hinzufügen von Websites und Postfächern verwenden, die einem Team oder einer Gruppe "jammern" als Datenquellen ohne Freiheitsentzug zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="df4e8-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="df4e8-124">Sie müssen das Postfach und die Website, die einem Team oder einer Gruppe von jammern zugeordnet sind, separat hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="df4e8-125">Nachdem Sie Datenquellen ohne Freiheitsentzug hinzugefügt haben, haben Sie die Möglichkeit, diese Speicherorte in der Warteschleife zu platzieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="df4e8-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="df4e8-126">Aktivieren oder deaktivieren Sie das Kontrollkästchen **halten** neben der Datenquelle, um es in die Warteschleife zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="df4e8-127">Klicken Sie unten auf der Flyout-Seite für **neue Datenspeicherorte ohne Freiheitsentzug** auf **Hinzufügen** , um die Datenquellen dem Fall hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="df4e8-128">Jede Datenquelle ohne Freiheits Schutz, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="df4e8-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="df4e8-129">Datenquellen ohne Freiheitsentzug werden durch den Wert **Datenspeicherort** in der Spalte **Quelltyp** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="df4e8-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Datenquellen ohne Freiheitsentzug auf der Registerkarte Datenquellen](../media/NonCustodialDataSources2.png)

<span data-ttu-id="df4e8-131">Nachdem Sie dem Fall Datenquellen ohne Freiheitsentzug hinzugefügt haben, wird ein Auftrag mit dem Namen " *Neuindizieren von nicht-Freiheitsentzug-Daten* " erstellt und auf der Registerkarte " **Aufträge** " der Groß-/Kleinschreibung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df4e8-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="df4e8-132">Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiiert und die Datenquellen neu indiziert.</span><span class="sxs-lookup"><span data-stu-id="df4e8-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="df4e8-133">Verwalten der Aufbewahrungszeit für Datenquellen ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="df4e8-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="df4e8-134">Nachdem Sie eine Datenquelle ohne Freiheitsentzug gespeichert haben, wird automatisch eine Aufbewahrungsrichtlinie erstellt, die die Datenquellen ohne Freiheits Schutz für den Fall enthält.</span><span class="sxs-lookup"><span data-stu-id="df4e8-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="df4e8-135">Wenn Sie andere Datenquellen ohne Freiheitsentzug in die Warteschleife setzen, werden Sie dieser Aufbewahrungsrichtlinie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="df4e8-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="df4e8-136">Öffnen Sie den erweiterten eDiscovery-Fall, und wählen Sie die Registerkarte **halten** aus.</span><span class="sxs-lookup"><span data-stu-id="df4e8-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="df4e8-137">Klicken Sie auf **NCDSHold- \<GUID\>**, wobei der GUID-Wert für den Fall eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="df4e8-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="df4e8-138">Auf der Flyout-Seite werden Informationen und Statistiken zu den nicht-Freiheits geschützten Datenquellen in der Warteschleife angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df4e8-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![Die Flyout-Seite für Datenquellen ohne Freiheitsentzug zeigt Statistiken an](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="df4e8-140">Klicken Sie auf Speicher **Bearbeiten** , um die Datenquellen ohne Freiheitsentzug anzuzeigen, die in der Warteschleife gespeichert sind, und führen Sie die folgenden Verwaltungsaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="df4e8-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="df4e8-141">Auf der Seite **Speicherorte** können Sie eine Datenquelle ohne Freiheitsentzug freigeben, indem Sie Sie aus dem Haltestatus entfernen.</span><span class="sxs-lookup"><span data-stu-id="df4e8-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="df4e8-142">Durch das Freigeben einer Datenquelle wird nicht die Datenquelle ohne Freiheitsentzug aus dem Fall entfernt.</span><span class="sxs-lookup"><span data-stu-id="df4e8-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="df4e8-143">Es entfernt nur den Haltebereich, der in der Datenquelle eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="df4e8-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="df4e8-144">Auf der Seite **Abfrage** können Sie den Haltebereich bearbeiten, um einen abfragebasierten Haltebereich zu erstellen, der auf alle Tha-nicht-Freiheits Zeichen-Datenquellen in dem Fall angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="df4e8-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
