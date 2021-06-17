---
title: Was wird sich nach der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen ändern
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Zusammenfassung: Verstehen, was sich bei der Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen verändert hat.'
ms.openlocfilehash: e503df16cfdbe0985e635b07cb6b4a45bc55d367
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930403"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Was wird sich nach der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen ändern

Mandantenmigrationen sind so angelegt, dass sie nur minimale Auswirkungen auf Nutzer und Administratoren haben. Allerdings gibt es unterschiedliche Überlegungen für jedes Workload. Überprüfen Sie bitte die folgenden Abschnitte, um die Migrationsumgebung für die Workloads besser zu verstehen.

Folgend kommen die wichtigsten Unterschiede zwischen Microsoft Cloud Deutschland und Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.

| Kategorie | Microsoft Cloud Deutschland | Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen |
|:-------|:-----|:-------|
| Microsoft 365-Dienste, die mit nur einem Office 365-Mandanten als Abonnement verfügbar sind | 15 Dienste | 29 Dienste <br><br> Weitere Informationen finden Sie unter [Wie hoch ist die Dienstverfügbarkeit der verschiedenen Office 365-Clouddienstangebote?](ms-cloud-germany-transition.md#serv-avail). |
| Neue Features | Es werden keine neuen Features verfügbar sein. | Neue Funktionen werden in Übereinstimmung mit den Office 365-Diensten bereitgestellt. |
| Datentreuhänder | Ja | Nein |
| Mandantenübergreifende Zusammenarbeit mit Office 365-Mandanten weltweit | Nein | Ja |
| Kundendatenhaltung | Kundendaten werden nur in deutschen Rechenzentren gespeichert. | Microsoft wird die folgenden Kundendaten ausschließlich in Deutschland speichern: <ul><li> Exchange Online-Postfachinhalte (E-Mail-Texte, Kalendereinträge und der Inhalt von E-Mail-Anlagen) </li><li> Microsoft Office SharePoint Online-Websiteinhalte und die auf der Website gespeicherten Dateien und auf OneDrive for Business hochgeladene Dateien </li></ul> |
| Geltende Nutzungsbedingungen | [Onlinedienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) mit diesem [Zusatz](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Onlinedienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Was sich nicht ändert:

- Die ursprüngliche Domäne des Mandanten (wie z.B. `contoso.onmicrosoft.de`) mit Mandanten-ID (GUID) und benutzerdefinierten Domänen wird nach der Migration erhalten bleiben. 

- Authentifizierungsanforderungen für Ressourcen, die zu Microsoft Office 365-Diensten migriert werden, werden von Office 365-Diensten den Azure-Authentifizierungsdienst (`login.microsoftonline.com`) gewährt bekommen. Während der Migration werden Ressourcen, die noch in Office 365 Deutschland verbleiben, vom vorhandenen deutschen Azure-Dienst (`login.microsoftonline.de`) authentifiziert.

Zu beachtenden Überlegungen:

- Bei verwalteten Domänenkonten müssen, nach dem Kopieren des anfänglichen Azure Active Directory (Azure AD)-Mandanten abgeschlossen ist (was der erste Schritt bei der Migration von Azure AD zu Office 365-Diensten Azure AD-Dienst ist), Kennwortänderungen, Änderungen an den Self-Service-Kennwortzurücksetzungen (SSPR), und Kennwortzurücksetzungen durch Administratoren über die Office 365-Service Portal erstellt werden. Die Anforderungen des Deutschland-Diensts zum Aktualisieren werden ab diesem Punkt nichtmehr erfolgreich sein, weil der Azure AD-Mandant zu den Office 365-Diensten migriert wurde. Die Zurücksetzung von Kennwörtern für die Verbunddomänen sind nicht betroffen, weil diese im lokalen Verzeichnis abgeschlossen sind.

- Azure-Anmeldungen werden im Portal angezeigt, in dem der Benutzer sich um den Zugriff versucht. Überwachungsprotokolle stehen nur vom Office 365-Dienstendpunkt nach dem Übergang zur Verfügung. Sie sollten Anmelde- und Überwachungsprotokolle vom Microsoft Corporation Deutschland-Portal speichern, bevor Sie zum Abschluss der Migration gehen.

- Das Zurücksetzen und Ändern von Kennwörtern und Zurücksetzen von Kennwörtern durch einen Administrator für verwaltete Organisationen (die nicht Active Directory-Verbunddienste (AD FS) verwenden) muss mittels des Office 365-Dienstportals durchgeführt werden. Versuche von Benutzern auf Microsoft Cloud Deutschland-Portale zuzugreifen, um Kennwörter zurückzusetzen, werden fehlschlagen.

- Allgemeine Datenbetreffesanforderungen (DSRs) für die Datenschutzbestimmungen (DSGVO) werden im Office 365-Dienste Azure-Verwaltungsportal für zukünftige Anforderungen ausgeführt. Alle älteren oder Nicht-Kunden-Diagnosedaten, die sich in Microsoft Cloud Deutschland befinden, werden spätestens nach 30 Tagen gelöscht.

## <a name="subscriptions--licenses"></a>Lizenzen und Abonnements

- Office 365 Dynamics-Abonnements von Microsoft Cloud Deutschland werden mit dem Azure AD-Umzug in die Region Deutschland umgestellt. Die Organisation wird dann aktualisiert, um die neuen Office 365-Dienste widerzuspiegeln. Während des kurzen Übertragungsprozesses für das Abonnement sind Änderungen an den jeweiligen Abonnements blockiert.

- Während der Umstellung des Mandanten auf Office 365-Dienste werden die für Deutschland spezifischen Abonnements und Lizenzen durch neue Office 365-Dienstangebote standardisiert. Die entsprechenden Abonnements für Office 365-Dienste werden für die übertragenen Deutschland-Abonnements erworben. Benutzern mit Deutschland-Lizenzen werden Lizenzen für Office 365-Dienste zugewiesen. Alte Deutschland-Abonnements werden nach ihrem Abschluss gelöscht und aus dem aktuellen Office 365-Dienstmandanten entfernt.

- Nach der Migration der einzelnen Workloads wird zusätzliche Funktionalität wegen der neuen Abonnements für Office 365-Dienste mittels der Office 365-Dienste zur Verfügung gestellt (wie z.B. des Microsoft Planners und Microsoft Flows). Wenn dies für Ihre Organisation geeignet ist, kann der Mandant oder der Lizenzierungsadministrator, während Sie das Änderungsmanagement für die Einführung der neuen Dienste planen, neue Dienste deaktivieren. Informationen über das Deaktivieren von Dienstplänen, die den Benutzerlizenzen zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste während des Zuweisens von Benutzerlizenzen](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- Exchange-Ressource-URLs wechseln vom alten Deutschland-Endpunkt `outlook.office.de` zu den Office 365-Dienstendpunkt `outlook.office365.com` nach der Migration. Ihre Benutzer können auf ihr migriertes Postfach zugreifen, indem sie das alte URL benutzen, bis die Migration abgeschlossen ist. Kunden sollten möglichst bald nach der die Exchange-Migration anfängt Benutzer zu der neuen URL wechseln, um die Einstellung der Deutschland-Umgebung nicht negativ zu beeinflussen. Die URLS der Office 365-Dienste für Outlook-Dienste werden erst nach dem die Exchange-Migration angefangen hat zur Verfügung gestellt.

- Postfächer werden als Backend-Prozess migriert. Benutzer in Ihrer Organisation befinden sich während des Übergangs entweder in Microsoft Cloud Deutschland oder in der Region Deutschland und sind Teil derselben Exchange-Organisation (in derselben globale Adressliste).

- Benutzern der Outlook Web App, die auf den Dienst mittels URL, in der sich ihr Postfach nicht befindet, zugreifen, wird eine zusätzliche Authentifizierungsaufforderung angezeigt. Wenn z. B. das Postfach des Benutzers in den Office 365-Diensten ist und die Outlook Web App-Verbindung des Benutzers den alten Endpunkt `outlook.office.de` verwendet, wird sich der Benutzer erst bei `login.microsoftonline.de` und dann bei `login.microsoftonline.com` authentifizieren. Wenn die Migration abschlossen ist, kann der Benutzer auf die neue URL (`https://outlook.office365.com`) zugreifen, und ihm wird nur die einzige erwartete Anmeldeanforderung angezeigt. 

## <a name="sharepoint-online"></a>SharePoint Online

In SharePoint Online und OneDrive for Business können Sie Elemente über Outlook freigeben. Nach dem Klicken auf die Outlook-Schaltfläche wird ein Link für die Freigabe erstellt und in eine neue Nachricht in Outlook Web App eingefügt.

Die Freigabe von Elementen in SharePoint Online und OneDrive for Business über Outlook funktioniert nach dem Abschluss der Migration von SharePoint Online nicht mehr. Dieses Problem ist bereits bekannt. Da diese Outlook-Funktion allerdings bereits veraltet ist, ist die Behebung des Problems erst geplant, wenn die Unterstützung beendet wurde.

## <a name="office-services"></a>Office-Dienste

Auf Office-Online-Dienste kann man während und bevor des Übergangs mittels `office.de` zugreifen. Nachdem die Postfächer der Benutzer zu den Office 365-Diensten übergegangen sind, sollten Benutzer beginnen die Office 365-Dienste zu verwenden. Während nachfolgende Workloads zu Office 365-Diensten migrieren, wird ihre Benutzeroberfläche vom office.com-Portal zu arbeiten anfangen.

Der Dienst „Zuletzt verwendet“ (most recently used, MRU) in Office ist eine Umstellung des Microsoft Cloud Deutschland-Dienstes zu Office 365-Globalen Diensten, keine Migration.  Nach der Migration vom Office.com-Portal werden nur MRU-Links von der Seite der Office 365-Dienste sichtbar sein. MRU-Links vom Microsoft Cloud Deutschland-Dienst werden nicht als MRU-Links in Office 365-Globalen Diensten sichtbar sein. In Office 365-Globalen Diensten kann auf MRU-Links erst zugegriffen werden, nachdem die Mandantenmigration Phase 9 erreicht hat.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Die Funktionen der Back-End Exchange Online Protection (EOP) werden in die neue Region Deutschland kopiert.
- Die Benutzer des Office 365 Security und Compliance Center müssen im Rahmen der Migration zur Verwendung globaler URLs, `https://protection.office.com`, wechseln.

## <a name="skype-for-business-online"></a>Skype for Business Online

Bestehende Skype für Business Online Kunden werden auf Microsoft Teams umgestellt. Weitere Informationen finden Sie unter [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here).

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video wird am 1. März 2021 eingestellt, und Office 365 Video wird nach Abschluss der Migration von SharePoint Online in die neuen deutschen Rechenzentren nicht mehr unterstützt. Inhalte aus Office 365 Video werden im Rahmen der Migration von SharePoint Online migriert. Videos in Office 365 Video werden jedoch nach der SharePoint-Migration nicht mehr in der Office 365 Video-Benutzeroberfläche wiedergegeben. Weitere Informationen zur Zeitachse der Migration finden Sie unter [Office 365 Video-Übergang zur Microsoft Stream (klassisch) Übersicht](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Nächster Schritt

[Phasen, Aktionen und Auswirkungen der Migration verstehen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
