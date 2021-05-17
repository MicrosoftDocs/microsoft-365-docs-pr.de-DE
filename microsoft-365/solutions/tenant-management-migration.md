---
title: 'Schritt 4: Migration für Ihre Microsoft 365 für Enterprise-Mandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migrieren Sie Windows Geräte, Office Client-Apps und Office Server für Microsoft 365 Mandanten.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929144"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 4. Migration für Ihre Microsoft 365 für Enterprise-Mandanten

Die meisten Unternehmensorganisationen verfügen über eine heterogene Umgebung, die mehrere Versionen von Betriebssystemen, Clientsoftware und Serversoftware umfasst. Microsoft 365 für Unternehmen umfasst die sichersten Versionen der wichtigsten Komponenten Ihrer IT-Infrastruktur. Es enthält auch Produktivitätsfeatures, die für die Nutzung von Cloudtechnologien entwickelt wurden.

Um den Geschäftswert der integrierten Microsoft 365 unternehmensintegrierten Produktsuite zu maximieren, beginnen Sie mit der Planung und Implementierung einer Strategie zum Migrieren dieser Versionen:

| Von | An |
|:-------|:-----|
| Windows 7 und Windows 8.1 | Windows 10 Enterprise |
| Office Auf den Geräten Ihrer Mitarbeiter installierte Clientprodukte | Microsoft 365 Apps for Enterprise |
| Office auf lokalen Servern installierte Serverprodukte | Ihre entsprechenden cloudbasierten Dienste in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrieren zu Windows 10

Jede Microsoft 365 enterprise-Lizenz enthält eine Lizenz für Windows 10 Enterprise. Um Ihre Geräte zu migrieren, auf Windows 7 oder Windows 8.1, können Sie ein in-Place-Upgrade durchführen. Der Support wurde für Windows 7 am *14. Januar 2020 beendet.* 

Weitere Methoden zum Installieren von Windows 10 Enterprise über ein in-place-Upgrade hinaus finden Sie [unter Windows 10 Bereitstellungsszenarien](/windows/deployment/windows-10-deployment-scenarios). Sie können [die Bereitstellung von Windows 10 auch selbst planen](/windows/deployment/planning/).

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrieren zu Microsoft 365 Apps for Enterprise

Microsoft 365 enterprise enthält Microsoft 365 Apps for Enterprise, eine Version der Office-Clientprodukte (Word, PowerPoint, Excel und Outlook), die in der Microsoft Cloud installiert und aktualisiert wird. Weitere Informationen finden Sie unter [Informationen Microsoft 365 Apps for Enterprise](/deployoffice/about-microsoft-365-apps).

Anstatt Ihre Computer für Office 2019 oder älteren Versionen auf dem neuesten Stand zu halten, gehen Sie wie folgt vor:

1. Hier können Sie eine Microsoft 365 für Ihre Benutzer erhalten und zuweisen.
2. Deinstallieren Office 2013 oder Office 2016 auf ihren Computern.
3. Installieren Microsoft 365 Apps for Enterprise, entweder einzeln oder während eines IT-Rollouts. Weitere Informationen finden Sie unter [Bereitstellungshandbuch für Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365 Apps for Enterprise installiert sowohl Sicherheitsupdates als auch neue Featureupdates automatisch und kann cloudbasierte Dienste in Microsoft 365 sicherheit und Produktivität nutzen.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migrieren von lokalen Servern und Daten zu Microsoft 365

Microsoft 365 für Unternehmen umfasst cloudbasierte Versionen von Office-Serverdiensten, die einige der gleichen Tools wie lokale Versionen von Office-Serversoftware verwenden, z. B. Webbrowser und Outlook Client. Diese cloudbasierten Dienste werden aus Sicherheitsgründen und neuen Features automatisch aktualisiert. Nach der Migration kann Ihre IT-Abteilung die Zeit sparen, die zum Warten und Aktualisieren von lokalen Servern benötigt wird.

Verwenden Sie die folgenden Ressourcen, um Informationen zum Migrieren von Benutzern und Daten für bestimmte Microsoft 365 zu erhalten:

- [Verschieben von Postfächern von lokalen Exchange Server in Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrieren SharePoint Daten von SharePoint Server zu SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrieren Skype for Business Online zu Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Umstellung Ihrer gesamten Organisation

Laden Sie dieses Übergangsposter herunter, um ein besseres Bild davon zu erhalten, wie Sie Ihre gesamte Organisation zu den Produkten und Diensten in Microsoft 365 Enterprise verschieben:

[![Abbildung des Posters "Transition to Microsoft 365".](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Dieses zweiseitige Poster bietet eine schnelle Methode, um Ihre vorhandene Infrastruktur aufzulisten. Verwenden Sie sie, um Anleitungen für den Wechsel zu einem Produkt oder dienst in Microsoft 365 Unternehmen zu erhalten. Es zeigt Windows und Office Produkte sowie andere Infrastruktur- und Sicherheitselemente wie Geräteverwaltung, Identitäts- und Bedrohungsschutz sowie Informationsschutz und Compliance.

## <a name="results-of-step-4"></a>Ergebnisse von Schritt 4

Für die Migration für Microsoft 365 Mandanten haben Sie ermittelt:

- Welche Geräte ausgeführt Windows 7 oder Windows 8.1 und der Plan, sie auf Windows 10 Enterprise.
- Auf welchen Geräten werden die Office Client-Apps ausgeführt, und der Plan, sie auf Microsoft 365 für Unternehmen zu aktualisieren.
- Welche lokalen Office Serverdienste zu ihren Microsoft 365 migriert werden sollten, sowie der Plan, sie und ihre Daten zu migrieren.

Im Folgenden finden Sie ein Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern.

![Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In dieser Abbildung verfügt die Organisation über:

- Die lokalen Postfächer wurden Exchange Server zu Exchange Online.
- Die lokalen Serverwebsites und -SharePoint wurden zu SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Fortlaufende Wartung der Migration

Auf fortlaufender Basis müssen Sie möglicherweise:

- Je nachdem, wie Exchange Postfachmigration ist, rollen Sie den Übergang zu Exchange Online ihrer Organisation fort.
- Je nach Status der lokalen Migration SharePoint Sie den Übergang zu SharePoint in Microsoft 365 Ihrer Organisation fort.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 5. Bereitstellen der Geräte- und App-Verwaltung](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Fahren Sie mit [der Geräte- und App-Verwaltung fort,](tenant-management-device-management.md) um die Geräte- und App-Verwaltung zu bereitstellen.