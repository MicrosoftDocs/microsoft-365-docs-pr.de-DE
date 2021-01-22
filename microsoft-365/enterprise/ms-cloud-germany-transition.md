---
title: Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Zusammenfassung: Die Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verstehen.'
ms.openlocfilehash: 28344f1249e4f51bb9802bf19ca7561182610a7c
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921592"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen

> [!NOTE]
> Dieser Artikel gilt nur für anspruchsberechtigte Kunden von Microsoft Cloud Deutschland.

Im August 2018 hat Microsoft die Absicht angekündigt, die gesamte Microsoft-Cloud – Azure, Office 365, Dynamics 365 und Power Platform – aus neuen Cloud-Regionen in Deutschland bereitzustellen, um die digitale Transformation seiner Kunden noch besser zu unterstützen. Im August 2019 haben wir angekündigt, dass wir die neuen Cloud-Regionen in Deutschland für erste Kunden eröffnen. Wir haben seitdem die Verfügbarkeit von Azure, Office 365, Dynamics 365 und Power Platform angekündigt.

Die neuen Regionen sind für die Anpassung an die sich ständig verändernden Anforderungen deutscher Kunden ausgelegt und bieten größere Flexibilität, die neuesten intelligenten Cloud-Dienste und die umfassende Verbindung zu unserem Microsoft 365 Cloud-Netzwerk sowie Kundendatenhaltung in Deutschland.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Migration zu den neuen deutschen Rechenzentrumsregionen

