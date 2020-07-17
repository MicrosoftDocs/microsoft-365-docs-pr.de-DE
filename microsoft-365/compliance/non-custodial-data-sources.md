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
description: Sie können einem erweiterten eDiscovery-Fall Datenquellen ohne Freiheitsentzug hinzufügen und die Datenquelle aufbewahren. Datenquellen ohne Freiheitsentzug werden neu indiziert, sodass alle Inhalte, die als teilweise indiziert betrachtet wurden, neu verarbeitet werden, damit Sie vollständig und schnell durchsuchbar sind.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024745"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="033c8-104">Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="033c8-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="033c8-105">In erweiterten eDiscovery-Fällen erfüllt es nicht immer Ihre Anforderungen, um eine Microsoft 365-Datenquelle mit einer Depotbank in dem Fall zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="033c8-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="033c8-106">Möglicherweise müssen Sie diese Daten jedoch dennoch einem Fall zuordnen, damit Sie Sie durchsuchen, Sie zu Überprüfungs Sätzen hinzufügen und überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="033c8-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="033c8-107">Mit dem neuen Feature " *nicht-Freiheits geschützte Datenquellen* " können Sie Daten zu einem Fall hinzufügen, ohne die Daten einer Depotbank zuordnen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="033c8-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="033c8-108">Sie wendet auch die gleiche erweiterte eDiscovery-Funktionalität auf nicht-Freiheitsentzug-Daten an, die für mit der Depotbank verbundene Daten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="033c8-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="033c8-109">Zwei der nützlichsten Funktionen, die Sie auf Daten ohne Freiheitsentzug anwenden können, sind das aufbewahren und das verarbeiten mit der [erweiterten Indizierung](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="033c8-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="033c8-110">Hinzufügen einer Datenquelle ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="033c8-110">Add a non-custodial data source</span></span>

<span data-ttu-id="033c8-111">Führen Sie die folgenden Schritte aus, um Datenquellen ohne Freiheitsentzug in einem erweiterten eDiscovery-Fall hinzuzufügen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="033c8-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="033c8-112">Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf den Fall, dem Sie die Daten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="033c8-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="033c8-113">Klicken Sie auf der Seite **Quellen** auf die Registerkarte **Datenspeicherorte** , und klicken Sie dann auf **Datenspeicherort hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="033c8-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="033c8-114">Klicken Sie auf **Datenspeicherort hinzufügen** , und wählen Sie die Datenquellen aus, die der Anfrage hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="033c8-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="033c8-115">Sie können mehrere Postfächer und Websites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="033c8-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="033c8-116">Fügen Sie auf der Seite **Speicherorte auswählen** des Assistenten Postfächer oder Websites (oder beides) als Datenquellen ohne Freiheitsentzug für den Fall hinzu.</span><span class="sxs-lookup"><span data-stu-id="033c8-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="033c8-117">Klicken Sie nach dem Hinzufügen der Datenquellen auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="033c8-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="033c8-118">Wählen Sie auf der Seite **Platz Haltestatus** die Datenquellen aus, die Sie speichern möchten, indem Sie das zugehörige Kontrollkästchen auswählen oder aufheben.</span><span class="sxs-lookup"><span data-stu-id="033c8-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="033c8-119">Überprüfen Sie die Aufbewahrungsoptionen, und klicken Sie dann auf **senden**.</span><span class="sxs-lookup"><span data-stu-id="033c8-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="033c8-120">Jede Datenquelle ohne Freiheits Schutz, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="033c8-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="033c8-121">Außerdem wird ein Auftrag mit dem Namen " *Neuindizieren von Daten ohne Freiheitsentzug* " erstellt und auf der Registerkarte " **Aufträge** " der Groß-/Kleinschreibung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="033c8-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="033c8-122">Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiiert und die Datenquellen neu indiziert.</span><span class="sxs-lookup"><span data-stu-id="033c8-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="033c8-123">Verwalten der Aufbewahrungszeit für Datenquellen ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="033c8-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="033c8-124">Nachdem Sie eine Datenquelle ohne Freiheitsentzug gespeichert haben, wird automatisch eine Aufbewahrungsrichtlinie erstellt, die alle Datenquellen ohne Freiheits Schutz für den Fall enthält.</span><span class="sxs-lookup"><span data-stu-id="033c8-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="033c8-125">Wenn Sie zusätzliche Datenquellen ohne Freiheitsentzug speichern, werden Sie dieser Aufbewahrungsrichtlinie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="033c8-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="033c8-126">Klicken Sie auf der **Start** Seite der Anfrage auf die Registerkarte halte **Status** .</span><span class="sxs-lookup"><span data-stu-id="033c8-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="033c8-127">Auf der Seite halte **Status** , und klicken Sie auf \*\*NCDSHold- \<GUID\> \*\*, wobei der GUID-Wert für den Fall eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="033c8-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="033c8-128">Klicken Sie auf der Flyout-Seite auf **Haltestatus bearbeiten** , um alle Datenquellen ohne Freiheitsentzug anzuzeigen, die in der Warteschleife gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="033c8-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="033c8-129">Sie können die folgende Verwaltungsaufgabe für Datenquellen ohne Freiheitsentzug ausführen:</span><span class="sxs-lookup"><span data-stu-id="033c8-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="033c8-130">Sie können den Haltebereich bearbeiten, um einen abfragebasierten Haltebereich zu erstellen, der für alle Datenquellen ohne Freiheitsentzug in dem Fall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="033c8-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="033c8-131">Sie können eine Datenquelle ohne Freiheitsentzug aus dem Haltestatus freigeben.</span><span class="sxs-lookup"><span data-stu-id="033c8-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="033c8-132">Durch das Freigeben einer Datenquelle wird nicht die Datenquelle ohne Freiheitsentzug aus dem Fall entfernt.</span><span class="sxs-lookup"><span data-stu-id="033c8-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="033c8-133">Es entfernt nur den Haltebereich, der in der Datenquelle eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="033c8-133">It only removes the hold that was placed on the data source.</span></span>
