---
title: Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Zusammenfassung: Die Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verstehen.'
ms.openlocfilehash: a77dc43c4c30992d2e50aad94878f9269573db52
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327117"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums

> [!NOTE]
> Dieser Artikel gilt nur für berechtigte Microsoft Cloud Deutschland-Kunden.

Im August 2018 kündigte Microsoft unsere Absicht an, die komplette Microsoft Cloud – Azure-, Office 365-, Dynamics 365-und Power-Plattform – aus neuen Cloud-Regionen in Deutschland bereitzustellen, um die digitale Transformation unserer Kunden besser zu ermöglichen. Wir haben im August 2019 angekündigt, dass wir die neuen Cloud-Regionen in Deutschland für erste Kunden eröffnen. Wir haben seither die Verfügbarkeit von Azure, Office 365, Dynamics 365 und Power Platform angekündigt.

Die neuen Regionen sind darauf ausgelegt, die sich entwickelnden Anforderungen von deutschen Kunden mit mehr Flexibilität, den neuesten intelligenten Cloud-Diensten und der vollständigen Konnektivität mit unserem Microsoft 365 Services Cloud-Netzwerk sowie dem Kundendaten Wohnsitz innerhalb Deutschlands zu erfüllen.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Migrieren zu den neuen deutschen Regionen

