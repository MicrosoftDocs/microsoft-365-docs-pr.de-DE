---
title: Aktionen und Auswirkungen der Migrationsphasen für die Migration von Microsoft Cloud Deutschland (generell)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Zusammenfassung: Verstehen der Aktionen und Auswirkungen der Migrationsphasen für die Verschiebung von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.'
ms.openlocfilehash: 1da3ff6b3347d0e996b017aa1f6243fd724ffccd
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454407"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Aktionen und Auswirkungen der Migrationsphasen für die Migration von Microsoft Cloud Deutschland (generell)

Mandanten-Migrationen von Microsoft Cloud Deutschland in die Region Deutschland der Office 365-Dienste von Microsoft werden als eine Reihe von Phasen und deren konfigurierten Aktionen für jeden Workload ausgeführt. Diese Abbildung zeigt die neun Phasen der Migration in die neuen deutschen Rechenzentren.

![Die neun Phasen der Migration in die neuen deutschen Rechenzentren](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Die Phasen und ihre Aktionen stellen sicher, dass kritische Daten und Erfahrungen zu den Office 365-Diensten migriert werden. Nachdem Ihr Mandant der Migrations-Warteschlange hinzugefügt wurde, wird jeder Workload als eine Reihe von Schritten abgeschlossen, die auf dem Backend-Dienst ausgeführt werden. Einige Workloads erfordern möglicherweise Aktionen des Administrators (oder Benutzers), oder die Migration kann die Verwendung der ausgeführten Phasen beeinflussen, die unter [Wie ist die Migration organisiert?](ms-cloud-germany-transition.md#how-is-the-migration-organized) diskutiert werden.

Die folgenden Abschnitte enthalten Aktionen und Auswirkungen für Workloads, während sie die verschiedenen Phasen der Migration durchlaufen. Überprüfen Sie die Tabellen und stellen Sie fest, welche Aktionen oder Auswirkungen auf Ihre Organisation zutreffen. Stellen Sie sicher, dass Sie vorbereitet sind, die Schritte in den jeweiligen Phasen wie erforderlich auszuführen. Wenn die erforderlichen Schritte nicht ausgeführt werden, kann dies zu einem Ausfall des Dienstes führen und der Abschluss der Migration zu den Office 365-Diensten kann sich verzögern.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Phase 4 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| SharePoint und OneDrive werden überführt. | SharePoint und OneDrive werden in dieser Phase von Microsoft Cloud Deutschland zu Office 365-Diensten migriert. Bestehende URLs von Microsoft Cloud Deutschland bleiben erhalten (Beispiel: `contoso.sharepoint.de`) Tokens, die von Microsoft Cloud Deutschland oder Office 365-Diensten herausgegeben wurden, bleiben während dem Übergang gültig. | SharePoint-Kunden | – Inhalte werden für zwei kurze Perioden während der Migration schreibgeschützt sein. Währen dieser Zeit wird ein Banner „Sie können Inhalte nicht bearbeiten“ in SharePoint angezeigt. <br><br> – Der Suchindex bleibt nicht erhalten, und es kann bis zu 10 Tage dauern, bis er wieder aufgebaut ist. <br><br> – SharePoint/OneDrive-Inhalte werden für zwei kurze Perioden während der Migration schreibgeschützt sein. Benutzer werden während dieser Zeit kurzfristig ein Banner „Sie können Inhalte nicht bearbeiten“ sehen. <br><br> – Der Suchindex ist möglicherweise nicht verfügbar, während der Index neu aufgebaut wird. Während dieser Periode geben Suchanfragen möglicherweise unvollständige Resultate zurück. <br><br> – Vorhandene Websites bleiben erhalten. |
|||||

Zusätzliche Überlegungen:

- Nach Abschluss der SharePoint Online-Migration in die Region Deutschland werden Datenindizes neu erstellt. Funktionen, die von Suchindizes abhängig sind, können betroffen sein, bis die Neuindizierung abgeschlossen ist.

- Wenn Ihre Organisation immer noch SharePoint 2010-Workflows verwendet, werden diese nach 31. Dezember 2021 nicht mehr funktionieren. SharePoint 2013-Workflows bleiben unterstützt, obwohl sie ab 1. November 2020 für neue Mandaten standardmäßig ausgeschaltet werden. Wenn die Migration zu den SharePoint Onlinediensten abgeschlossen ist, empfehlen wir, dass Sie zu Power Automate oder anderen unterstützten Lösungen wechseln.

- Nach Abschluss der OneDrive-Migration in die Region Deutschland werden Datenindizes neu erstellt. Funktionen, die von Suchindizes abhängig sind, können betroffen sein, während die Neuindizierung im Gange ist.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz noch nicht migriert wurde, müssen bei Version 16.0.20616.12000 (oder niedriger) von SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM bleiben. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.

- Microsoft Cloud Deutschland-Kunden, deren SharePoint Online-Instanz bereits migriert wurde, müssen SharePoint Online-PowerShell-Modul/Microsoft.SharePointOnline.CSOM auf Version 16.0.20717.12000 oder höher aktualisieren. Andernfalls schlagen Verbindungen zu SharePoint Online über PowerShell oder das clientseitige Objektmodell fehl.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Phase 5 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Die neue Region Deutschland wird der vorhandenen Organisationseinrichtung hinzugefügt, und Postfächer werden zu Office 365-Diensten verschoben. | Die Exchange Online-Konfiguration fügt die neue lokale deutsche Region zur Übergangsorganisation hinzu. Diese Office 365-Dienste-Region ist standardmäßig festgelegt, sodass der interne Lastenausgleichsdienst die Postfächer an die entsprechende Standardregion in den Office 365-Diensten weiterverteilen kann. Bei diesem Übergang befinden sich die Benutzer beider Seiten (Deutschland oder Office 365-Dienste) in der gleichen Organisation und können einen der beiden URL-Endpunkte verwenden. | Exchange Online | - Übergang von Benutzern und Diensten von Ihren älteren URLs (outlook.office.de) zu neuen URLs für Office 365-Dienste ( `https://outlook.office365.com` ). <br><br> – Benutzer können während der Migration weiterhin über ältere URLs in Deutschland auf den Dienst zugreifen, müssen jedoch nach Abschluss der Migration die Verwendung der älteren URLs beenden. <br><br> - Benutzer sollten auf das weltweite Office-Portal für Office Online-Features (Kalender, E-Mail, Personen) umgestellt werden. Die Navigation zu Diensten, die noch nicht zu Office 365-Diensten migriert wurden, funktioniert erst, wenn sie migriert wurden. <br><br> – Die Outlook Web App bietet während der Migration keine Öffentliche Ordner-Erfahrung. |
| Aktualisieren von benutzerdefinierten DNS-Einstellungen für die AutoErmittlung| Vom Kunden verwaltete DNS-Einstellungen für die AutoErmittlung, die derzeit auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, um nach Abschluss der Exchange Online-Phase (Phase 5) auf Office 365 zu verweisen. <br> Vorhandene #A0 mit CNAME, die auf autodiscover-outlook.office.de müssen aktualisiert werden, um auf autodiscover.outlook.com. | Exchange Online | Verfügbarkeitsanforderungen und Dienstermittlungsaufrufe über AutoErmittlungspunkt direkt an die Office 365-Dienste. Kunden, die diese DNS-Updates nicht ausführen, treten beim Abschluss der Migration möglicherweise Probleme mit dem AutoErmittlungsdienst auf. |
|||||

Zusätzliche Überlegungen:

- `myaccount.msft.com` wird erst nach der Übernahme auf Office 365 funktionieren. Links werden bis zu diesem Zeitpunkt Fehlermeldungen wie „Etwas ist fehlgeschlagen“ zurückgeben.

- Benutzer, die mit Outlook Web App auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (Beispiel: ein Benutzer in der Deutschland-Umgebung greift auf ein freigegebenes Postfach in der globalen Umgebung zu), werden aufgefordert, sich ein zweites Mal zu authentifizieren. Der Benutzer muss sich zuerst authentifizieren und auf sein eigenes Postfach in `outlook.office.de` zugreifen und dann das freigegebene Postfach in `outlook.office365.com` öffnen. Sie müssen sich ein zweites Mal authentifizieren, wenn sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.

- Für bestehende Microsoft Cloud Deutschland-Kunden oder solche, die sich in der Übergangsphase befinden, kann das Anzeigen von Kalenderberechtigungen fehlschlagen, wenn ein freigegebenes Postfach über **Datei > Info > Konto hinzufügen** zu Outlook hinzugefügt wird (der Outlook-Client versucht, die Rest-API `https://outlook.office.de/api/v2.0/Me/Calendars` zu verwenden). Kunden, die ein Konto hinzufügen möchten, um Kalenderberechtigungen anzuzeigen, können den Registrierungsschlüssel wie in [Änderungen der Benutzererfahrung für die Freigabe eines Kalenders in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich sein wird. Dieser Registrierungsschlüssel kann unternehmensweit über eine Gruppenrichtlinie bereitgestellt werden.

- Die Verwendung der PowerShell-Cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, und **Test-MigrationsServerAvailability** kann während der Migrationsphase zu Fehlern führen (Fehler auf dem Proxy). Dies geschieht, wenn das Vermittlungspostfach auf weltweit migriert wurde, das Administrator-Postfach aber noch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandantensitzung das Vermittlungspostfach als Routing-Hinweis in **ConnectionUri**. Beispiel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Wenn Sie Exchange Online Hybrid verwenden:

    - Exchange Online Hybrid-Kunden müssen den Assistenten für die Hybridkonfiguration (Hybrid Configuration Wizard, HCW) im Rahmen dieses Übergangs mehrmals ausführen. Bevor der Migrationsschritt **5 beginnt,** muss jeder Exchange Online-Hybridkunde die neueste Version des HCW im Office 365 Deutschland-Modus ausführen, um die lokale Konfiguration für die Migration zu Office 365 global vorzubereiten. Nach Abschluss der Migrationsphase **5** (wenn der Message Center-Hinweis veröffentlicht wird) müssen Sie den HCW für die Verwendung von Office 365 Worldwide-Einstellungen ausführen, um Ihre lokalen Systeme auf den globalen Dienst zu verweisen. Wenn Sie benutzerdefinierte Domänen verwenden, werden möglicherweise weitere DNS-Updates erforderlich sein.

Um mehr über die Unterschiede zwischen Organisationen bei der Migration und nach der Migration von Exchange Online-Ressourcen zu erfahren, lesen Sie die Informationen in [Kundenerfahrung während der Migration zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (Phase 6 von 9)

Die Backend-Funktionen von Exchange Online Protection (EOP) werden in die neue Region Deutschland kopiert. 

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Migration des Exchange Online-Routing und von historischen Nachrichtendetails. | Exchange Online ermöglicht das Weiterleiten von externen Hosts auf Office 365. Die externen MX-Datensätze werden umgestellt, um auf die EOP-Dienste weiterzuleiten. Die Mandanten-Konfiguration und historische Details werden migriert. | Exchange Online-Kunden | – Microsoft-verwaltete DNS-Einträge werden von Office 365 Deutschland EOP zu Office 365-Diensten aktualisiert. <br><br> – Kunden sollten währen 30 Tagen nach dem EOP Dual Write auf die EOP-Migration warten. Anderenfalls kann es zu einem Datenverlust kommen. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (Phase 7 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Wechseln von Skype for Business zu Microsoft Teams. | Bestehende Skype for Business-Kunden werden auf Office 365-Dienste in Europa migriert und anschließend auf Microsoft Teams in der Region Deutschland der Office 365-Dienste umgestellt. | Skype for Business-Kunden | – Benutzer können sich am Migrationsdatum nicht bei Skype for Business anmelden. Zehn Tage vor der Migration werden Sie im Admin Center über den Zeitpunkt der Migration informiert, und erneut, wenn die Migration beginnt. <br><br> – Die Richtlinienkonfiguration wird migriert.  <br><br> – Die Benutzer werden nach Teams migriert und verfügen nach der Migration nicht mehr über Skype for Business. <br><br> – Die Benutzer müssen den Teams-Desktopclient installiert haben. Die Installation erfolgt während der 10 Tage über Richtlinien in der Skype for Business-Infrastruktur. Wenn dies jedoch fehlschlägt, müssen Benutzer den Client manuell herunterladen oder eine Verbindung mit einem unterstützten Browser herstellen. <br><br> – Kontakte und Besprechungen werden nach Teams migriert. <br><br> – Benutzer können sich während der Übergangszeit der Dienste nach Office 365-Dienste nicht in Skype for Business anmelden und auch nicht, bevor die Kunden-DNS-Einträge abgeschlossen sind. <br><br> – Kontakte und vorhandene Besprechungen werden weiterhin als Skype for Business-Besprechungen funktionieren.  |
|||||


## <a name="office-apps-phase-8-of-9"></a>Office-Apps (Phase 8 von 9)

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Clients, Office Online während der Office-Client-Übernahmemigration, Azure AD finalisiert den Mandantenbereich so, dass er auf die Office 365-Dienste verweist. | Mit dieser Konfigurationsänderung können Office-Clients aktualisiert und auf die Office 365-Dienstendpunkte verweisen. | Alle Office-Kunden | – Benachrichtigen Sie die Benutzer, dass _alle_ Office-Apps geschlossen werden, und melden Sie sich dann erneut an (oder erzwingen Sie den Neustart der Clients und die Anmeldung der Benutzer), damit die Office-Clients die Änderung übernehmen können. <br><br> – Informieren Sie die Benutzer und Mitarbeiter des Helpdesks, dass Benutzern *möglicherweise* ein Office-Banner angezeigt wird, das sie dazu auffordert, Office-Apps innerhalb von 72 Stunden nach der Übernahmemigration zu reaktivieren. <br><br> – Alle Office-Anwendungen auf privaten Computern müssen geschlossen werden, und die Benutzer müssen sich abmelden und dann erneut anmelden. Melden Sie sich in der gelben Aktivierungsleiste an, um die Office 365-Dienste zu reaktivieren. <br><br> – Gemeinsam genutzte Computer erfordern Aktionen, die mit privaten Computern vergleichbar sind, erfordern aber keine spezielle Vorgehensweise. <br><br> – Auf mobilen Geräten müssen sich die Benutzer von Apps abmelden, sie schließen und sich dann erneut anmelden. |
|||||


## <a name="office-services"></a>Office-Dienste

Der Dienst „zuletzt verwendet“ (most recently used, MRU) in Office ist eine Übernahme des Deutschland-Dienstes zu Office 365-Dienste, keine Migration.  Nach der Migration vom Office.com-Portal werden nur MRU-Links von der Seite der Office 365-Dienste sichtbar sein. MRU-Links vom Deutschland-Dienst werden nicht als MRU-Links in den Office 365-Diensten sichtbar sein. MRU-Links in Office 365 sind erst verfügbar, wenn die Mandanten-Migration abgeschlossen ist.

## <a name="subscription"></a>Abonnement

| Schritt(e) | Beschreibung | Betrifft | Auswirkung |
|:-------|:-----|:-------|:-------|
| Wir können Kunden ohne ihre Zustimmung nicht migrieren. | Microsoft hat das Recht, auf zwei Arten zu migrieren, wodurch Microsoft den Übergang von Daten und Diensten zur Office 365-Dienstinstanz koordinieren kann. <br> Der Administrator meldet sich für die von Microsoft gesteuerte Migration an. <br> Kunden erneuern sämtliche Abonnements in ihrem Microsoft Cloud Deutschland-Mandanten nach dem 1. Mai 2020. Wir werden diese Kunden jeden Monat über das Migrationsrecht informieren, 30 Tage warten, um den Kunden die Möglichkeit zu geben, die Migration zu stornieren, und uns dann direkt anmelden und dies in ICM nachverfolgen. | Alle Office-Kunden | – Der Mandant ist als mit der Migration einverstanden markiert und das Admin Center zeigt die Bestätigung. <br><br> – Die Zustimmung wird im Mandanten-Nachrichtencenter von Cloud Deutschland veröffentlicht. Die Dienstkonfiguration wird von den Endpunkten der Microsoft Cloud Deutschland fortgesetzt. <br><br> – Monitor-Nachrichtencenter für Aktualisierungen des Status der Migrationsphasen. |
| Abonnements werden übertragen und Lizenzen werden neu zugewiesen. | Nach der Umstellung des Mandanten auf Office 365-Dienste werden für die übertragenen Microsoft Cloud Deutschland-Abonnements entsprechende Office 365-Dienste-Abonnements erworben. Benutzer mit zugewiesenen Lizenzen von Microsoft Cloud Deutschland erhalten Lizenzen für Office 365-Dienste zugewiesen. Alte Microsoft Cloud Deutschland-Abonnements werden nach Abschluss aus dem Office 365-Dienste-Mandanten entfernt. | Alle Office Kunden | – Änderungen an bestehenden Abonnements (z. B. der Kauf neuer Abonnements oder Änderung der Arbeitsplatzzahl) werden während dieser Phase blockiert. <br><br> – Änderungen der Lizenzzuweisung werden blockiert.  <br><br> – Das Microsoft Cloud Deutschland-Abonnement wird auf ein entsprechendes Office 365-Dienste-Abonnement migriert. Das Office 365-Dienste-Angebot dieses Abonnements wird von Microsoft definiert (auch als _Angebotsabbildung_ bekannt). <br><br> – Die Anzahl der Features (Dienstpläne), die von Office 365-Diensten angeboten werden, kann höher sein als im ursprünglichen Microsoft Cloud Deutschland-Angebot.  Benutzerlizenzen in Office 365-Diensten werden äquivalent zu ähnlichen Microsoft Cloud Deutschland-Funktionen (Servicepläne) zugewiesen. Benutzerlizenzen aller Benutzer werden automatisch an diese neuen Features zugewiesen. Falls notwendig, muss der Administrator die Deaktivierung dieser Lizenzen durch eine explizite Aktion vornehmen. <br><br> – Wenn die Migration der Abonnements abgeschlossen ist, werden sowohl Office 365-Dienste wie auch Deutschland-Abonnements im Office 365 Admin-Portal sichtbar sein, der Staus der Deutschland-Abonnements wird _abgemeldet_ sein. <br><br> – Den Benutzern werden neue Lizenzen zugewiesen, die an die neuen Office 365-Dienste-Abonnements gebunden sind. Alle Kundenprozesse mit Abhängigkeiten zu Deutschland-Abonnements oder SKU GUIDs werden unterbrochen und müssen mit dem Office 365-Serviceangebot überarbeitet werden. <br><br> – Neue Abonnements für die Office 365-Dienste werden mit der neuen Laufzeit (monatlich/vierteljährlich/jährlich) erworben, und der Kunde erhält eine anteilige Rückerstattung für den nicht verwendeten Restbetrag des Microsoft Cloud Deutschland-Abonnements. <br><br> – Mandanten von Partner Microsoft Cloud Deutschland werden nicht migriert. CSP-Kunden werden unter dem neuen Mandanten für Office 365-Dienste desselben Partners auf Office 365-Dienste migriert. Nach der Kundenmigration kann der Partner diesen Kunden nur noch über den Mandanten für Office 365-Dienste verwalten. <br><br> – Zusätzliche Funktionalitäten sind verfügbar (z. B. Microsoft Planner und Microsoft Flow), sofern sie nicht vom Mandantenadministrator deaktiviert wurden. Informationen zum Deaktivieren von Dienstplänen, die Benutzerlizenzen zugewiesen sind, finden Sie unter [Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Nächster Schritt

[Zusätzliche Vorarbeit durchführen](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
