---
title: Informationen zur eDiscovery-Erfahrung während der Migration aus Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: eDiscovery-Migrationsschritte für die Migration aus Microsoft Cloud Deutschland'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844250"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="52791-103">Informationen zur eDiscovery-Erfahrung während der Migration aus Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="52791-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="52791-104">Die folgenden Abschnitte enthalten zusätzliche Informationen zur eDiscovery-Erfahrung beim Wechsel aus Microsoft Cloud Deutschland zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.</span><span class="sxs-lookup"><span data-stu-id="52791-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="52791-105">eDiscovery-Verwaltung bis Phase 4</span><span class="sxs-lookup"><span data-stu-id="52791-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="52791-106">Bis Phase 4 ist das Security & Compliance Center vollständig verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52791-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="52791-107">Alle Inhalte bleiben in der Microsoft Cloud Deutschland und können über das Microsoft Cloud Deutschland Security & Compliance Center (https://protection.office.de/) verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="52791-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="52791-108">eDiscovery-Erfahrung zwischen Phase 4 und Abschluss von Phase 9</span><span class="sxs-lookup"><span data-stu-id="52791-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="52791-109">Von Beginn von Phase 4 bis zum Abschluss von Phase 9 schlagen eDiscovery-Suchen fehl oder geben 0 (null) Ergebnisse für SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte zurück, die migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="52791-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="52791-110">Während der Migration können Kunden weiterhin Fälle, Archive, Suchvorgänge und Exporte im [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations) erstellen, einschließlich [Inhaltssuche](/microsoft-365/compliance/search-for-content).</span><span class="sxs-lookup"><span data-stu-id="52791-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="52791-111">Bei Suchvorgängen in SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorten, die migriert wurden, werden jedoch entweder 0 Ergebnisse oder ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52791-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="52791-112">Für den Fall, dass eine Suche 0 (null) Ergebnisse oder einen Fehler während der Migration zurückgibt, sollten Sie die folgende Aktion für SharePoint Online ausführen:</span><span class="sxs-lookup"><span data-stu-id="52791-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="52791-113">Laden Sie Websites direkt von der SharePoint Online- oder OneDrive for Business-Website herunter, indem Sie die Anweisungen in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) befolgen.</span><span class="sxs-lookup"><span data-stu-id="52791-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="52791-114">Für diese Methode sind SharePoint Online-Administratorberechtigungen oder Nur-Lesen-Berechtigungen auf der Website erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52791-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="52791-115">Wenn Limits überschritten werden, wie in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) erläutert wird, können Kunden den OneDrive for Business-Synchronisierungsclient verwenden, indem sie den Anweisungen unter [Synchronisieren von SharePoint- und Team Dateien mit Ihrem Computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) folgen.</span><span class="sxs-lookup"><span data-stu-id="52791-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="52791-116">Weitere Informationen finden Sie unter [In-Situ-eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span><span class="sxs-lookup"><span data-stu-id="52791-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="52791-117">eDiscovery-Verwaltung nach Phase 9</span><span class="sxs-lookup"><span data-stu-id="52791-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="52791-118">**Gilt für:** Alle Kunden, die eDiscovery verwenden</span><span class="sxs-lookup"><span data-stu-id="52791-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="52791-119">In Phase 9 werden die letzten Schritte für den Wechsel in die neue deutsche Rechenzentrumsregion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52791-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="52791-120">In dieser Phase werden alle verbleibenden Dienstkomponenten migriert.</span><span class="sxs-lookup"><span data-stu-id="52791-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="52791-121">Nach Phase 9 wird die Verwendung des Security & Compliance Centers in der Microsoft Cloud Deutschland (protection.office.de) nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52791-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="52791-122">Verwenden Sie stattdessen das neue [Security Center](https://security.microsoft.com/) oder [Compliance Center](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="52791-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="52791-123">Alle Daten wurden in die neuen Verwaltungsportale übertragen.</span><span class="sxs-lookup"><span data-stu-id="52791-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="52791-124">Schritte:</span><span class="sxs-lookup"><span data-stu-id="52791-124">Step(s)</span></span> | <span data-ttu-id="52791-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52791-125">Description</span></span> | <span data-ttu-id="52791-126">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="52791-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="52791-127">Alle SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte wurden zusammen mit dem Security and Compliance Center (SCC) migriert.</span><span class="sxs-lookup"><span data-stu-id="52791-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="52791-128">Alle eDiscovery-Aktivitäten sollten vom weltweiten Mandanten aus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52791-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="52791-129">Suchvorgänge sind jetzt zu 100 % erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="52791-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="52791-130">Alle Fehler oder Ausfälle sollten normalen Supportkanälen folgen.</span><span class="sxs-lookup"><span data-stu-id="52791-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="52791-131">Keine</span><span class="sxs-lookup"><span data-stu-id="52791-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="52791-132">eDiscovery-Aufbewahrungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="52791-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="52791-133">**Gilt für:** Alle Kunden, die eine Aufbewahrungsrichtlinie im Rahmen der Schritte vor der Migration angewendet haben</span><span class="sxs-lookup"><span data-stu-id="52791-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="52791-134">Schritte:</span><span class="sxs-lookup"><span data-stu-id="52791-134">Step(s)</span></span> | <span data-ttu-id="52791-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52791-135">Description</span></span> | <span data-ttu-id="52791-136">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="52791-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="52791-137">Entfernen organisationsweiter Aufbewahrungsrichtlinien, die während der Schritte vor der Migration erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="52791-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="52791-138">Kunden können die organisationsweiten Aufbewahrungsrichtlinien entfernen, die während der Arbeit der Kunden vor der Migration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="52791-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="52791-139">Keine</span><span class="sxs-lookup"><span data-stu-id="52791-139">None</span></span> |
||||
