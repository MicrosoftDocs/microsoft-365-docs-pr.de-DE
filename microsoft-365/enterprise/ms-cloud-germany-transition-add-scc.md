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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844250"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Informationen zur eDiscovery-Erfahrung während der Migration aus Microsoft Cloud Deutschland
Die folgenden Abschnitte enthalten zusätzliche Informationen zur eDiscovery-Erfahrung beim Wechsel aus Microsoft Cloud Deutschland zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.

## <a name="ediscovery-administration-until-phase-4"></a>eDiscovery-Verwaltung bis Phase 4
Bis Phase 4 ist das Security & Compliance Center vollständig verfügbar. Alle Inhalte bleiben in der Microsoft Cloud Deutschland und können über das Microsoft Cloud Deutschland Security & Compliance Center (https://protection.office.de/) verwaltet werden.

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>eDiscovery-Erfahrung zwischen Phase 4 und Abschluss von Phase 9
Von Beginn von Phase 4 bis zum Abschluss von Phase 9 schlagen eDiscovery-Suchen fehl oder geben 0 (null) Ergebnisse für SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte zurück, die migriert wurden.

> [!NOTE]
> Während der Migration können Kunden weiterhin Fälle, Archive, Suchvorgänge und Exporte im [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations) erstellen, einschließlich [Inhaltssuche](/microsoft-365/compliance/search-for-content). Bei Suchvorgängen in SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorten, die migriert wurden, werden jedoch entweder 0 Ergebnisse oder ein Fehler zurückgegeben.

Für den Fall, dass eine Suche 0 (null) Ergebnisse oder einen Fehler während der Migration zurückgibt, sollten Sie die folgende Aktion für SharePoint Online ausführen:

- Laden Sie Websites direkt von der SharePoint Online- oder OneDrive for Business-Website herunter, indem Sie die Anweisungen in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) befolgen. Für diese Methode sind SharePoint Online-Administratorberechtigungen oder Nur-Lesen-Berechtigungen auf der Website erforderlich.
- Wenn Limits überschritten werden, wie in [Herunterladen von Dateien und Ordnern aus OneDrive oder SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) erläutert wird, können Kunden den OneDrive for Business-Synchronisierungsclient verwenden, indem sie den Anweisungen unter [Synchronisieren von SharePoint- und Team Dateien mit Ihrem Computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) folgen.

- Weitere Informationen finden Sie unter [In-Situ-eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).


## <a name="ediscovery-administration-after-phase-9"></a>eDiscovery-Verwaltung nach Phase 9

**Gilt für:** Alle Kunden, die eDiscovery verwenden

In Phase 9 werden die letzten Schritte für den Wechsel in die neue deutsche Rechenzentrumsregion ausgeführt. In dieser Phase werden alle verbleibenden Dienstkomponenten migriert.
Nach Phase 9 wird die Verwendung des Security & Compliance Centers in der Microsoft Cloud Deutschland (protection.office.de) nicht mehr unterstützt. Verwenden Sie stattdessen das neue [Security Center](https://security.microsoft.com/) oder [Compliance Center](https://compliance.microsoft.com/). Alle Daten wurden in die neuen Verwaltungsportale übertragen.

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
|  Alle SharePoint Online-, OneDrive for Business- und Exchange Online-Speicherorte wurden zusammen mit dem Security and Compliance Center (SCC) migriert. | Alle eDiscovery-Aktivitäten sollten vom weltweiten Mandanten aus ausgeführt werden. Suchvorgänge sind jetzt zu 100 % erfolgreich. Alle Fehler oder Ausfälle sollten normalen Supportkanälen folgen. | Keine |
||||

### <a name="ediscovery-retention-policy"></a>eDiscovery-Aufbewahrungsrichtlinie
**Gilt für:** Alle Kunden, die eine Aufbewahrungsrichtlinie im Rahmen der Schritte vor der Migration angewendet haben

| Schritte: | Beschreibung | Auswirkung |
|:-------|:-------|:-------|
| Entfernen organisationsweiter Aufbewahrungsrichtlinien, die während der Schritte vor der Migration erstellt wurden | Kunden können die organisationsweiten Aufbewahrungsrichtlinien entfernen, die während der Arbeit der Kunden vor der Migration erstellt wurden. | Keine |
||||
