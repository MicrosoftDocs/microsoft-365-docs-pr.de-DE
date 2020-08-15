---
title: Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
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
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690714"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen


>[!Note]
>Dieser Artikel gilt nur für berechtigte Kunden von Microsoft Cloud Germany/Deutschland.
>

## <a name="cloud-service-offerings-in-germany"></a>Cloud-Serviceangebote in Deutschland

Im August 2018 haben wir unsere Absicht angekündigt, die gesamte Microsoft-Cloud – Azure, Office 365, Dynamics 365 und Power Plattform – aus neuen Cloud-Regionen in Deutschland bereitzustellen, um die digitale Transformation unserer Kunden noch besser zu unterstützen. Wir haben im August 2019 angekündigt, dass wir die neuen Cloud-Regionen in Deutschland für erste Kunden eröffnen. Wir haben die Verfügbarkeit von Azure im August angekündigt und Office 365 wurde im Dezember verfügbar.  Dynamics 365 und Power Platform werden voraussichtlich im ersten Quartal 2020 verfügbar sein.  

Die neuen Regionen sind so konzipiert, dass sie sich ständig an die veränderten Anforderungen deutscher Kunden anpassen. Dank der Verbindung zu unserem weltweiten Cloud-Netzwerk bieten wir, neben dem vollen Funktionsumfang, stetige Erweiterung mit neuen Funktionen zudem die Möglichkeit den Anforderung nach lokaler Datenhaltung in Deutschland gerecht zu werden.

## <a name="moving-to-the-new-german-regions"></a>Umstieg auf die neuen deutschen Regionen