Bestehende Kunden der Microsoft Cloud Deutschland können nun mit der Migration ihrer Office 365-, Dynamics 365 Customer Engagement- und Power Platform-Kunden beginnen. Der erste Schritt besteht darin, [sich für eine von Microsoft geleitete Migration in unsere neuen deutschen Rechenzentrumsregionen anzumelden](https://aka.ms/office365germanymoveoptin).

Die Migrationen für Organisationen, die sich für die durch Microsoft geleitete Migration anmelden, werden voraussichtlich Anfang 2021 starten und bis zum 29. Oktober 2021 abgeschlossen sein. Als Ergebnis der Migration werden die wichtigsten Kundendaten und -abonnements in die neuen deutschen Rechenzentrumsregionen verschoben.

Dieser Artikel enthält eine Übersicht über die durch Microsoft durchgeführte Migration, Details zu den Erfahrungen für Benutzer und Administratoren während und nach der Migration sowie zu Aktionen, die für Kunden basierend auf den von Ihnen verwendeten Arbeitslasten erforderlich sind.

Die folgenden Dienste werden im Rahmen der Migration durch Microsoft migriert:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365-Gruppen
- Dynamics 365 / Power Platform\*\*\*

\*\*Während der Migration von Microsoft Cloud Deutschland in die deutschen Rechenzentrumsregionen werden bestehende Skype for Business Online-Kunden auf Microsoft Teams umgestellt. Weitere Informationen finden Sie unter [Erste Schritte mit dem Microsoft Teams-Upgrade](https://aka.ms/SkypeToTeams-Home).

\*\*\*Die Voraussetzungen und Auswirkungen der Migration für diese Dienste sind im Artikel [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin) beschrieben.

Office 365 Video wird am 1. März 2021 eingestellt. Wenn Sie Ihren Office 365-Mandanten in die Regionen der neuen deutschen Rechenzentren migrieren, wird Office 365 Video nach Abschluss der SharePoint Online-Migration nicht unterstützt. Weitere Informationen finden Sie unter [Microsoft Cloud Deutschland-Zeitachse](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>Wie ist die Migration organisiert?

Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren.

![Die neun Phasen der Migration in die neuen Rechenzentren in Deutschland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Diese Phasen beginnen, wenn Sie [sich für die Migration entscheiden.](https://aka.ms/office365germanymoveoptin) Die meisten Migrationsphasen werden nach und nach als Back-End-Dienstvorgänge durchgeführt, bei denen nur wenige Kundeninteraktionen erforderlich sind. Ab wann Maßnahmen auf Kundenseite erforderlich sind sowie der allgemeine Stand der Migration werden während des Migrationsprozesses über das Nachrichtencenter des Microsoft 365 Admin Centers mitgeteilt. Zu den kundenseitig erforderlichen Maßnahmen zählen beispielsweise durch Kunden verwaltete DNS-Updates, die Neukonfiguration des Hybrid-Setups für Kunden von Exchange-Hybridlösungen oder Azure-Migrationen.

Die Migration beginnt nicht unmittelbar bei der Anmeldung. Ihre Organisation wird der Liste von Mandanten hinzugefügt, die für eine spätere Migration geplant sind. Sie können mit den Vorbereitungsphasen jetzt beginnen, da diese für eine erfolgreiche Migration und anschließende Nutzung wesentlich sind:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)

Eine Woche vor Beginn der Mandantenmigration erhalten Sie im Nachrichtencenter-Dienst eine Benachrichtigung, mit der Sie ein letztes Mal darauf hingewiesen werden, dass alle Voraussetzungen erfüllt sein müssen.

Bei der Migration wird Ihr Azure AD-Mandant vom unabhängigen Azure AD-Dienst Deutschland in die Office 365-Dienste-Instanz von Azure AD in der europäischen Region verlagert.

Die nächste Phase besteht in der Migration der Abonnements und Benutzerlizenzen Ihres Mandanten für Deutschland-spezifische Produkte in globale Produkte.

Sobald alle Schritte einschließlich der Azure Kunden-Migration durchgeführt wurden, wird Ihr Mandant im Office 365 Services-Dienst finalisiert und die Migration als abgeschlossen gekennzeichnet. An diesem Punkt erhalten Sie eine abschließende Benachrichtigung im Nachrichtencenter. Der Mandant ist nun eine vollständig globale Office 365-Organisation.

Sie werden mittels Nachichtencenter-Mitteilungen über den Status der Migration informiert. Die Mitteilungen erfolgen anlässlich bestimmter Meilensteine und bieten Orientierungshilfe zum Fortschritt eines Schritts sowie wichtige Informationen für kundenseitige Maßnahmen auf der Grundlage der Prozessanforderungen. Nachrichtencenter-Mitteilungen werden anlässlich der folgenden Meilensteine bereitgestellt:

- Beginn der Migration (5 Werktage vor Beginn der Azure AD-Migration)
- Azure AD-Migration abgeschlossen
- Abonnement- und Lizenzmigration abgeschlossen
- SharePoint-Migration abgeschlossen
- Exchange-Migration abgeschlossen
- Skype for Business abgeschlossen
- Dynamics abgeschlossen
- Power BI abgeschlossen
- Endgültige Umstellung der Dienste abgeschlossen

## <a name="moving-to-the-new-german-datacenter-regions"></a>Verschiebung in die neuen deutschen Rechenzentrumsregionen

Microsoft Cloud Deutschland-Bestandskunden können nun mit der Migration ihrer Office 365-, Dynamics 365 Customer Engagement- und Power Platform-Diensten beginnen. Der erste Schritt besteht darin, [sich für eine von Microsoft geleitete Migration in unsere neuen deutschen Rechenzentrumsregionen anzumelden](https://aka.ms/office365germanymoveoptin). Wenn Sie Ihr Abonnement verlängern, melden Sie sich automatisch für eine von Microsoft geleitete Migration an. Microsoft wird in diesem Fall die Mandantenadministratoren von Kunden per E-Mail und im Nachrichtencenter des Microsoft 365 Admin Centers darüber benachrichtigen. Wenn Sie es jedoch vorziehen, den Vorgang jetzt zu starten, können Sie direkt im Microsoft 365 Admin Center sofort [das Opt-In vornehmen](https://aka.ms/office365germanymoveoptin). Die Migrationen werden voraussichtlich Anfang 2021 beginnen und bis zum 29. Oktober 2021 abgeschlossen sein. 

Als Ergebnis der Migration werden die wichtigsten Kundendaten und -abonnements in die neuen deutschen Rechenzentrumsregionen verschoben.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Vorbereitung auf die Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen

Der erste Schritt besteht darin, Microsoft zu benachrichtigen, sodass wir über Ihr Einverständnis zum Migrieren Ihres Abonnements und Ihrer Daten aus der Microsoft-Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verfügen. Anweisungen hierzu finden Sie auf der Seite zum [Opt-In-Vorgang](https://aka.ms/office365germanymoveoptin). Bitte beachten Sie Folgendes:

- Alle Kunden mit Migrationsbedarf müssen die Verbindung zu den [Office 365-URLs und -IP-Adressen](urls-and-ip-address-ranges.md) der Office 365-Dienste überprüfen, die die neuen deutschen Rechenzentrumsregionen umfassen. Diesbezügliche Untätigkeit kann zu Dienst- und Clientfehlern führen.
- Überprüfen Sie die Liste der [Vorarbeiten](ms-cloud-germany-transition-add-pre-work.md), um sicherzustellen, dass Ihre Organisation informiert und auf die Änderungen vorbereitet ist.
- Lesen Sie die Beschreibung der Office 365-Plattformdienste, um sich ein Bild davon zu machen, welche Funktionen und Dienste nach der Migration in die deutsche Rechenzentrumsregion für Ihre Organisation verfügbar sein werden.
- Testabonnements werden nicht migriert und blockieren die Migration aller kostenpflichtigen Abonnements. Sie müssen vor dem Beginn der Migration alle Testabos stornieren oder in kostenpflichtige Abonnements umwandeln.

## <a name="where-do-i-go-from-here"></a>Weitere Schritte

Lesen Sie den folgenden Abschnitt mit Antworten auf häufig gestellte Fragen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-migration-required"></a>Ist die Migration erforderlich?

Microsoft bietet eine Mandantenmigration für Office 365 von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen ohne Aufpreis. Wir empfehlen Ihnen dringend, sich für die Migration zu den neuen deutschen Rechenzentrumsregionen anzumelden, aber wir werden weiterhin die erforderlichen Sicherheitsupdates für die Region „Microsoft Cloud Deutschland“ bereitstellen.

Merkmale der Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen:

- Sie bieten marktgerechte Preise für [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)und [Power BI](https://powerbi.microsoft.com/pricing/).
- Sie sind mit dem globalen Microsoft-Netzwerk verbunden und bieten eine Vielzahl von Netzwerk-Edge-Sites, Peering-Standorten und Übergabepunkten, um überall auf der Welt eine verlässliche Benutzererfahrung zur ermöglichen.
- Sie helfen Ihnen, Anforderungen im Hinblick auf die lokale Kundendatenhaltung innerhalb von Deutschland zu erfüllen.
- Sie bieten Zugriff auf unser umfassendes globales Cloud-Angebot, einschließlich der neuesten Versionen unserer Dienste und neuer Lösungen wie Microsoft Teams und Multi-Geo in Office 365. Hier finden Sie die Vergleiche unserer Produkte nach Region für [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) und [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Sie bieten die vollständige Funktionalität, Sicherheit auf Unternehmensniveau und umfassende Funktionen, die Kunden bei der Einhaltung behördlicher oder eigener Vorschriften unterstützen.
- Sie sind im Rahmen vorhandener Verträge für Onlinedienstleistungen verfügbar.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Wie hoch ist die Dienstverfügbarkeit der verschiedenen Office 365-Clouddienstangebote?
<h2 id="serv-avail"></h2>

Die folgenden 15 Dienste sind im Clouddienstangebot von Microsoft Cloud Deutschland verfügbar. Microsoft Cloud Deutschland werden keine neuen Dienste hinzugefügt.

1. Exchange Online
2. Kunden-Lockbox (Exchange Online)
3. Gruppen (moderne Gruppen)
4. Delve-Profil
5. Exchange Online Protection
6. Microsoft Defender für Office 365
7. Advanced eDiscovery
8. Advanced Data Governance
9. SharePoint Online
10. Kunden-Lockbox (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 ProPlus
15. Outlook Mobile

Derzeit sind 39 Dienste als Bestandteil von Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verfügbar. In Übereinstimmung mit den globalen Office 365-Diensten werden fortlaufend neue Features und Dienste bereitgestellt.

1. Exchange Online
2. Kunden-Lockbox für Exchange Online
3. Microsoft 365-Gruppen
4. Delve-Profil
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Microsoft Defender für Office 365
9. Advanced eDiscovery
10. Advanced Security Management
11. Schutz von Informationen für Office 365 
12. Advanced Data Governance
13. SharePoint Online
14. Kunden-Lockbox für SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (während der Migration erfolgt ein Wechsel zu Microsoft Teams)
18. Cloud PBX
19. PSTN-Konferenzen
20. PSTN-Anrufe
21. Microsoft Teams
22. Administrator-Berichte/ Verwendungsberichte
23. Office für das Web
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune und Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power BI für Office 365
32. Power Virtual Agents für Office 365
33. PowerApps für Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Listen

### <a name="when-will-migration-happen"></a>Wann wird die Migration durchgeführt?

**Azure**

Wenn Sie nur Azure-Kunde sind, können Sie bereits mit der [Migration](https://docs.microsoft.com/azure/germany/germany-migration-main) Ihrer Azure-Ressourcen beginnen. 

Wenn Sie Azure mit Office 365, Dynamics 365 oder Power BI verwenden, müssen Sie den Migrationsprozess befolgen, um eine erfolgreiche AzureAD-Migration sicherzustellen, bevor Sie die selbstgesteuerte Azure-Migration beginnen. Sie müssen die Azure-Migration vor der Dienstschließung abschließen, um Ihre Azure-Workloads mit Ihrer AzureAD- und Office 365-Organisation beizubehalten.

**Office 365**

[Melden Sie sich noch heute für von Microsoft gesteuerte Migration an](https://aka.ms/office365germanymoveoptin). Sobald wir bereit sind, Ihre Migration zu starten, werden wir Sie darüber über das Nachrichtencenter im Microsoft 365 Admin Center informieren.

**Dynamics 365 und Power BI**

Melden Sie sich noch heute für die von Microsoft gesteuerte Migration für [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) und [Power BI](https://aka.ms/PBIOptIn) an. Sobald wir bereit sind, Ihre Migration zu starten, werden wir Sie darüber über das Nachrichtencenter im Microsoft 365 Admin Center informieren.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Werden sich die Preise für die von mir verwendeten Office 365-Dienste ändern?

Ja. Die Preise in den globalen Microsoft Cloud-Regionen (einschließlich der neuen Rechenzentrumsregionen) sind im Allgemeinen niedriger.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Welche SKUs und Lizenzen werden während der Abonnementmigration auf meine Organisation und ihre Benutzer angewendet?

Während der Migration von Microsoft Cloud Deutschland zu den Office 365-Diensten werden die servicespezifischen SKUs für Deutschland durch globale Versionen derselben oder ähnlicher SKUs ersetzt. In den meisten Fällen ist die SKU in Office 365-Diensten identisch, es gibt jedoch einige wenige SKUs, die in Deutschland in den Office 365-Diensten nicht mehr verfügbar sind und ersetzt werden. Wenn Sie die Ihrer Organisation zugewiesene SKU nach Abschluss der Migration aktualisieren möchten, wenden Sie sich an Ihren Händler, um die zugeordneten Dienste hinzuzufügen oder zu ändern.

| Microsoft Cloud Deutschland – Produkt-SKU (DE) | Microsoft Cloud Global – Produkt-SKU (WW) |
| --- | --- |
| Kunden-Lockbox\_DE (LOCKBOX\_DE) | Kunden-Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition – Zusätzlicher Datenbankspeicher\_DE (CRMSTORAGE\_DE) | Dynamics 365 Enterprise Edition – Zusätzlicher Datenbankspeicher (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition – Zusätzliche nicht produktionsbezogene Instanz\_DE (CRMTESTINSTANCE\_DE) | Dynamics 365 Enterprise Edition – Zusätzliche nicht produktionsbezogene Instanz (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition\_DE (DYN365\_ENTERPRISE\_CUSTOMER\_SERVICE\_DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365\_ENTERPRISE\_CUSTOMER\_SERVICE) |
| Dynamics 365 for Sales Enterprise Edition\_DE (DYN365\_ENTERPRISE\_SALES\_DE) | Dynamics 365 for Sales Enterprise Edition (DYN365\_ENTERPRISE\_SALES) |
| Dynamics 365 for Team Members Enterprise Edition\_DE (DYN365\_ENTERPRISE\_TEAM\_MEMBERS\_DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365\_ENTERPRISE\_TEAM\_MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_DE (DYN365\_ENTERPRISE\_PLAN1\_DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365\_ENTERPRISE\_PLAN1) |
| ECAL-Dienste (EOA, EOP, DLP)\_DE (ECAL\_SERVICES\_DE) | ECAL-Dienste (EOA, EOP, DLP) (ECAL\_SERVICES) |
| Enterprise Mobility + Security E3\_DE (EMS\_DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (Plan 1)\_DE (EXCHANGESTANDARD\_DE) | Exchange Online (Plan 1) (EXCHANGESTANDARD) |
| Exchange Online (Plan 2)\_DE (EXCHANGEENTERPRISE\_DE) | Exchange Online (Plan 2) (EXCHANGEENTERPRISE) |
| Exchange Online-Archivierung für Exchange Online\_DE (EXCHANGEARCHIVE\_ADDON\_DE) | Exchange Online-Archivierung für Exchange Online (EXCHANGEARCHIVE\_ADDON) |
| Exchange Online-Archivierung für Exchange Server\_DE (EXCHANGEARCHIVE\_DE) | Exchange Online-Archivierung für Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials\_DE (EXCHANGE\_S\_ESSENTIALS\_DE) | Exchange Online Essentials (EXCHANGE\_S\_ESSENTIALS) |
| Exchange Online Kiosk\_DE (EXCHANGEDESKLESS\_DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection\_DE (EOP\_ENTERPRISE\_DE) | Exchange Online Protection (EOP\_ENTERPRISE) |
| Microsoft 365 Business Standard (O365\_BUSINESS\_PREMIUM) | Microsoft 365 Business Standard (O365\_BUSINESS\_PREMIUM) |
| Microsoft Dynamics CRM Live-Instanz\_DE (CRMINSTANCE\_DE) | Microsoft Dynamics CRM Live-Instanz (CRMINSTANCE) |
| Office 365 A1 für Lehrpersonal\_DE (STANDARDWOFFPACK\_FACULTY\_DE) | Office 365 A1 für Lehrpersonal (STANDARDWOFFPACK\_FACULTY) |
| Office 365 A1 für Schüler und Studenten\_DE (STANDARDWOFFPACK\_STUDENT\_DE) | Office 365 A1 für Schüler und Studenten (STANDARDWOFFPACK\_STUDENT) |
| Office 365 Advanced Compliance\_DE (EQUIVIO\_ANALYTICS\_DE) | Microsoft 365 E5 Compliance (INFORMATION\_PROTECTION\_COMPLIANCE) |
|Microsoft Defender für Office 365 Plan 1)\_DE (ATP\_ENTERPRISE\_DE) |Microsoft Defender für Office 365 (Plan 1) (ATP\_ENTERPRISE) |
| Office 365 Business Essentials\_DE (O365\_BUSINESS\_ESSENTIALS\_DE) | Microsoft 365 Business Basic (O365\_BUSINESS\_ESSENTIALS) |
| Office 365 Business Premium\_DE (O365\_BUSINESS\_PREMIUM\_DE) | Microsoft 365 Business Standard (O365\_BUSINESS\_PREMIUM) |
| Office 365 Business\_DE (O365\_BUSINESS\_DE) | Microsoft 365 Apps for Business (O365\_BUSINESS) |
| Office 365 E1\_DE (STANDARDPACK\_DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 ohne ProPlus\_DE (ENTERPRISEPACKWITHOUTPROPLUS\_DE) | Office 365 E3 ohne ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3\_DE (ENTERPRISEPACK\_DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1\_DE (STANDARDPACK\_DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3\_DE (ENTERPRISEPACK\_DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage\_DE (SHAREPOINTSTORAGE\_DE) | Office 365 Extra File Storage (SHAREPOINTSTORAGE) |
| Office 365 F1\_DE (DESKLESSPACK\_DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus für Lehrpersonal\_DE (OFFICESUBSCRIPTION\_FACULTY\_DE) | Office 365 ProPlus für Lehrpersonal (OFFICESUBSCRIPTION\_FACULTY) |
| Office 365 ProPlus für Schüler und Studenten\_DE (OFFICESUBSCRIPTION\_STUDENT\_DE) | Office 365 ProPlus für Schüler und Studenten (OFFICESUBSCRIPTION\_STUDENT) |
| Office 365 ProPlus\_DE (OFFICESUBSCRIPTION\_DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive for Business (Plan 1)\_DE (WACONEDRIVESTANDARD\_DE) | OneDrive for Business (Plan 1) (WACONEDRIVESTANDARD) |
| OneDrive for Business (Plan 2)\_DE (WACONEDRIVEENTERPRISE\_DE) | OneDrive for Business (Plan 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro für Lehrpersonal\_DE (POWER\_BI\_PRO\_FACULTY\_DE) | Power BI Pro für Lehrpersonal (POWER\_BI\_PRO\_FACULTY) |
| Power BI Pro\_DE (POWER\_BI\_PRO\_DE) | Power BI Pro (POWER\_BI\_PRO) |
| Project Online Essentials\_DE (PROJECTESSENTIALS\_DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium\_DE (PROJECTPREMIUM\_DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional\_DE (PROJECTPROFESSIONAL\_DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Project Plan 3\_DE (PROJECTPROFESSIONAL\_DE) | Project Plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4\_DE (ENTERPRISEWITHSCAL\_DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (Plan 1)\_DE (SHAREPOINTSTANDARD\_DE) | SharePoint Online (Plan 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (Plan 2)\_DE (SHAREPOINTENTERPRISE\_DE) | SharePoint Online (Plan 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (Plan 1)\_DE (MCOIMP\_DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (Plan 1)\_DE (MCOIMP\_DE) | Skype for Business Online (Plan 1) (MCOIMP) |
| Skype for Business Online (Plan 2)\_DE (MCOSTANDARD\_DE) | Skype for Business Online (Plan 2) (MCOSTANDARD) |
| Skype for Business Plus CAL\_DE (MCOPLUSCAL\_DE) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Online Plan 1 für Lehrpersonal\_DE (VISIOONLINE\_PLAN1\_FAC\_DE) | Visio Online Plan 1 für Lehrpersonal (VISIOONLINE\_PLAN1\_FAC) |
| Visio Online Plan 1\_DE (VISIOONLINE\_PLAN1\_DE) | Visio Online Plan 1 (VISIOONLINE\_PLAN1) |
| Visio Online Plan 2 für Lehrpersonal\_DE (VISIOCLIENT\_FACULTY\_DE) | Visio Online Plan 2 für Lehrpersoanl (VISIOCLIENT\_FACULTY) |
| Visio Online Plan 2\_DE (VISIOCLIENT\_DE) | Visio Online Plan 2 (VISIOCLIENT) |
| Visio Plan 1\_DE (VISIOONLINE\_PLAN1\_DE) | Visio Plan 1 (VISIOONLINE\_PLAN1) |
| Visio Plan 2\_DE (VISIOCLIENT\_DE) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Wie erhalte ich Hilfe von Microsoft, um zu einer neuen Region zu migrieren, oder Antworten auf meine Support-Fragen?

Wenden Sie sich bei Fragen an uns oder an Ihren Partner:

- Bei Fragen zu Azure können Sie [neue Supportanfragen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) im Azure-Portal einreichen.
- Fragen zu Office 365 können Sie über den Link &quot;Benötigen Sie Hilfe?&quot; im [Microsoft 365 Admin Center](https://portal.office.de/) übermitteln.
- Dynamics 365 Customer Engagement- und Power BI-Kunden, die auch über Office 365 verfügen, können Fragen über den Link &quot;Benötigen Sie Hilfe?&quot; im [Microsoft 365 Admin Center](https://portal.office.de/) übermitteln. Die Dynamics 365 Customer Engagement-Supportoptionen befinden sich [hier](https://docs.microsoft.com/dynamics365/get-started/support/). Die Power BI-Supportoptionen befinden sich [hier](https://powerbi.microsoft.com/support/).


## <a name="next-step"></a>Nächster Schritt

[Für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