Vorhandene Microsoft Cloud Deutschland-Kunden können jetzt mit der Migration Ihrer Office 365, des Dynamics 365-Kundenengagements und der Power Platform-Kunden beginnen. Der erste Schritt besteht darin, [sich für die von Microsoft geleiteten Migration in unsere neuen deutschen Rechenzentrumsregionen anzumelden](https://aka.ms/office365germanymoveoptin).

Für Organisationen, die sich für den Microsoft-gesteuerten Ansatz entscheiden, werden Migrationen voraussichtlich Anfang 2021 beginnen und bis zum 29. Oktober 2021 abgeschlossen sein. Als Ergebnis der Migration werden die wichtigsten Kundendaten und -abonnements in die neuen deutschen Regionen verschoben.

Dieser Artikel bietet eine Übersicht über den von Microsoft geführten Ansatz für die Migration, Klarheit über die Benutzer-und Administratoraktivitäten während und nach der Migration sowie Aktionen, die für Kunden auf der Grundlage der von Ihnen verwendeten Arbeitslasten erforderlich sind.

Die folgenden Dienste werden als Teil des von Microsoft geleiteten Ansatzes migriert:

- Azure-Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365-Gruppen
- Dynamics 365/Power Platform\*\*\*

\*\*Während der Migration von Microsoft Cloud Deutschland in die Regionen des deutschen Rechenzentrums werden vorhandene Skype for Business Online Kunden auf Microsoft Teams umstellen. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*Die Voraussetzungen und Auswirkungen der Migration für diese Dienste werden im Artikel [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin) beschrieben.

Office 365 Video wird am 1. März 2021 eingestellt. Wenn Sie Ihren Office 365-Mandanten in die Regionen der neuen deutschen Rechenzentren migrieren, wird Office 365 Video nach Abschluss der SharePoint Online-Migration nicht unterstützt. Klicken Sie [hier](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) , um weitere Informationen zu erhalten.

## <a name="how-is-the-migration-organized"></a>Wie ist die Migration organisiert?

Diese Abbildung stellt die verschiedenen Komponenten von Office 365 und Dynamics 365 in der Migration zu den neuen deutschen Rechenzentren dar.

![Komponenten von Office 365 und Dynamics 365 in der Migration zu den neuen Rechenzentren in Deutschland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Die Migration wird in Phasen ausgeführt, die alle beginnen, wenn Sie sich [für die Migration anmelden](https://aka.ms/office365germanymoveoptin). Die meisten Migrationsphasen werden als Back-End-Dienstvorgänge ausgeführt, wobei minimale Kundeninteraktion erforderlich ist und eine Phase nach der anderen ausgeführt wird. Der Start für weitere vom Kunden geleitete Aufgaben und den Gesamt Migrationsstatus wird während des Migrationsprozesses über das Nachrichtencenter des Microsoft 365 admin Centers kommuniziert. Beispiele für Aufgaben sind möglicherweise von Kunden verwaltete DNS-Updates, Neukonfiguration von Hybrid Setup für Exchange-Hybrid Kunden oder Azure-Migration.

Die Migration beginnt nicht sofort, wenn das Opt-in erfolgt. Ihre Organisation wird der Liste der Mandanten hinzugefügt, die für eine spätere Migration geplant sind. Sie können die vorarbeits Phasen jetzt beginnen, da diese für eine erfolgreiche Migration und Verwendung nach Abschluss wichtig sind.

Eine Woche vor dem Start der Mandanten Migration erhalten Sie eine Benachrichtigung im Nachrichtencenter Dienst als abschließende Warnung, dass alle Voraussetzungen vollständig sein müssen.

Die Migration wird von Ihrem Azure AD Mandanten aus dem souveränen Deutschland Azure AD Dienst in die Office 365-Dienstinstanz von Azure AD in der EU-Region umsteigen.

Die nächste Phase ist die Migration Ihrer Mandanten&#39;s-Abonnements und Benutzerlizenzen aus Deutschland-spezifischen Produkten.

Nachdem alle Schritte einschließlich der Azure-Kundenmigration abgeschlossen wurden, wird Ihr Mandant im Office 365 Dienste-Dienst fertig gestellt, und die Migration ist als abgeschlossen markiert. An diesem Punkt wird Ihnen die abschließende Aktualisierung des Nachrichten Centers zur Verfügung gestellt. Der Mandant ist jetzt keine vollständig globale Office 365 Organisation.

Sie werden über den Migrations Fortschritt mit Nachrichtencenter-Beiträgen informiert. Die Beiträge werden an bestimmten Meilensteinen ausgeführt, und es werden Anleitungen zum Fortschritt eines Schritts sowie wichtige Informationen für Kunden bereitgestellt, die basierend auf den Prozessanforderungen agieren können. Nachrichtencenter-Benachrichtigungen werden unter den folgenden Meilensteinen bereitgestellt:

- Beginn der Migration (5 Werktage vor Beginn der Migration von Azure AD)
- Azure AD Migration abgeschlossen
- Abonnement-und Lizenz Migration abgeschlossen
- SharePoint-Migration abgeschlossen
- Exchange-Migration abgeschlossen
- Skype for Business abgeschlossen
- Dynamics abgeschlossen
- Power BI abgeschlossen
- Abschließende Cutover der Dienste ist abgeschlossen

## <a name="moving-to-the-new-german-regions"></a>Umstieg auf die neuen deutschen Regionen

Vorhandene Microsoft Cloud Deutschland-Kunden (Microsoft Cloud Deutschland) können jetzt mit der Migration Ihrer Office 365, des Dynamics 365-Kundenengagements und der Power Platform-Kunden beginnen. Der erste Schritt besteht darin, [sich für die von Microsoft geleiteten Migration in unsere neuen deutschen Rechenzentrumsregionen anzumelden](https://aka.ms/office365germanymoveoptin). Wenn Sie Ihr Abonnement erneuern, melden Sie sich automatisch für eine von Microsoft unterstützte Migration an. Microsoft benachrichtigt Kundenmandanten Administratoren per e-Mail und im Nachrichtencenter des Microsoft 365 Admin Center, wenn dies geschehen ist. Wenn Sie den Prozess jedoch jetzt lieber starten möchten, können Sie sich heute direkt im Microsoft 365 Admin Center [Anmelden](https://aka.ms/office365germanymoveoptin) . Migrationen werden voraussichtlich Anfang 2021 beginnen und werden bis zum 29. Oktober 2021 abgeschlossen sein. 

Als Ergebnis der Migration werden die wichtigsten Kundendaten und -abonnements in die neuen deutschen Regionen verschoben.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Wie Sie sich auf die Migration auf Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen vorbereiten können

Der erste Schritt besteht darin, Microsoft so zu benachrichtigen, dass wir Ihre Berechtigung zum Migrieren Ihres Abonnements und der Daten von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen im deutschen Datencenter haben. Weitere Informationen finden Sie im [Opt-in-Prozess](https://aka.ms/office365germanymoveoptin) , und beachten Sie Folgendes:

- Alle migrierten Kunden müssen die Verbindung mit den Office 365 Diensten [Office 365 URLs und IP-Adressen](urls-and-ip-address-ranges.md)überprüfen, einschließlich der neuen Regionen des deutschen Datencenters. InAktion kann zu Dienst-und Client Fehlern führen.
- Überprüfen Sie die Beschreibung des Office 365-Platt Form Diensts, um zu verstehen, welche Features und Dienste für Ihre Organisation verfügbar sind, nachdem Sie die Migration in die Region Deutschland durchführt haben.
- Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. Vor Beginn der Migration müssen Sie alle Testversionen abbrechen oder in kostenpflichtige Abonnements konvertieren.

## <a name="where-do-i-go-from-here"></a>Wo gehe ich von hier aus?

Lesen Sie den folgenden Abschnitt mit häufig gestellten Fragen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-migration-required"></a>Ist die Migration erforderlich?

Microsoft bietet Office 365 Mandanten Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums ohne Aufpreis. Wir empfehlen zwar dringend, dass Sie sich für die Migration zu den neuen Regionen des deutschen Datencenters entscheiden, aber wir werden weiterhin die erforderlichen Sicherheitsupdates für die Microsoft Cloud Deutschland-Region bereitstellen.

Office 365 Dienste in den neuen Bereichen des Rechenzentrums in Deutschland:

- Sie bieten marktgerechte Preise für [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)und [Power BI](https://powerbi.microsoft.com/pricing/).
- Sind mit dem globalen Microsoft&#39;-Netzwerk verbunden, das Hunderte von Netzwerk-Edge-Standorten, Peering-Standorten und Ausgangspunkten bietet, um eine robuste Benutzererfahrung überall auf der Welt bereitzustellen.
- Sie helfen Ihnen, die Anforderungen an die lokale Datenhaltung innerhalb von Deutschland zu erfüllen.
- Liefern Sie unser umfassendes globales Cloud-Angebot mit den neuesten Versionen unserer Dienste und neuen Funktionen wie Microsoft Teams und Multi-Geo in Office 365. Hier finden Sie die Vergleiche unserer Produkte nach Region für [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) und [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Sie bieten die vollständige Funktionalität, Sicherheit auf Unternehmensniveau und umfassende Funktionen, die Kunden bei der Einhaltung behördlicher oder eigener Vorschriften unterstützen.
- Sie sind im Rahmen vorhandener Verträge für Onlinedienstleistungen verfügbar.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Wie hoch ist die Dienstverfügbarkeit der verschiedenen Office 365-Clouddienstangebote?

Die folgenden 15 Dienste stehen im Cloud-Dienstangebot von Microsoft Cloud Deutschland zur Verfügung. Wir fügen Microsoft Cloud Deutschland keine neuen Dienste hinzu.

1. Exchange Online
2. Kunden-Lockbox (Exchange Online)
3. Gruppen (moderne Gruppen)
4. Delve-Profil
5. Exchange Online Protection
6. Advanced Threat Protection, ATP
7. Advanced eDiscovery
8. Advanced Data Governance
9. SharePoint Online
10. Kunden-Lockbox (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 ProPlus
15. Outlook Mobile

Derzeit sind 29 Dienste als Bestandteil von Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verfügbar. In Übereinstimmung mit den globalen Office 365-Diensten werden fortlaufend neue Features und Dienste bereitgestellt.

1. Exchange Online
2. Kunden-Lockbox für Exchange Online
3. Microsoft 365-Gruppen
4. Delve-Profil
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Advanced Threat Protection, ATP
9. Advanced eDiscovery
10. Advanced Security Management
11. Verwaltung von Informationsrechten
12. Advanced Data Governance
13. SharePoint Online
14. Kunden-Lockbox für SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (wird während der Migration zu Microsoft Teams migriert)
18. Cloud PBX
19. PSTN-Konferenzen
20. PSTN-Anrufe
21. Microsoft Teams
22. Administrator-Berichte/ Verwendungsberichte
23. Word Online, Excel Online, PowerPoint, OneNote und Visio Online
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, InTune und Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Wann wird die Migration durchgeführt?

**Azure**

Wenn Sie nur ein Azure-Kunde sind, können Sie die [Migration](https://docs.microsoft.com/azure/germany/germany-migration-main) ihrer Azure-Ressourcen in eine andere Region heute beginnen. Wenn Sie Azure mit Office 365, Dynamics 365 oder Power BI haben, führen Sie die folgenden Schritte aus.

**Office 365**

[Melden Sie sich an](https://aka.ms/office365germanymoveoptin) für noch heute für Migration durch Microsoft an. Wenn wir die Migration starten möchten, werden wir Sie über das Nachrichtencenter im Microsoft 365 Admin Center informieren.

**Dynamics 365 und Power BI**

Entscheiden Sie sich für das Kunden Engagement von Microsoft-Driven Migration for [Dynamics 365](https://aka.ms/D365ceOptIn) und [Power BI](https://aka.ms/PBIOptIn) heute. Wenn wir bereit sind, Ihre Migration zu starten, werden wir Sie über das Message Center im Microsoft 365 Admin Center informieren.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Ändert sich die Preisänderung für die Office 365 Dienste, die ich verwende?

Ja. Die Preisgestaltung in den globalen Cloud-Regionen von Microsoft&#39;(einschließlich der neuen Datencenter Regionen) ist im Allgemeinen geringer.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Welche SKUs und Lizenzen werden während der Abonnement Migration auf meine Organisation und Benutzer angewendet?

Während der Migration von Microsoft Cloud Deutschland zu den Office 365 Diensten werden die dienstspezifischen SKUs für Deutschland durch globale Versionen derselben oder ähnlicher SKU ersetzt. In den meisten Fällen ist die SKU in Office 365 Diensten identisch, es gibt jedoch nur wenige Ersatz, bei denen die SKU in Deutschland in den Office 365 Diensten nicht mehr verfügbar ist. Wenn Sie die Ihrer Organisation zugewiesene SKU nach Abschluss der Migration aktualisieren möchten, wenden Sie sich an Ihren Verkäufer, um die zugewiesenen Dienste hinzuzufügen oder zu ändern.

| Microsoft Cloud Deutschland-Produkt-SKU (de) | Microsoft Cloud Global – Produkt-SKU (WW) |
| --- | --- |
| Kunden-Lockbox \_ de (Lockbox \_ de) | Kunden-Lockbox (Lockbox) |
| Dynamics 365 Enterprise Edition-zusätzlicher Datenbankspeicher \_ de (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition – zusätzlicher Datenbankspeicher (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-zusätzliche Nichtproduktionsinstanz \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition – zusätzliche Nichtproduktionsinstanz (CRMTESTINSTANCE) |
| Dynamics 365 für Kundendienst Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ Service \_ de) | Dynamics 365 für Kundendienst Enterprise Edition (DYN365 \_ Enterprise \_ \_ -Kundendienst) |
| Dynamics 365 für Sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ de) | Dynamics 365 für Sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 für Team Mitglieder Enterprise Edition \_ de (DYN365 \_ Enterprise \_ \_ -Teammitglieder \_ de) | Dynamics 365 für Team Mitglieder Enterprise Edition (DYN365 \_ Enterprise \_ \_ -Teammitglieder) |
| Dynamics 365 Plan 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| ECAL-Dienste (EOA, EoP, DLP) \_ de (ECAL \_ Services \_ de) | ECAL-Dienste (EOA, EoP, DLP) (ECAL- \_ Dienste) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (Plan 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (Plan 1) (EXCHANGESTANDARD) |
| Exchange Online (Plan 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (Plan 2) (EXCHANGEENTERPRISE) |
| Exchange Online Archivierung für Exchange Online \_ de (EXCHANGEARCHIVE \_ Addon \_ de) | Exchange Online Archivierung für Exchange Online (EXCHANGEARCHIVE \_ Addon) |
| Exchange Online Archivierung für Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Exchange Online Archivierung für Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (Exchange \_ S \_ Essentials) |
| Exchange Online Kiosk \_ de (EXCHANGEDESKLESS \_ de) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ de (EoP \_ Enterprise \_ de) | Exchange Online Schutz (EoP \_ Enterprise) |
| Microsoft 365 Business Standard (O365 \_ Business \_ Premium) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Microsoft Dynamics CRM Online-Instanz \_ de (CRMINSTANCE \_ de) | Microsoft Dynamics CRM Online-Instanz (CRMINSTANCE) |
| Office 365 a1 für Faculty \_ de (STANDARDWOFFPACK \_ Faculty \_ de) | Office 365 a1 für Fakultät (STANDARDWOFFPACK \_ Faculty) |
| Office 365 a1 für Schüler \_ de (STANDARDWOFFPACK \_ Student \_ de) | Office 365 a1 für Schüler (STANDARDWOFFPACK \_ Student) |
| Office 365 Advanced Compliance \_ de (EQUIVIO \_ Analytics \_ de) | Microsoft 365 E5-Compliance (Information \_ Protection \_ Compliance) |
| Office 365 Advanced Threat Protection (Plan 1) \_ de (ATP \_ Enterprise \_ de) | Office 365 Advanced Threat Protection (Plan 1) (ATP \_ Enterprise) |
| Office 365 Business Essentials \_ de (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ Business \_ Essentials) |
| Office 365 Business Premium \_ de (O365 \_ Business \_ Premium \_ de) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Office 365 Business \_ de (O365 \_ Business \_ de) | Microsoft 365 apps for Business (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 ohne ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 ohne ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 zusätzlicher Dateispeicher \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 zusätzlicher Dateispeicher (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus für Faculty \_ de (sich officesubscription \_ Faculty \_ de) | Office 365 ProPlus für die Fakultät (sich officesubscription \_ Faculty) |
| Office 365 ProPlus für Schüler \_ de (sich officesubscription \_ Student \_ de) | Office 365 ProPlus für Schüler (sich officesubscription \_ Student) |
| Office 365 ProPlus \_ de (sich officesubscription \_ de) | Office 365 ProPlus (sich officesubscription) |
| OneDrive für Unternehmen (Plan 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive für Unternehmen (Plan 1) (WACONEDRIVESTANDARD) |
| OneDrive für Unternehmen (Plan 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive für Unternehmen (Plan 2) (WACONEDRIVEENTERPRISE) |
| Power BI pro für Faculty \_ de (Power \_ BI \_ pro \_ Faculty \_ de) | Power BI pro für Dozenten (Power \_ BI \_ pro \_ Faculty) |
| Power BI pro \_ de (Power \_ BI \_ pro \_ de) | Power BI pro (Power \_ BI \_ pro) |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| Projekt Plan 3 \_ de (PROJECTPROFESSIONAL \_ de) | Projekt Plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (Plan 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (Plan 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (Plan 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (Plan 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (Plan 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (Plan 1) \_ de (MCOIMP \_ de) | Skype for Business Online (Plan 1) (MCOIMP) |
| Skype for Business Online (Plan 2) \_ de (MCOSTANDARD \_ de) | Skype for Business Online (Plan 2) (MCOSTANDARD) |
| Skype for Business Plus Cal \_ de (MCOPLUSCAL \_ de) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Online-Plan 1 für Faculty \_ de (VISIOONLINE \_ PLAN1 \_ FAC \_ de) | Visio Online-Plan 1 für Faculty (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online-Plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio Online-Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Online-Plan 2 für Faculty \_ de (VISIOCLIENT \_ Faculty \_ de) | Visio Online-Plan 2 für Faculty (VISIOCLIENT \_ Faculty) |
| Visio Online-Plan 2 \_ de (VISIOCLIENT \_ de) | Visio Online-Plan 2 (VISIOCLIENT) |
| Visio-Plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio-Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio-Plan 2 \_ de (VISIOCLIENT \_ de) | Visio-Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Wie erhalte ich Hilfe von Microsoft, um zu einer neuen Region zu migrieren, oder Antworten auf meine Support-Fragen?

Wenn Sie Fragen haben, können Sie uns oder Ihren Partner kontaktieren:

- Für Azure können Sie [neue Supportanfragen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) im Azure-Portal senden.
- Für Office 365 können Sie Fragen über den &quot; Link Need Help? &quot; des [Microsoft 365 Admin Center](https://portal.office.de/)übermitteln.
- Wenn Sie Dynamics 365 Kunden Engagement und Power BI-Kunde sind und auch Office 365 haben, können Sie Fragen über den &quot; Link Need Help? &quot; des [Microsoft 365 Admin Center](https://portal.office.de/)übermitteln. Die Dynamics 365 Customer Engagement-Supportoptionen befinden sich [hier](https://docs.microsoft.com/dynamics365/get-started/support/). Die Power BI-Supportoptionen befinden sich [hier](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zur Migration zu den neuen Regionen des deutschen Rechenzentrums kommen. Bookmarken Sie diese Seite, damit Sie einchecken und aktuell bleiben können.

- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](https://aka.ms/office365germanymoveoptin)
- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365endpoints)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