Bestehende Kunden der Microsoft Cloud Germany (Microsoft Cloud Deutschland) können nun mit der Migration ihrer Office 365, Dynamics 365 Customer Engagement und Power Platform BI beginnen.  Der erste Schritt besteht darin, [sich für die von Microsoft geleiteten Migration in unsere neuen deutschen Rechenzentrumsregionen anzumelden](https://aka.ms/office365germanymoveoptin).

Die Migrationen für Organisationen, die sich für den von Microsoft geleiteten Ansatz anmelden, werden voraussichtlich in 2020 durchgeführt. Als Ergebnis der Migration werden die wichtigsten Kundendaten und -abonnements in die neuen deutschen Regionen verschoben. 

Die folgenden Dienste werden als Teil des von Microsoft geleiteten Ansatzes migriert:

- Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business
- Skype for Business Online

Während der Migration von Microsoft Cloud Deutschland in die deutschen Rechenzentrumsregionen werden bestehende Skype for Business Online Kunden auf Microsoft Teams umgestellt. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

- Office 365-Gruppen
- Dynamics 365 / Power Platform

Die Voraussetzungen und Auswirkungen der Migration für diese Dienste sind im Artikel [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin) beschrieben.

Office 365 Video wird am 1. März 2021 eingestellt. Wenn Sie Ihren Office 365-Mandanten in die Regionen der neuen deutschen Rechenzentren migrieren, wird Office 365 Video nach Abschluss der SharePoint Online-Migration nicht unterstützt. [Weitere Informationen](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Wie Sie sich auf die Migration auf Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen vorbereiten können

Der erste Schritt besteht darin, Microsoft zu benachrichtigen, dass Sie uns Ihr Einverständniszum Migrieren Ihres Abonnements und der Daten aus der Microsoft-Cloud Deutschland auf Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen geben.  Anweisungen hierzu finden Sie im [Abonnementsprozess](ms-cloud-germany-migration-opt-in.md).

- Alle Kunden mit MIgrationsbedarf müssen die Konnektivität zum weltweiten [Office 365-URLs und -IP-Adressen](urls-and-ip-address-ranges.md), die die neuen deutschen Rechenzentrumsregionen haben, überprüfen.
- Überprüfen Sie die Beschreibung der Office 365-Plattformdienste, um zu verstehen, welche Funktionen und Dienste nach der Fertigstellung in der Region für Ihre Organisation verfügbar werden. 
- Im Rahmen der Migration werden bezahlte Abonnements überführt.  Testabonnements können nicht migriert werden.

Mandantenmigrationen werden als Back-End-Dienste ausgeführt, wobei nur minimale Interaktionen von Kunden erforderlich sind.  Alle möglicherweise auf Kundenseite erforderlichen Aufgaben und der allgemeine Stand der Migration werden während des Migrationsprozesses über das Message Center mitgeteilt.  Zu den kundenseitig erforderlichen Maßnahmen zählen beispielsweise durch Kunden verwaltete DNS-Updates oder die Neukonfiguration des Hybrid-Setups für Kunden von Exchange-Hybridlösungen.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Die Kundenerfahrung während der Migration auf Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen

Mandantenmigrationen sind so angelegt, dass sie nur minimale Auswirkungen auf Nutzer und Administratoren haben.  Allerdings gibt es unterschiedliche Überlegungen für jede Workload.  

### <a name="azure-active-directory"></a>Azure Active Directory

Office-/ Dynamics-Abonnements von Microsoft Cloud Deutschland werden mit dem Azure Active Directory-Umzug (Azure AD) in die Region Deutschland umgestellt. Die Organisation wird dann aktualisiert, um die neuen weltweiten Dienste widerzuspiegeln. Während des kurzen Übertragungsprozesses für das Abonnement werden Änderungen an den jeweiligen Abonnements blockiert.

### <a name="exchange-online"></a>Exchange Online

Exchange Online Hybrid-Kunden müssen den Hybrid-Konfigurationsassistenten erneut ausführen, um die Konfiguration vor Ort gegen Microsoft Cloud Deutschland vor der Umstellung zu aktualisieren und die HCW nach der Bereinigung gegen den weltweiten Service erneut auszuführen. Für Kunden mit benutzerdefinierten Domänen werden ggf. weitere DNS-Updates erforderlich sein.

Postfächer werden als Back-End-Prozess migriert. Benutzer in Ihrer Organisation befinden sich während des Übergangs entweder in Microsoft Cloud Deutschland oder in der Region Deutschland und sind Teil derselben Exchange-Organisation (GAL).

### <a name="exchange-online-protection"></a>Exchange Online Protection

Die Backend-Funktionen von Exchange Online Protection werden in die neue Region Deutschland kopiert.

### <a name="sharepoint-online"></a>SharePoint Online

Nach Abschluss der SharePoint Online-Migration in die Region Deutschland werden Datenindizes neu erstellt. Funktionen, die von Suchindizes abhängig sind, können betroffen sein, bis die Neuindizierung abgeschlossen ist.

Vorhandene SharePoint.de-URLs werden für übertragene Organisationen beibehalten.

### <a name="onedrive-for-business"></a>OneDrive for Business

Nach Abschluss der OneDrive for Business-Migration in die Region Deutschland werden Datenindizes neu erstellt. Funktionen, die von Suchindizes abhängig sind, können betroffen sein, bis die Neuindizierung abgeschlossen ist.

### <a name="skype-for-business-online"></a>Skype for Business Online

Bestehende Skype für Business Online Kunden werden auf Microsoft Teams umgestellt. Weitere Informationen finden Sie unter [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home).

### <a name="office-365-video"></a>Office 365 Video
Inhalte aus Office 365 Video werden im Rahmen der SharePoint Online-Migration migriert. Office 365 Video wird jedoch eingestellt. Office 365 Video wird nach Abschluss der SharePoint Online-Migration in die neuen deutschen Rechenzentren nicht mehr unterstützt. Videos in Office 365 Video werden nach der SharePoint-Migration nicht mehr in der Office 365 Video-Benutzeroberfläche wiedergegeben.

Microsoft Stream wird nicht für Microsoft Deutschland bereitgestellt, und es gibt derzeit keine Zeitachse für die Bereitstellung von Microsoft Stream in den neuen deutschen Rechenzentren. Daher gibt es in dieser Region keine Migrationstools für Office 365 Video in Microsoft Stream. Wenn Sie Ihre Inhalte beibehalten möchten, müssen Sie Inhalte vor dem 1. März 2021 manuell herunterladen oder verlegen. [Weitere Informationen](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Wichtigste Unterschiede zwischen Microsoft Cloud Germany (Microsoft Cloud Deutschland) und Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen


|| Microsoft Cloud Deutschland | Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen |
|:-------|:-----|:-----|
| Microsoft 365-Dienste, die mit nur einem Office 365-Mandanten als Abonnement verfügbar sind | 15 Dienste (siehe Bezug) | 29 Dienste (siehe Bezug) |
| Neue Features | Es sind keine neuen Features verfügbar. | Neue Funktionen werden in Übereinstimmung mit den globalen Office 365-Diensten bereitgestellt. |
| Datentreuhänder | Ja | Nein |
| Mandantenübergreifende Zusammenarbeit mit Office 365-Mandanten weltweit | Nein | Ja |
| Kundendatenhaltung | Kundendaten werden nur in deutschen Rechenzentren gespeichert. | Die folgenden Kundendaten werden von Microsoft ausschließlich in Deutschland gespeichert: Exchange Online-Postfachinhalte (E-Mail-Text, Kalendereinträge und der Inhalt von E-Mail-Anlagen), SharePoint Online-Websiteinhalte und die Dateien, die auf dieser Website gespeichert sind, und Dateien, die in OneDrive for Business hochgeladen wurden. |
| Geltende Nutzungsbedingungen | [Onlinedienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) mit [Zusatz](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Onlinedienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-migration-required"></a>Ist die Migration erforderlich?

Microsoft bietet eine Mandantenmigration für Office 365 von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen ohne Aufpreis.  Wir empfehlen Ihnen dringend, sich für die Migration zu den neuen deutschen Rechenzentrumsregionen anzumelden, aber wir werden weiterhin die erforderlichen Sicherheitsupdates für die Region „Microsoft Cloud Deutschland“ bereitstellen.  

Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen bieten zusätzliche Vorteile:

- Sie bieten marktgerechte Preise für [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)und [Power BI](https://powerbi.microsoft.com/pricing/). 
- Sie sind mit einem globalen Microsoft-Netzwerk verbunden und bieten eine Vielzahl von Netzwerk-Edge-Websites, Peering-Standorten und Übergabepunkte, um überall auf der Welt eine sichere Benutzererfahrung zur ermöglichen. 
- Sie helfen Ihnen, die Anforderungen an die lokale Datenhaltung innerhalb von Deutschland zu erfüllen. 
- Sie bieten unser umfassendes globales Cloud-Angebot, einschließlich der neuesten Version unserer Dienste und neuer Funktionen wie Microsoft Teams und Multi-Geo in Office 365. Hier finden Sie die Vergleiche unserer Produkte nach Region für [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) und [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Sie bieten die vollständige Funktionalität, Sicherheit auf Unternehmensniveau und umfassende Funktionen, die Kunden bei der Einhaltung behördlicher oder eigener Vorschriften unterstützen. 
- Sie sind im Rahmen vorhandener Verträge für Onlinedienstleistungen verfügbar.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Wie hoch ist die Dienstverfügbarkeit der verschiedenen Office 365-Clouddienstangebote?

Die folgenden 15 Dienste sind im Clouddienstangebot von Microsoft Cloud Germany (Microsoft Cloud Deutschland) verfügbar.  Microsoft Cloud Germany werden keine neuen Dienste hinzufügen.

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
12. Skype for Business
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 ProPlus
15. Outlook Mobile

Derzeit sind 29 Dienste als Bestandteil von Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verfügbar.  In Übereinstimmung mit den globalen Office 365-Diensten werden fortlaufend neue Features und Dienste bereitgestellt.

1. Exchange Online
2. Kunden-Lockbox (Exchange Online)
3. Gruppen (moderne Gruppen)
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
14. Kunden-Lockbox (SharePoint Online)
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (während der Migration erfolgt ein Umstieg zu Microsoft Teams)
18. Cloud PBX
19. PSTN-Konferenzen
20. PSTN-Anrufe
21. Microsoft Teams
22. Administrator-Berichte/ Verwendungsberichte
23. Word Online, Excel Online, PowerPoint, OneNote und Visio Online
24. Planner
25. Sway
26. Office 365 ProPlus
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + Intune + Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Wann wird die Migration durchgeführt?

#### <a name="azure"></a>Azure 

Sie können [die Migration von](https://docs.microsoft.com/azure/germany/germany-migration-main) Azure-Ressourcen zu einer anderen Region bereits starten. Wenn Sie über Azure mit Office 365, Dynamics 365 und/oder Power BI verfügen, führen Sie die folgenden Schritte aus.

#### <a name="office-365"></a>Office 365

[Melden Sie sich an](https://aka.ms/office365germanymoveoptin) für noch heute für Migration durch Microsoft an. Wenn wir bereit sind, Ihre Migration zu starten, werden wir Sie über das [Message Center](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) im Microsoft 365 Admin Center informieren.

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 und Power BI

Melden Sie sich noch heute für die von Microsoft gesteuerte Migration für [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) und [Power BI](https://aka.ms/PBIOptIn) an. Wenn wir bereit sind, Ihre Migration zu starten, werden wir Sie über das [Message Center](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) im Microsoft 365 Admin Center informieren.

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>Werden die Preise für die von mir verwendeten Office-Dienste geändert?

Ja, die Preise in den globalen Microsoft-Cloudbereichen (einschließlich der neuen Rechenzentrumsregionen) sind im Allgemeinen niedriger.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Wie erhalte ich Hilfe von Microsoft, um zu einer neuen Region zu migrieren, oder Antworten auf meine Support-Fragen?

Wenn Sie Fragen haben, können Sie uns wie folgt oder über Ihren Partner kontaktieren:

- Für Azure können Sie [neue Supportanfragen](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) im Azure-Portal senden.
- Für Office 365 übermitteln Sie uns Ihre Fragen über den Link „Benötigen Sie Hilfe?“ im [Microsoft 365 Admin Center](https://portal.office.de/).
- Für Dynamics 365 Customer Engagement- und Power BI-Kunden, die auch Office 365 besitzen, senden Sie uns Ihre Fragen über „Benötigen Sie Hilfe?“ im [Microsoft 365 Admin Center](https://portal.office.de/). Die Dynamics 365 Customer Engagement-Supportoptionen befinden sich [hier](https://docs.microsoft.com/dynamics365/get-started/support/). Die Power BI-Supportoptionen befinden sich [hier](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Weitere Informationen

- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](https://aka.ms/office365germanymoveoptin)
- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365endpoints)
- [Office 365 Hybrid-Konfigurationsassistent](https://aka.ms/HybridWizard)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
