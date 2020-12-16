---
title: Was hat sich für die Migration zu Office 365 Diensten in den neuen deutschen Rechenzentrums Regionen geändert?
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
description: 'Zusammenfassung: Hier erfahren Sie, was sich bei der Umstellung von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) auf Office 365 Dienste im neuen rechenzentrumsbereich geändert hat.'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688622"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Was hat sich für die Migration zu Office 365 Diensten in den neuen deutschen Rechenzentrums Regionen geändert?

Mandanten Migrationen sind so konzipiert, dass Sie minimale Auswirkungen auf Administratoren und Benutzer haben. Allerdings gibt es unterschiedliche Überlegungen für jede Workload. Lesen Sie die folgenden Abschnitte, um die Migrationserfahrung für die Arbeitsauslastungen besser zu verstehen.

Im folgenden finden Sie die wichtigsten Unterschiede zwischen Microsoft Cloud Deutschland und Office 365 Diensten in den neuen Bereichen des Rechenzentrums in Deutschland.

| Kategorie | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Office 365-Dienste in den neuen deutschen Rechenzentrumsregionen |
|:-------|:-----|:-------|
| Microsoft 365-Dienste, die mit nur einem Office 365-Mandanten als Abonnement verfügbar sind | 15 Dienste | 29 Dienste <br><br> Weitere Informationen finden Sie unter [Was ist die Dienstverfügbarkeit zwischen den verschiedenen Office 365 Cloud Service-angeboten?](ms-cloud-germany-transition.md#serv-avail). |
| Neue Features | Es sind keine neuen Features verfügbar. | Neue Features stehen im Einklang mit Office 365 Diensten zur Verfügung. |
| Datentreuhänder | Ja | Nein |
| Mandantenübergreifende Zusammenarbeit mit Office 365-Mandanten weltweit | Nein | Ja |
| Kundendatenhaltung | Kundendaten werden ausschließlich in deutschen Rechenzentren gespeichert. | Die folgenden Kundendaten werden von Microsoft ausschließlich in Deutschland gespeichert: <ul><li> Exchange Online Postfachinhalt (e-Mail-Text, Kalendereinträge und der Inhalt von e-Mail-Anlagen) </li><li> SharePoint Online Websiteinhalt und die auf dieser Website gespeicherten Dateien und Dateien, die in OneDrive für Unternehmen hochgeladen wurden </li></ul> |
| Geltende Nutzungsbedingungen | [Online Dienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) mit dieser [Ergänzung](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Onlinedienstbedingungen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Was sich nicht ändert:

- Die anfängliche Mandantendomäne (beispielsweise `contoso.onmicrosoft.de` ) mit Mandanten-ID (GUID) und benutzerdefinierten Domänen bleibt nach der Migration erhalten. 

- Authentifizierungsanforderungen für Ressourcen, die zu Office 365 Diensten migriert werden, werden vom Azure-Authentifizierungsdienst () von Office 365 Services erteilt `login.microsoftonline.com` . Während der Migration werden Ressourcen, die noch in Office 365 Deutschland verbleiben, vom vorhandenen Deutschland Azure-Dienst authentifiziert ( `login.microsoftonline.de` ).

Überlegungen zur Kenntnis:

- Bei verwalteten Domänenkonten muss nach dem Kopieren des anfänglichen Azure Active Directory (Azure AD)-Mandanten (der erste Schritt Azure AD Migration zum Office 365 Dienste Azure AD Dienst), Kennwortänderungen, Änderungen an SSPR (Self-Service Password Reset) und Kennwortzurücksetzungen durch Administratoren von den Office 365 Dienst Portalen ausgeführt werden. Anforderungen zum Aktualisieren von Kennwörtern aus dem Deutschland-Dienst können an dieser Stelle nicht erfolgreich sein, da der Azure AD Mandanten zu Office 365 Diensten migriert wurde. Zurücksetzen von Kennwörtern der Verbunddomäne sind nicht betroffen, da diese im lokalen Verzeichnis abgeschlossen werden.

- Azure-Anmeldungen werden im Portal angezeigt, in dem der Benutzer versucht, darauf zuzugreifen. Überwachungsprotokolle sind nur über den Office 365-Dienste-Endpunkt nach dem Übergang verfügbar. Vor der Migration bis zum Abschluss der Migration sollten Sie die Anmelde-und Überwachungsprotokolle aus dem Microsoft Cloud Deutschland-Portal speichern.

- Zurücksetzen von Kennwörtern, Kennwortänderungen, Kennwortzurücksetzung durch einen Administrator für verwaltete Organisationen (die nicht Active Directory Verbunddienste verwenden) müssen über das Office 365-Dienste-Portal ausgeführt werden. Versuche von Benutzern, die auf Microsoft Cloud Deutschland-Portale zugreifen, um Kennwörter zurückzusetzen, werden nicht ausgeführt.

- Allgemeine Datenschutzverordnung (dsgvo) Datensubjekt Anforderungen (DSRs) werden über das Azure-Verwaltungsportal von Office 365 Services für zukünftige Anforderungen ausgeführt. Alle Legacy-oder nicht-Kunden-Diagnosedaten, die in Microsoft Cloud Deutschland wohnhaft sind, werden vor oder vor 30 Tagen gelöscht.

## <a name="subscriptions--licenses"></a>Abonnements & Lizenzen

- Office 365-und Dynamics-Abonnements von Microsoft Cloud Deutschland werden mit der Azure AD Verschiebung in die Region Deutschland umgestellt. Die Organisation wird dann aktualisiert, um neue Office 365-Dienste-Abonnements widerzuspiegeln. Während des kurzen Abonnement Übertragungsprozesses werden Änderungen an Abonnements blockiert.

- Während der Übergang des Mandanten zu Office 365 Diensten erfolgt, werden die Deutschland-spezifischen Abonnements und Lizenzen mit neuen Office 365-Dienst angeboten standardisiert. Entsprechende Office 365-Dienste-Abonnements werden für die übertragenen Deutschland-Abonnements erworben. Benutzer mit Deutschland-Lizenzen werden Office 365 Dienstlizenzen zugewiesen. Nach Abschluss werden Legacy Germany-Abonnements storniert und aus dem aktuellen Office 365-Dienste-Mandanten entfernt.

- Nach der Migration der einzelnen Arbeitslasten werden aufgrund der neuen Office 365-Dienste-Abonnements zusätzliche Funktionen über die Office 365 Dienste (wie Microsoft Planner und Microsoft Flow) zur Verfügung gestellt. Wenn es für Ihre Organisation geeignet ist, kann der Mandanten-oder Lizenzierungs Administrator neue Dienstpläne beim Planen der Änderungsverwaltung deaktivieren, um die neuen Dienste einzuführen. Anleitungen zum Deaktivieren von Dienstplänen, die den Lizenzen von Benutzern zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- Exchange-Ressourcen-URLs Übergang vom Legacy Deutschland Endpunkt `outlook.office.de` zum Office 365-Dienste `outlook.office365.com` -Endpunkt nach der Migration. Ihre Benutzer können über die Legacy-URL auf Ihr migriertes Postfach zugreifen, bis die Migration abgeschlossen ist. Kunden sollten die Benutzer so schnell wie möglich auf die neue URL umstellen, nachdem die Exchange-Migration beginnt, um das Ausscheiden in der deutschen Umgebung zu verhindern. Die Office 365-Dienste-URLs für Outlook-Dienste werden erst nach Beginn der Exchange-Migration verfügbar.

- Postfächer werden als Back-End-Prozess migriert. Benutzer in Ihrer Organisation können sich während des Übergangs entweder in Microsoft Cloud Deutschland oder in der deutschen Region befinden und sind Teil derselben Exchange-Organisation (in derselben globalen Adressliste).

- Benutzer des Outlook Web App, die über eine URL auf den Dienst zugreifen, in der sich Ihr Postfach nicht befindet, erhalten eine zusätzliche Authentifizierungsaufforderung. Wenn sich das Postfach des Benutzers beispielsweise im Office 365 Dienste befindet und die Outlook Web App-Verbindung des Benutzers den Legacy Endpunkt verwendet `outlook.office.de` , authentifiziert sich der Benutzer zunächst bei `login.microsoftonline.de` und dann bei `login.microsoftonline.com` . Wenn die Migration abgeschlossen ist, kann der Benutzer auf die neue URL ( `https://outlook.office365.com` ) zugreifen, und es wird nur die einzelne erwartete Anmeldeanforderung angezeigt. 

## <a name="office-services"></a>Office-Dienste

Auf Office Online Dienste kann über `office.de` vor und während des Übergangs zugegriffen werden. Nachdem die Postfächer der Benutzer auf die Office 365 Dienste umgestellt wurden, sollten Benutzer mit der Verwendung von Office 365-Dienste-URLs beginnen. Wenn nachfolgende Arbeitslasten zu Office 365 Diensten migriert werden, wird die Schnittstelle aus dem Office.com-Portal mit der Arbeit beginnen.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Back-End-Exchange Online Schutzfeatures (EoP) werden in die Region New Germany kopiert.
- Benutzer von Office 365 Security and Compliance Center müssen im Rahmen der Migration zur Verwendung globaler URLs wechseln `https://protection.office.com` .

## <a name="skype-for-business-online"></a>Skype for Business Online

Bestehende Skype für Business Online Kunden werden auf Microsoft Teams umgestellt. Weitere Informationen finden Sie unter [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video wird am 1. März 2021 zurückgezogen, und Office 365 Video wird nicht unterstützt, nachdem die Migration von SharePoint Online in die neuen Regionen des deutschen Rechenzentrums abgeschlossen ist. Inhalte aus Office 365 Video werden im Rahmen der Migration von SharePoint Online migriert. Videos in Office 365 Video werden jedoch nach der SharePoint-Migration nicht in der Benutzeroberfläche von Office 365 Video wiedergegeben. Weitere Informationen zur Migrations Zeitachse finden Sie unter [Office 365 Video Übergang zu Microsoft Stream (klassisch) Overview](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Nächster Schritt

[Grundlegendes zu Migrationsphasen Aktionen und Auswirkungen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)

Navigieren durch den Übergang:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
